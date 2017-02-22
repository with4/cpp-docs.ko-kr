---
title: "com::ptr 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "com::ptr"
  - "msclr::com::ptr"
  - "msclr.com.ptr"
  - "com.ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ptr 클래스"
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# com::ptr 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

CLR 클래스의 멤버로 사용할 수 있는 COM 개체에 대 한 래퍼.  또한 래퍼 소멸자가 호출 될 때 개체의 참조를 모두 소유를 해제 하는 COM 개체의 수명 관리를 자동화 합니다.  유사한 [CComPtr Class](../atl/reference/ccomptr-class.md).  
  
## 구문  
  
```  
template<class _interface_type>  
ref class ptr;  
```  
  
#### 매개 변수  
 `_interface_type`  
 COM 인터페이스  
  
## 설명  
 A  `com::ptr`  는 함수의 지역 변수로 COM의 다양 한 작업을 단순화 하 고 수명 관리를 자동화할 수 있습니다.  
  
 A  `com::ptr`  ; 함수 매개 변수로 직접 사용할 수 없습니다. 대신 [Tracking Reference Operator](../windows/tracking-reference-operator-cpp-component-extensions.md) or a [개체 연산자에 대한 핸들\(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) 사용하세요.  
  
 A  `com::ptr`  ; 함수에서 직접 반환할 수 없습니다 대신 핸들을 사용 합니다.  
  
## 예제  
 이 이때 사용 하는 CLR 클래스를 구현 하는  `com::ptr`  의 전용 멤버를  `IXMLDOMDocument`  개체입니다.  포함 된에 대 한 호출 결과 클래스의 공용 메서드를 호출 합니다.  `IXMLDOMDocument`  개체입니다.  샘플 몇 가지 간단한 xml 입력을 단순화 된 워크 인쇄 콘솔에 XML 문서 구문 분석된 트리 노드를 XML 문서 인스턴스를 만듭니다.  
  
```  
// comptr.cpp  
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
         // load some XML into the document  
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
  
   // simplified function to write just the first xml node to the console  
   void WriteXml() {  
      IXMLDOMNode* pNode = NULL;  
  
      try {  
         // the first child of the document is the first real xml node  
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));  
         if (NULL != pNode) {  
            WriteNode(pNode);  
         }  
      }  
      finally {  
         if (NULL != pNode) {  
            pNode->Release();  
         }  
      }  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   // simplified function that only writes the node  
   void WriteNode(IXMLDOMNode* pNode) {  
      BSTR bstr = NULL;  
  
      try {  
         // write out the name and text properties  
         Marshal::ThrowExceptionForHR(pNode->get_nodeName(&bstr));  
         String^ strName = gcnew String(bstr);  
         Console::Write("<{0}>", strName);  
         ::SysFreeString(bstr);  
         bstr = NULL;  
  
         Marshal::ThrowExceptionForHR(pNode->get_text(&bstr));  
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
      doc.WriteXml();  
   }  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
}  
```  
  
  **\<단어\>주의\<\/단어\>**   
## 요구 사항  
 **헤더 파일** \<msclr\\com\\ptr.h\>  
  
 **네임 스페이스** msclr::com  
  
## 참고 항목  
 [C\+\+ 지원 라이브러리](../dotnet/cpp-support-library.md)   
 [ptr 멤버](../dotnet/ptr-members.md)