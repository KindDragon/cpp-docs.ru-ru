---
title: "Обработка событий в COM | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- event handling [C++], COM
- event handling [C++], about event handling
- declaring events
- event handlers [C++], COM
- event handlers
- COM, events
- event receivers, in event handling
- event handling [C++]
- hooking events
- event receivers, name and signature matching
- event sources, in event handling
- declaring events, in COM
- declaring events, event handling in COM
ms.assetid: 6b4617d4-a58e-440c-a8a6-1ad1c715b2bb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1c57b8429a05ab3989dce318f4c16a58475560a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="event-handling-in-com"></a>Обработка событий в COM
Обработка событий COM, необходимо настроить событие источник и приемник событий с помощью [event_source](../windows/event-source.md) и [event_receiver](../windows/event-receiver.md) атрибуты, соответственно, указав `type` = **com**. Эти атрибуты вводят соответствующий код для пользовательского, сдвоенного интерфейса и интерфейса диспетчеризации, чтобы позволить классам, к которым они применяются, запускать и обрабатывать события через точки подключения COM.  
  
## <a name="declaring-events"></a>Объявление событий  
 В классе источника событий используйте [__event](../cpp/event.md) ключевое слово в объявлении интерфейса, чтобы объявить методы интерфейса в качестве событий. События этого интерфейса запускаются при вызове их в качестве методов интерфейса. Методы в интерфейсах событий могут иметь ноль или более параметров (все они должны являться **в** параметров). Тип возвращаемого значения может быть пустым или любым целочисленным типом.  
  
