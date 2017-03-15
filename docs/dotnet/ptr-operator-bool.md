---
title: "ptr::operator bool | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ptr::operator bool"
  - "ptr.operator bool"
  - "operator bool"
  - "msclr::com::ptr::operator bool"
  - "msclr.com.ptr.operator bool"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr::operator bool"
ms.assetid: 31123377-6ecd-4cef-9b75-3db3996fbcd1
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ptr::operator bool
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Operator for using `com::ptr` in a conditional expression.  
  
## 구문  
  
```  
operator bool();  
```  
  
## 반환 값  
 `true` if the owned COM object is valid; `false` otherwise.  
  
## 설명  
 The owned COM object is valid if it is not `nullptr`.  
  
 This operator actually converts to `_detail_class::_safe_bool` which is safer than `bool` because it cannot be converted to an integral type.  
  
## 예제  
 This example implements a CLR class that uses a `com::ptr` to wrap its private member `IXMLDOMDocument` object.  The `CreateInstance` member function uses `operator bool` after creating the new document object to determine if it is valid and writes to the console if it is.  
  
```  
// comptr_op_bool.cpp  
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
   void CreateInstance(String^ progid) {  
      if (!m_ptrDoc) {  
         m_ptrDoc.CreateInstance(progid);     
         if (m_ptrDoc) { // uses operator bool  
            Console::WriteLine("DOM Document created.");  
         }  
      }  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   try {  
      XmlDocument doc;  
      // create the instance from a progid string  
      doc.CreateInstance("Msxml2.DOMDocument.3.0");  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
}  
```  
  
  **DOM Document created.**   
## 요구 사항  
 **Header file** \<msclr\\com\\ptr.h\>  
  
 **Namespace** msclr::com  
  
## 참고 항목  
 [ptr 멤버](../dotnet/ptr-members.md)   
 [ptr::operator\!](../dotnet/ptr-operator-logical-not.md)