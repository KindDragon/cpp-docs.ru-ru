---
title: "PTR::QueryInterface | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ptr.QueryInterface
- ptr::QueryInterface
- msclr::com::ptr::QueryInterface
- msclr.com.ptr.QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method
ms.assetid: c2619517-3fde-493b-b12d-da8f62d5d803
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 687c57c32d4f270d397e3ed8fd068d603cbcb9b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ptrqueryinterface"></a>ptr::QueryInterface
Запрашивает у владельца объекта COM для интерфейса и прикрепляет результаты в другой `com::ptr`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class _other_type>  
void QueryInterface(  
   ptr<_other_type> % other  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `other`  
 `com::ptr` , Получите интерфейс.  
  
## <a name="exceptions"></a>Исключения  
 На внутреннем уровне `QueryInterface` будет вызван на собственный объект COM и любая ошибка `HRESULT` преобразуется в исключение по <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>.  
  
## <a name="remarks"></a>Примечания  
 Используйте этот метод для создания оболочки COM для другой интерфейс COM-объекта, принадлежащие текущей программой-оболочкой. Этот метод вызывает метод `QueryInterface` через собственные COM-объект для запроса указатель на определенный интерфейс COM-объекта и присоединяет возвращенного указателя на интерфейс переданный `com::ptr`.  
  
## <a name="example"></a>Пример  
 В этом примере реализуется класс CLR, который использует `com::ptr` программы-оболочки для своего закрытого члена `IXMLDOMDocument` объекта. `WriteTopLevelNode` Функция-член использует `QueryInterface` для заполнения локальной `com::ptr` с `IXMLDOMNode` , а затем передает `com::ptr` (путем отслеживания ссылок) функции закрытый член, которая выводит на консоль имя и текст свойства узла.  
  
```  
// comptr_queryinterface.cpp  
// compile with: /clr /link msxml2.lib  
#include <msxml2.h>  
#include <msclr\com\ptr.h>  
  
#import <msxml3.dll> raw_interfaces_only  
  
using namespace System;  
using namespace System::Runtime::InteropServices;  
using namespace msclr;  
  
// a ref class that uses a com::ptr to contain an   
// IXMLDOMDocument object  
ref class XmlDocument {  
public:  
   // construct the internal com::ptr with a null interface  
   // and use CreateInstance to fill it  
   XmlDocument(String^ progid) {  
      m_ptrDoc.CreateInstance(progid);     
   }  
  
   void LoadXml(String^ xml) {  
      pin_ptr<const wchar_t> pinnedXml = PtrToStringChars(xml);  
      BSTR bstr = NULL;  
  
      try {  
         // load some XML into our document  
         bstr = ::SysAllocString(pinnedXml);  
         if (NULL == bstr) {  
            throw gcnew OutOfMemoryException;  
         }  
         VARIANT_BOOL bIsSuccessful = false;  
         // use operator -> to call IXMODOMDocument member function  
         Marshal::ThrowExceptionForHR(m_ptrDoc->loadXML(bstr, &bIsSuccessful));  
      }  
      finally {  
         ::SysFreeString(bstr);  
      }  
   }  
  
   // write the top level node to the console  
   void WriteTopLevelNode() {  
      com::ptr<IXMLDOMNode> ptrNode;  
  
      // query for the top level node interface  
      m_ptrDoc.QueryInterface(ptrNode);  
      WriteNode(ptrNode);  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   // simplified function that only writes the node  
   void WriteNode(com::ptr<IXMLDOMNode> % node) {  
      BSTR bstr = NULL;  
  
      try {  
         // write out the name and text properties  
         Marshal::ThrowExceptionForHR(node->get_nodeName(&bstr));  
         String^ strName = gcnew String(bstr);  
         Console::Write("<{0}>", strName);  
         ::SysFreeString(bstr);  
         bstr = NULL;  
  
         Marshal::ThrowExceptionForHR(node->get_text(&bstr));  
         Console::Write(gcnew String(bstr));  
         ::SysFreeString(bstr);  
         bstr = NULL;  
  
         Console::WriteLine("</{0}>", strName);  
      }  
      finally {  
         ::SysFreeString(bstr);  
      }  
   }  
  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   try {  
      // create the class from a progid string  
      XmlDocument doc("Msxml2.DOMDocument.3.0");  
  
      // stream some xml into the document  
      doc.LoadXml("<word>persnickety</word>");  
  
      // write the document to the console  
      doc.WriteTopLevelNode();  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
}  
```  
  
```Output  
<#document>persnickety</#document>  
```  
  
## <a name="requirements"></a>Требования  
 **Файл заголовка** \<msclr\com\ptr.h >  
  
 **Пространство имен** msclr::com  
  
## <a name="see-also"></a>См. также  
 [Члены PTR](../dotnet/ptr-members.md)   
 [ptr::GetInterface](../dotnet/ptr-getinterface.md)