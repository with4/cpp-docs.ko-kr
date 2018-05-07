---
title: ptr::operator-&gt; | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr.com.ptr.operator->
- ptr.operator->
- ptr::operator->
- msclr::com::ptr::operator->
dev_langs:
- C++
helpviewer_keywords:
- ptr::operator->
ms.assetid: e752b549-74ed-430d-9a60-6c8e0e441998
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 6f18329bc7d3e1d3e76074e9fdb20c7f6dbe10c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ptroperator-gt"></a>ptr::operator-&gt;
멤버 액세스 연산자를 소유 하는 COM 개체에서 메서드를 호출 하는 데 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
_detail::smart_com_ptr<_interface_type> operator->();  
```  
  
## <a name="return-value"></a>반환 값  
 A `smart_com_ptr` COM 개체에 있습니다.  
  
## <a name="exceptions"></a>예외  
 내부적으로 `QueryInterface` 소유한 COM 개체 및 모든 오류를 호출할 `HRESULT` 여 예외로 변환 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A>합니다.  
  
## <a name="remarks"></a>설명  
 이 연산자를 사용 하면 소유한 COM 개체의 메서드를 호출할 수 있습니다. 임시 반환 `smart_com_ptr` 자동으로 처리 하는 자체 `AddRef` 및 `Release`합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. `WriteDocument` 사용 하 여 함수 `operator->` 호출 하 여 `get_firstChild` 문서 개체의 멤버입니다.  
  
```  
// comptr_op_member.cpp  
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
  
   // add a reference to and return the COM object  
   // but keep an internal reference to the object  
   IXMLDOMDocument* GetDocument() {  
      return m_ptrDoc.GetInterface();  
   }  
  
   // simplified function that only writes the first node  
   void WriteDocument() {  
      IXMLDOMNode* pNode = NULL;  
      BSTR bstr = NULL;  
  
      try {  
         // use operator -> to call XML Doc member  
         Marshal::ThrowExceptionForHR(m_ptrDoc->get_firstChild(&pNode));  
         if (NULL != pNode) {  
            // write out the xml  
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
      }  
      finally {  
         if (NULL != pNode) {  
            pNode->Release();  
         }  
         ::SysFreeString(bstr);  
      }  
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
      pDoc = doc.GetDocument();  
      // use unmanaged function and raw object to load xml  
      Marshal::ThrowExceptionForHR(LoadXml(pDoc, bstrXml));  
      // release reference to document object (but ref class still references it)  
      pDoc->Release();  
      pDoc = NULL;  
  
      // call another function on the ref class  
      doc.WriteDocument();  
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
  
```Output  
<word>persnickety</word>  
```  
  
## <a name="requirements"></a>요구 사항  
 **헤더 파일** \<msclr\com\ptr.h >  
  
 **Namespace** msclr:: com  
  
## <a name="see-also"></a>참고 항목  
 [ptr 멤버](../dotnet/ptr-members.md)