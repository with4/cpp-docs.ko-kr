---
title: "com:: ptr 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- com::ptr
- msclr::com::ptr
- msclr.com.ptr
- com.ptr
dev_langs:
- C++
helpviewer_keywords:
- ptr class
ms.assetid: 0144d0e4-919c-45f9-a3f8-fbc9edba32bf
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ae02518b60190dd129443f00d82b377317c816b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="comptr-class"></a>com::ptr 클래스
CLR 클래스의 멤버로 사용할 수 있는 COM 개체에 대한 래퍼입니다.  이 래퍼는 또한 COM 개체의 수명 주기 관리를 자동화하여 소멸자가 호출될 때 개체에서 모든 소유 참조를 해제합니다. 유사 [CComPtr 클래스](../atl/reference/ccomptr-class.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<class _interface_type>  
ref class ptr;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `_interface_type`  
 COM 인터페이스.  
  
## <a name="remarks"></a>설명  
 또한 `com::ptr`은 로컬 함수 변수로 사용하여 여러 COM 작업을 간소화하고 수명 주기 관리를 자동화할 수 있습니다.  
  
 A `com::ptr` 함수 매개 변수로 직접 사용할 수 없습니다; 사용 된 [추적 참조 연산자](../windows/tracking-reference-operator-cpp-component-extensions.md) 또는 [개체 연산자 (^)에 대 한 핸들](../windows/handle-to-object-operator-hat-cpp-component-extensions.md) 대신 합니다.  
  
 `com::ptr`은 함수로부터 직접 반환될 수 없습니다. 대신 핸들을 사용하십시오.  
  
## <a name="example"></a>예  
 이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다.  클래스의 공용 메서드를 호출하면 포함된 `IXMLDOMDocument` 개체가 호출됩니다.  이 샘플은 XML 문서의 인스턴스를 만들고, 여기에 일부 간단한 XML을 채우고, 구문 분석된 문서 트리에서 간소화된 노드 작업을 수행하고 XML을 콘솔에 출력합니다.  
  
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
  
```Output  
<word>persnickety</word>  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더 파일** \<msclr\com\ptr.h >  
  
 **Namespace** msclr:: com  
  
## <a name="see-also"></a>참고 항목  
 [C + + 지원 라이브러리](../dotnet/cpp-support-library.md)   
 [ptr 멤버](../dotnet/ptr-members.md)