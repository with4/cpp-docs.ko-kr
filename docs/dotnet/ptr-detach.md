---
title: ptr::Detach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- ptr.Detach
- msclr.com.ptr.Detach
- ptr::Detach
- msclr::com::ptr::Detach
dev_langs:
- C++
helpviewer_keywords:
- ptr::Detach
ms.assetid: 23370c8a-8f79-4880-9fa1-46e110c1a92c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 24e5c71a20b3bffebd9cd25bf2795fd309491d11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33161449"
---
# <a name="ptrdetach"></a>ptr::Detach
개체에 대 한 포인터를 반환 하는 COM 개체의 소유권을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
_interface_type * Detach();  
```  
  
## <a name="return-value"></a>반환 값  
 COM 개체에 대 한 포인터입니다.  
  
 개체가 소유 하는 경우에 NULL이 반환 됩니다.  
  
## <a name="exceptions"></a>예외  
 내부적으로 `QueryInterface` 소유한 COM 개체 및 모든 오류를 호출할 `HRESULT` 여 예외로 변환 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>합니다.  
  
## <a name="remarks"></a>설명  
 `Detach` 먼저 호출자를 대신 하 여 COM 개체에 대 한 참조를 추가 하 고 다음가 소유 하는 모든 참조를 해제는 `com::ptr`합니다.  호출자에 게 반환된 된 개체를 소멸 시킵니다 해제 궁극적으로 해야 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다.  `DetachDocument` 멤버 함수 호출 `Detach` COM 개체의 소유권을 호출자에 대 한 포인터를 반환 합니다.  
  
```  
// comptr_detach.cpp  
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
  
   // detach the COM object and return it  
   // this releases the internal reference to the object  
   IXMLDOMDocument* DetachDocument() {  
      return m_ptrDoc.Detach();  
   }  
  
   // note that the destructor will call the com::ptr destructor  
   // and automatically release the reference to the COM object  
  
private:  
   com::ptr<IXMLDOMDocument> m_ptrDoc;  
};  
  
// unmanaged function that loads XML into a raw XML DOM Document object  
HRESULT LoadXml(IXMLDOMDocument* pDoc, BSTR bstrXml) {  
   HRESULT hr = S_OK;  
   VARIANT_BOOL bSuccess;  
   hr = pDoc->loadXML(bstrXml, &bSuccess);  
   if (S_OK == hr && !bSuccess) {  
      hr = E_FAIL;  
   }  
   return hr;  
}  
  
// use the ref class to handle an XML DOM Document object  
int main() {  
   IXMLDOMDocument* pDoc = NULL;  
   BSTR bstrXml = NULL;  
  
   try {  
      // create the class from a progid string  
      XmlDocument doc("Msxml2.DOMDocument.3.0");  
  
      bstrXml = ::SysAllocString(L"<word>persnickety</word>");  
      if (NULL == bstrXml) {  
         throw gcnew OutOfMemoryException("bstrXml");  
      }  
      // detach the document object from the ref class  
      pDoc = doc.DetachDocument();  
      // use unmanaged function and raw object to load xml  
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));  
      // release document object as the ref class no longer owns it  
      pDoc->Release();  
      pDoc = NULL;  
   }  
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
 [ptr::Release](../dotnet/ptr-release.md)   
 [ptr::Attach](../dotnet/ptr-attach.md)