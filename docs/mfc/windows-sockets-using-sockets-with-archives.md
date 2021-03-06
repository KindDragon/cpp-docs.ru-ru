---
title: "Сокеты Windows: Использование сокетов с архивами | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], archives
- sockets [MFC], with archives
- archives [MFC], and Windows Sockets
- CSocket class [MFC], programming model
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c9956e48f88988dfec7e04cda5bba95e514ec109
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-using-sockets-with-archives"></a>Сокеты Windows. Использование сокетов с архивами
В этой статье описывается [модель программирования CSocket](#_core_the_csocket_programming_model). Класс [CSocket](../mfc/reference/csocket-class.md) предоставляет поддержка сокета на более высоком уровне абстракции, чем класс [CAsyncSocket](../mfc/reference/casyncsocket-class.md). `CSocket`использует версию протокола сериализации MFC для передачи данных с объектом сокета посредством MFC [CArchive](../mfc/reference/carchive-class.md) объекта. `CSocket`предоставляет блокировку (при управлении фоновой обработки сообщений Windows) и предоставляет доступ к `CArchive`, который управляет многие аспекты связи, который необходимо сделать самостоятельно с помощью необработанных API-Интерфейс или класс `CAsyncSocket`.  
  
> [!TIP]
>  Класс можно использовать `CSocket` сам по себе, как более удобным версия `CAsyncSocket`, но использовать это самая простая модель программирования `CSocket` с `CArchive` объекта.  
  
 Дополнительные сведения о работе реализации сокетов с архивами см. в разделе [Windows Sockets: как сокетов с архивирует рабочих](../mfc/windows-sockets-how-sockets-with-archives-work.md). Пример кода см. в разделе [Windows Sockets: последовательность операций](../mfc/windows-sockets-sequence-of-operations.md) и [Windows Sockets: пример из сокетов с использованием архивов](../mfc/windows-sockets-example-of-sockets-using-archives.md). Сведения о некоторых функциональных возможностей, можно получить путем наследования из классов сокетов собственных классов, в разделе [Windows Sockets: наследование от классов сокета](../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
> [!NOTE]
>  При написании программы MFC клиента для взаимодействия с серверами установленное (не являющихся MFC), не отправляйте объектами C++ с помощью архива. Не является приложение MFC, который понимает типы объектов, которые вы хотите отправить, оно не будет возможность получения и десериализации объектов. Связанные материалы о субъекте взаимодействия с приложениями, не являющихся MFC также см. в статье [Windows Sockets: порядок байтов](../mfc/windows-sockets-byte-ordering.md).  
  
##  <a name="_core_the_csocket_programming_model"></a>Модель программирования CSocket  
 С помощью `CSocket` объект включает в себя создание и связывание друг с другом несколько объектов классов MFC. В общую процедуру каждый шаг выполняемое сокета сервера и клиента сокета, за исключением шаге 3, в котором для каждого типа сокета требуется другое действие.  
  
> [!TIP]
>  Во время выполнения серверного приложения обычно начинается сначала готовности и «прослушивается», когда клиентское приложение ищет соединения. Если сервер не готов, когда клиент пытается подключиться, обычно требуется пользовательское приложение, чтобы повторить попытку позже.  
  
#### <a name="to-set-up-communication-between-a-server-socket-and-a-client-socket"></a>Настройка обмена данными между сокета сервера и сокета клиента  
  
1.  Создать [CSocket](../mfc/reference/csocket-class.md) объекта.  
  
2.  Использовать объект для создания базового **СОКЕТА** обработки.  
  
     Для `CSocket` объекта клиента, обычно следует использовать параметры по умолчанию для [создать](../mfc/reference/casyncsocket-class.md#create), если не требуется сокета датаграмм. Для `CSocket` объект сервера, необходимо указать порт в **создать** вызова.  
  
    > [!NOTE]
    >  `CArchive`не удается выполнить сокеты датаграмм. Если вы хотите использовать `CSocket` для сокета датаграмм, необходимо использовать класс, как используется `CAsyncSocket`, то есть без архивации. Поскольку ненадежны датаграмм (не прибывают и повторно или не по порядку), не совместимы с сериализацией через архив. Предполагается, что операции сериализации для завершения надежно и в последовательности. При попытке использовать `CSocket` с `CArchive` объекта датаграммы, ошибке утверждения MFC.  
  
3.  Если клиент является сокета, вызовите [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect) подключение объекта сокета сокета сервера.  
  
     - или -  
  
     Если сокет является сервером, вызовите [CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen) для начала прослушивание подключения попыток от клиента. При получении запроса на подключение, примите его путем вызова [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept).  
  
    > [!NOTE]
    >  **Accept** функции-члена принимает ссылку на новый, пустой `CSocket` объект в качестве параметра. Этот объект необходимо создать перед вызовом метода **Accept**. Если этот объект сокета выходит за пределы области, закрывает соединение. Не вызывайте **создать** для этого нового объекта сокета.  
  
4.  Создание [CSocketFile](../mfc/reference/csocketfile-class.md) объекта связывание `CSocket` объекта с ним.  
  
5.  Создание [CArchive](../mfc/reference/carchive-class.md) объект для загрузки (получение) или хранения данных (отправки). Архив, связанные с `CSocketFile` объекта.  
  
     Имейте в виду, что `CArchive` не работает с сокеты датаграмм.  
  
6.  Используйте `CArchive` для передачи данных между клиентом и сервером сокетов.  
  
     Имейте в виду, что данный `CArchive` объекта перемещает данные только в одном направлении: для загрузки (получение) или хранения (отправки). В некоторых случаях будет использовать два `CArchive` объектов: один для отправки данных, другой — для получения подтверждения.  
  
     После принятия запроса на подключение и настройка архив, вы можете выполнить такие задачи, как проверка паролей.  
  
7.  Уничтожить архива, файл сокетов и объекты сокета.  
  
    > [!NOTE]
    >  Класс `CArchive` предоставляет `IsBufferEmpty` функции-члена специально для использования с классом `CSocket`. Если буфер содержит несколько сообщений с данными, например, необходимо в цикл, пока все они доступны для чтения и буфер удаляется. В противном случае отсутствуют данные, предназначенные для получения следующего уведомления бесконечно с задержкой. Используйте `IsBufferEmpty` для гарантии, что можно получить все данные.  
  
 Статья [Windows Sockets: последовательность операций](../mfc/windows-sockets-sequence-of-operations.md) обе части этого процесса пример кода иллюстрирует.  
  
 Дополнительные сведения:  
  
-   [Сокеты Windows. Сокеты потоков](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Сокеты Windows. Сокеты датаграмм](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>См. также  
 [Сокеты Windows в MFC](../mfc/windows-sockets-in-mfc.md)   
 [CSocket::Create](../mfc/reference/csocket-class.md#create)

