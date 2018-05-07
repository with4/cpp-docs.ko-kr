---
title: ptr::ptr | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- ptr::ptr
- ptr.ptr
- msclr.com.ptr.ptr
- msclr::com::ptr::ptr
dev_langs:
- C++
helpviewer_keywords:
- ptr::ptr
ms.assetid: 4f5883b4-7c0a-46c6-aa9f-4e49eed463eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0cd8b4a4a1140a1a34e0148756cdb23b2f8069cc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ptrptr"></a>ptr::ptr
생성 한 `com::ptr` 를 래핑하는 COM 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
ptr();  
ptr(  
   _interface_type * p  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `P`  
 COM 인터페이스 포인터.  
  
## <a name="remarks"></a>설명  
 인수 없는 생성자 할당 `nullptr` 기본 개체 핸들을 합니다. 에 대 한 후속 호출에서 `com::ptr` 내부 개체의 유효성을 검사 하 고 자동으로 개체를 실제로 만들거나 연결 될 때까지 실패 합니다.  
  
 단일 인수 생성자를 사용 하는 COM 개체에 대 한 참조를 추가 하지만 호출자에 게 호출 해야 하므로 호출자의 참조를 해제 하지 않습니다 `Release` 진정으로 컨트롤을 제공 하는 COM 개체에서 합니다. 경우는 `com::ptr`의 소멸자가 호출 되는 COM 개체의 참조를 자동으로 해제 됩니다.  
  
 전달 `NULL` 이 생성자에 인수가 없는 버전을 호출 하는 것과 같습니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. 생성자의 두 버전의 사용을 보여 줍니다.  
  
```  
// comptr_ptr.cpp  
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
  
   // construct the internal com::ptr with a COM object  
   XmlDocument(IXMLDOMDocument* pDoc) : m_ptrDoc(pDoc) {}  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   IXMLDOMDocument* pDoc = NULL;  
  
   try {  
      // create an XML DOM document object  
      Marshal::ThrowExceptionForHR(CoCreateInstance(CLSID_DOMDocument30, NULL,   
         CLSCTX_ALL, IID_IXMLDOMDocument, (void**)&pDoc));  
      // construct the ref class with the COM object  
      XmlDocument doc1(pDoc);  
  
      // or create the class from a progid string  
      XmlDocument doc2("Msxml2.DOMDocument.3.0");  
   }  
   // doc1 and doc2 destructors are called when they go out of scope  
   // and the internal com::ptr releases its reference to the COM object  
   catch (Exception^ e) {  
      Console::WriteLine(e);     
   }  
   finally {  
      if (NULL != pDoc) {  
         pDoc->Release();        
      }  
   }  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더 파일** \<msclr\com\ptr.h >  
  
 **Namespace** msclr:: com  
  
## <a name="see-also"></a>참고 항목  
 [ptr 멤버](../dotnet/ptr-members.md)   
 [ptr::CreateInstance](../dotnet/ptr-createinstance.md)   
 [ptr::~ptr](../dotnet/ptr-tilde-ptr.md)