## <a name="defining-event-handlers"></a>Определение обработчиков событий  
 В классе приемника событий необходимо указать обработчики событий, которые представляют собой методы с подписями (типы возвращаемого значения, соглашения о вызовах и аргументы), соответствующие событию, которое они будут обрабатывать. Для событий модели COM соглашения о вызовах не должны совпадать; в разделе [события COM, зависимые от макета](#vcconeventhandlingincomanchorlayoutdependentcomevents) ниже сведения.  
  
## <a name="hooking-event-handlers-to-events"></a>Прикрепление обработчиков событий к событиям  
 Также в классе приемника событий, можно использовать встроенную функцию [__hook](../cpp/hook.md) для связывания событий с обработчиками событий и [__unhook](../cpp/unhook.md) отменить связь событий от обработчиков событий. Можно прикрепить несколько событий к обработчику событий либо несколько обработчиков событий к одному событию.  
  
> [!NOTE]
>  Как правило, существует два метода предоставления приемнику событий COM доступа к определениям интерфейса исходного кода событий. Во-первых, как показано ниже, можно предоставить общий доступ к одному файлу заголовка. Второй — для использования [#import](../preprocessor/hash-import-directive-cpp.md) с `embedded_idl` квалификатором импорта, чтобы библиотека типов исходного события записываются в файл .tlh с сохранением созданного атрибутом кода.  
  
## <a name="firing-events"></a>Запуск событий  
 Для запуска события достаточно вызвать метод в интерфейсе, объявленном с использованием ключевого слова `__event` в классе исходного кода событий. Если обработчики прикреплены к событию, они будут вызваны.  
  
### <a name="com-event-code"></a>Код события COM  
 В следующем примере демонстрируется запуск события в COM-классе. Для компиляции и выполнения примера см. комментарии в коде.  
  
```  
// evh_server.h  
#pragma once  
  
[ dual, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IEvents {  
   [id(1)] HRESULT MyEvent([in] int value);  
};  
  
[ dual, uuid("00000000-0000-0000-0000-000000000002") ]  
__interface IEventSource {  
   [id(1)] HRESULT FireEvent();  
};  
  
class DECLSPEC_UUID("530DF3AD-6936-3214-A83B-27B63C7997C4") CSource;  
```  
  
 Затем сервер.  
  
```  
// evh_server.cpp  
// compile with: /LD  
// post-build command: Regsvr32.exe /s evh_server.dll  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include "evh_server.h"  
  
[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];  
  
[coclass, event_source(com), uuid("530DF3AD-6936-3214-A83B-27B63C7997C4")]  
class CSource : public IEventSource {  
public:  
   __event __interface IEvents;   
  
   HRESULT FireEvent() {  
      __raise MyEvent(123);  
      return S_OK;  
   }  
};  
```  
  
 Затем клиент.  
  
```  
// evh_client.cpp  
// compile with: /link /OPT:NOREF  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <stdio.h>  
#include "evh_server.h"  
  
[ module(name="EventReceiver") ];  
  
[ event_receiver(com) ]  
class CReceiver {  
public:  
   HRESULT MyHandler1(int nValue) {  
      printf_s("MyHandler1 was called with value %d.\n", nValue);  
      return S_OK;  
   }  
  
   HRESULT MyHandler2(int nValue) {  
      printf_s("MyHandler2 was called with value %d.\n", nValue);  
      return S_OK;  
   }  
  
   void HookEvent(IEventSource* pSource) {  
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);  
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
  
   void UnhookEvent(IEventSource* pSource) {  
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);  
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
};  
  
int main() {  
   // Create COM object  
   CoInitialize(NULL);  
   {  
      IEventSource* pSource = 0;  
      HRESULT hr = CoCreateInstance(__uuidof(CSource), NULL,         CLSCTX_ALL, __uuidof(IEventSource), (void **) &pSource);  
      if (FAILED(hr)) {  
         return -1;  
      }  
  
      // Create receiver and fire event  
      CReceiver receiver;  
      receiver.HookEvent(pSource);  
      pSource->FireEvent();  
      receiver.UnhookEvent(pSource);  
   }  
   CoUninitialize();  
   return 0;  
}  
```  
  
### <a name="output"></a>Вывод  
  
```  
MyHandler1 was called with value 123.  
MyHandler2 was called with value 123.  
```  
  
##  <a name="vcconeventhandlingincomanchorlayoutdependentcomevents"></a>Макет зависимых COM-событий  
 Зависимость от макета становится проблемой только в программировании COM. При обработке событий в собственном и управляемом коде подписи (возвращаемый тип, соглашение о вызовах и аргументы) обработчиков должны соответствовать их событиям, однако имена обработчиков не обязательно должны соответствовать событиям.  
  
 Тем не менее, при обработке событий COM, при установке *layout_dependent* параметр **event_receiver** для **true**, обеспечивается совпадение имени и подписи. Это означает, что имена и подписи обработчиков в приемнике событий должны точно соответствовать именам и подписям событий, к которым они прикреплены.  
  
 При *layout_dependent* равно **false**, вызывающий соглашение и класс хранения (виртуальный, статический и т. д.) можно mixed и разных сочетаниях метод событий и методах прикрепления (его делегаты). Это немного более рационально использовать *layout_dependent*=**true**.  
  
 Например, предположим, что `IEventSource` определен как объект, имеющий следующие методы.  
  
```  
[id(1)] HRESULT MyEvent1([in] int value);  
[id(2)] HRESULT MyEvent2([in] int value);  
```  
  
 Предположим, источник событий имеет следующую форму:  
  
```  
[coclass, event_source(com)]  
class CSource : public IEventSource {  
public:  
   __event __interface IEvents;  
  
   HRESULT FireEvent() {  
      MyEvent1(123);  
      MyEvent2(123);  
      return S_OK;  
   }  
};  
```  
  
 Затем в приемнике событий любой обработчик, который прикрепляется к методу в `IEventSource`, должен соответствовать имени и подписи следующим образом.  
  
```  
[coclass, event_receiver(com, true)]  
class CReceiver {  
public:  
   HRESULT MyEvent1(int nValue) {  // name and signature matches MyEvent1  
      ...  
   }  
   HRESULT MyEvent2(E c, char* pc) {  // signature doesn't match MyEvent2  
      ...  
   }  
   HRESULT MyHandler1(int nValue) {  // name doesn't match MyEvent1 (or 2)  
      ...  
   }  
   void HookEvent(IEventSource* pSource) {  
      __hook(IFace, pSource);  // Hooks up all name-matched events   
                               // under layout_dependent = true  
      __hook(&IFace::MyEvent1, pSource, &CReceive::MyEvent1);   // valid  
      __hook(&IFace::MyEvent2, pSource, &CSink::MyEvent2);   // not valid  
      __hook(&IFace::MyEvent1, pSource, &CSink:: MyHandler1); // not valid  
   }  
};  
```  
  
## <a name="see-also"></a>См. также  
 [Обработка событий](../cpp/event-handling.md)