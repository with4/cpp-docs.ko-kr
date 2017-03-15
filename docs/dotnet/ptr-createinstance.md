---
title: "ptr::CreateInstance | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ptr.CreateInstance"
  - "msclr::com::ptr::CreateInstance"
  - "msclr.com.ptr.CreateInstance"
  - "ptr::CreateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr::CreateInstance"
ms.assetid: 9e8e4c4c-1651-4839-8829-5857d74470fe
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# ptr::CreateInstance
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Creates an instance of a COM object within a `com::ptr`.  
  
## 구문  
  
```  
void CreateInstance(  
   System::String ^ progid,  
   LPUNKNOWN pouter,  
   DWORD cls_context  
);  
void CreateInstance(  
   System::String ^ progid,  
   LPUNKNOWN pouter  
);  
void CreateInstance(  
   System::String ^ progid  
);  
void CreateInstance(  
   const wchar_t * progid,  
   LPUNKNOWN pouter,  
   DWORD cls_context  
);  
void CreateInstance(  
   const wchar_t * progid,  
   LPUNKNOWN pouter  
);  
void CreateInstance(  
   const wchar_t * progid  
);  
void CreateInstance(  
   REFCLSID rclsid,  
   LPUNKNOWN pouter,  
   DWORD cls_context  
);  
void CreateInstance(  
   REFCLSID rclsid,  
   LPUNKNOWN pouter  
);  
void CreateInstance(  
   REFCLSID rclsid  
);  
```  
  
#### 매개 변수  
 `progid`  
 `ProgID` 문자열입니다.  
  
 `pouter`  
 Pointer to the aggregate object's IUnknown interface \(the controlling IUnknown\).  If `pouter` is not specified, `NULL` is used.  
  
 `cls_context`  
 Context in which the code that manages the newly created object will run.  The values are taken from the `CLSCTX` enumeration.  If `cls_context` is not specified, the value CLSCTX\_ALL is used.  
  
 `rclsid`  
 `CLSID` associated with the data and code that will be used to create the object.  
  
## 예외  
 If the `com::ptr` already owns a reference to a COM object, `CreateInstance` throws <xref:System.InvalidOperationException>.  
  
 This function calls `CoCreateInstance` and uses <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> to convert any error `HRESULT` to an appropriate exception.  
  
## 설명  
 `CreateInstance` uses `CoCreateInstance` to create a new instance of the specified object, identified either from a ProgID or a CLSID.  The `com::ptr` references the newly created object and will automatically release all owned references upon destruction.  
  
## 예제  
 This example implements a CLR class that uses a `com::ptr` to wrap its private member `IXMLDOMDocument` object.  The class constructors use two different forms of `CreateInstance` to create the document object either from a ProgID or from a CLSID plus a CLSCTX.  
  
```  
// comptr_createinstance.cpp  
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
   XmlDocument(REFCLSID clsid, DWORD clsctx) {  
      m_ptrDoc.CreateInstance(clsid, NULL, clsctx);  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   try {  
      // create the class from a progid string  
      XmlDocument doc1("Msxml2.DOMDocument.3.0");  
  
      // or from a clsid with specific CLSCTX  
      XmlDocument doc2(CLSID_DOMDocument30, CLSCTX_INPROC_SERVER);  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
}  
```  
  
## 요구 사항  
 **Header file** \<msclr\\com\\ptr.h\>  
  
 **Namespace** msclr::com  
  
## 참고 항목  
 [ptr 멤버](../dotnet/ptr-members.md)