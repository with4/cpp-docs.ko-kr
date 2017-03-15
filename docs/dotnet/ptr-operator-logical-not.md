---
title: "ptr::operator! | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ptr::operator!"
  - "msclr::com::ptr::operator!"
  - "ptr.operator!"
  - "msclr.com.ptr.operator!"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr::operator!"
ms.assetid: 7f4101dc-2045-42e7-abb1-6a30e17147f2
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ptr::operator!
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Operator to determine if the owned COM object is invalid.  
  
## 구문  
  
```  
bool operator!();  
```  
  
## 반환 값  
 `true` if the owned COM object is invalid; `false` otherwise.  
  
## 설명  
 The owned COM object is valid if it is not `nullptr`.  
  
## 예제  
 This example implements a CLR class that uses a `com::ptr` to wrap its private member `IXMLDOMDocument` object.  The `CreateInstance` member function uses `operator!` to determine if a document object is already owned, and only creates a new instance if the object is invalid.  
  
```  
// comptr_op_not.cpp  
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
         if (m_ptrDoc) {  
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
 [ptr::operator bool](../dotnet/ptr-operator-bool.md)