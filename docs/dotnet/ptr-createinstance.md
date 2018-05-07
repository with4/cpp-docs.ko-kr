---
title: ptr::CreateInstance | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- ptr.CreateInstance
- msclr::com::ptr::CreateInstance
- msclr.com.ptr.CreateInstance
- ptr::CreateInstance
dev_langs:
- C++
helpviewer_keywords:
- ptr::CreateInstance
ms.assetid: 9e8e4c4c-1651-4839-8829-5857d74470fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dd4ba56b92150046b986f2b101f6a004c114bf28
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ptrcreateinstance"></a>ptr::CreateInstance
내에서 COM 개체의 인스턴스를 만듭니다는 `com::ptr`합니다.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `progid`  
 `ProgID` 문자열입니다.  
  
 `pouter`  
 집계 개체의 IUnknown 인터페이스 (controlling IUnknown)에 대 한 포인터입니다. 경우 `pouter` 를 지정 하지 않으면 `NULL` 사용 됩니다.  
  
 `cls_context`  
 새로 만든된 개체를 관리 하는 코드가 실행 되는 컨텍스트. 값에서 가져옵니다는 `CLSCTX` 열거형입니다. 경우 `cls_context` 을 지정 하지 않으면 CLSCTX_ALL 사용 되는 값입니다.  
  
 `rclsid`  
 `CLSID` 데이터 및 개체를 만드는 사용할 수 있는 코드와 연결 합니다.  
  
## <a name="exceptions"></a>예외  
 경우는 `com::ptr` COM 개체에 대 한 참조를 이미 소유한 `CreateInstance` throw <xref:System.InvalidOperationException>합니다.  
  
 이 함수 호출 `CoCreateInstance` 사용 하 여 <xref:System.Runtime.InteropServices.Marshal.ThrowExceptionForHR%2A> 오류 변환할 `HRESULT` 적절 한 예외를 합니다.  
  
## <a name="remarks"></a>설명  
 `CreateInstance` 사용 하 여 `CoCreateInstance` ProgID 또는 CLSID에서 식별 된 지정된 된 개체의 새 인스턴스를 만듭니다. `com::ptr` 새로 만든된 개체를 참조 하 고는 자동으로 소멸 시 모든 소유 참조를 해제 합니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 `com::ptr`을 사용해서 해당 개인 멤버 `IXMLDOMDocument` 개체를 래핑하는 CLR 클래스를 구현합니다. 클래스 생성자의 두 가지 다른 형식이 사용 `CreateInstance` ProgID 또는 CLSID는 CLSCTX에서 문서 개체를 만들려고 합니다.  
  
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
  
## <a name="requirements"></a>요구 사항  
 **헤더 파일** \<msclr\com\ptr.h >  
  
 **Namespace** msclr:: com  
  
## <a name="see-also"></a>참고 항목  
 [ptr 멤버](../dotnet/ptr-members.md)