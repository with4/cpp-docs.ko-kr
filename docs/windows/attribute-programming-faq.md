---
title: "Attribute Programming FAQ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributed programming"
  - "attributes [C++], frequently asked questions"
  - "FAQs (frequently asked questions), attributed programming [C++]"
ms.assetid: a1b8349f-7f51-43c4-95ea-4edb6e5f243f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Attribute Programming FAQ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 다음에 대 한 질문과 대답 합니다.  
  
-   [HRESULT는 무엇입니까?](#vcconattributeprogrammmingfaqanchor1)  
  
-   [특성의 매개 변수 이름을 지정할 수 있는 경우](#vcconattributeprogrammmingfaqanchor2)  
  
-   [의견을 특성 블록에서 사용할 수 있습니까?](#vcconattributeprogrammmingfaqanchor3)  
  
-   [특성이 상속과 상호 작용 하는 방법](#vcconattributeprogrammmingfaqanchor4)  
  
-   [특성된 ATL 프로젝트에서 특성을 사용 하려면 어떻게 해야 합니까?](#vcconattributeprogrammmingfaqanchor5)  
  
-   [특성 사용된 프로젝트에서.idl 파일을 어떻게 사용할 수 있습니까?](#vcconattributeprogrammmingfaqanchor6)  
  
-   [특성에 의해 삽입 된 코드를 수정할 수 있습니까?](#vcconattributeprogrammmingfaqanchor7)  
  
-   [어떻게 앞으로 특성 사용된 인터페이스를 선언할 수 있습니다.](#vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface)  
  
-   [특성에서는 특성을 사용 하는 클래스에서 파생 된 클래스에 사용할 수 있습니까?](#vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor)  
  
##  <a name="vcconattributeprogrammmingfaqanchor1"></a> HRESULT는 무엇입니까?  
 `HRESULT` 자주 반환 값으로 특성 및 ATL에서 일반적 사용 하는 단순 데이터 형식입니다.  다음 표에서 다양 한 값에 설명합니다.  더 많은 값을 헤더 파일이 아니라 winerror.h에 포함 되어 있습니다.  
  
|Name|설명|값|  
|----------|--------|-------|  
|S\_OK|작업 성공|0x00000000|  
|E\_UNEXPECTED|예기치 않은 오류|0x8000ffff는|  
|E\_NOTIMPL|구현 되지 않음|0x80004001|  
|E\_OUTOFMEMORY|필요한 메모리를 할당 하지 못했습니다.|0x8007000E|  
|E\_INVALIDARG|하나 이상의 인수가 잘못 되었습니다.|0x80070057|  
|E\_NOINTERFACE|지원 되지 않는 인터페이스|0x80004002|  
|E\_POINTER|잘못 된 포인터|0x80004003|  
|E\_HANDLE|잘못 된 핸들|0x80070006|  
|E\_ABORT|작업이 중단 되었습니다|0x80004004|  
|E\_FAIL|지정 되지 않은 오류|0x80004005|  
|이 실패|일반 액세스 거부 오류|0x80070005|  
  
##  <a name="vcconattributeprogrammmingfaqanchor2"></a> 특성의 매개 변수 이름을 지정할 수 있는 경우  
 단일 매개 변수는 특성이 있을 경우 대부분의 경우 해당 매개 변수 라고 합니다.  이 이름은 특성을 코드에 삽입 하는 경우 필요 하지 않습니다.  예를 들어, 다음 사용에 있는  [집계 가능한](../windows/aggregatable.md) 특성:  
  
```  
[coclass, aggregatable(value=allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 정확 하 게 동일 합니다.  
  
```  
[coclass, aggregatable(allowed)]  
class CMyClass  
{  
// The class declaration  
};  
```  
  
 그러나 다음과 같은 특성이 단일, 명명 되지 않은 매개 변수가 있습니다.  
  
||||  
|-|-|-|  
|[call\_as](../windows/call-as.md)|[case](../windows/case-cpp.md)|[cpp\_quote](../windows/cpp-quote.md)|  
|[default](../windows/default-cpp.md)|[defaultvalue](../windows/defaultvalue.md)|[defaultvtable](../windows/defaultvtable.md)|  
|[emitidl](../windows/emitidl.md)|[항목](../windows/entry.md)|[first\_is](../windows/first-is.md)|  
|[HelpContext](../windows/helpcontext.md)|[도움말 파일](../windows/helpfile.md)|[helpstring](../windows/helpstring.md)|  
|[helpstringcontext](../windows/helpstringcontext.md)|[helpstringdll](../windows/helpstringdll.md)|[id](../windows/id.md)|  
|[iid\_is](../windows/iid-is.md)|[import](../windows/import.md)|[importlib](../windows/importlib.md)|  
|[포함](../windows/include-cpp.md)|[includelib](../windows/includelib-cpp.md)|[last\_is](../windows/last-is.md)|  
|[length\_is](../windows/length-is.md)|[max\_is](../windows/max-is.md)|[no\_injected\_text](../windows/no-injected-text.md)|  
|[pointer\_default](../windows/pointer-default.md)|[pragma](../windows/pragma.md)|[restricted](../windows/restricted.md)|  
|[size\_is](../windows/size-is.md)|[source](../windows/source-cpp.md)|[switch\_is](../windows/switch-is.md)|  
|[switch\_type](../windows/switch-type.md)|[transmit\_as](../windows/transmit-as.md)|[wire\_marshal](../windows/wire-marshal.md)|  
  
##  <a name="vcconattributeprogrammmingfaqanchor3"></a> 의견을 특성 블록에서 사용할 수 있습니까?  
 한 줄 및 여러 줄을 모두 주석 특성 블록 내에서 사용할 수 있습니다.  그러나 속성을 사용 하는 매개 변수를 보유 하는 괄호 안에 메모의 두 스타일 중 하나를 사용할 수 없습니다.  
  
 다음 허용 됩니다.  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1"), /* Multiple-line  
                                       comment */  
   threading("both") // Single-line comment  
]  
```  
  
 다음 허용 됩니다.  
  
```  
[ coclass,  
   progid("MyClass.CMyClass.1" /* Multiple-line comment */ ),  
   threading("both" // Single-line comment)  
]  
```  
  
##  <a name="vcconattributeprogrammmingfaqanchor4"></a> 특성이 상속과 상호 작용 하는 방법  
 특성 사용 및 해결 되지 않은 클래스 자체 또는 않는 볼 수 있습니다 다른 클래스 로부터 상속할 수 있습니다.  가 특성 사용된 클래스에서 파생 한 결과 특성 공급자가 해당 코드를 변환한 후 해당 클래스에서 파생 시키는 것입니다.  특성은 C\+\+ 상속을 통해 클래스를 파생 하도록 전송 되지 않습니다.  특성 공급자만 코드의 특성으로 변환합니다.  
  
##  <a name="vcconattributeprogrammmingfaqanchor5"></a> 특성된 ATL 프로젝트에서 특성을 사용 하려면 어떻게 해야 합니까?  
 .Idl 파일이 있는 특성된 ATL 프로젝트에 있을 수 있습니다 한 특성된 개체를 추가 할 수 있습니다.  이 경우 클래스 추가 마법사를 사용 하는 코드를 제공 합니다.  
  
##  <a name="vcconattributeprogrammmingfaqanchor6"></a> 특성 사용된 프로젝트에서.idl 파일을 어떻게 사용할 수 있습니까?  
 특성을 사용 하는 ATL 프로젝트에 사용 하려는.idl 파일이 있을 수 있습니다.  사용 합니다이 경우에  [importidl](../windows/importidl.md) 특성,.idl 파일의.h 파일을 컴파일할 \(참조 하십시오의  [MIDL 속성 페이지](../ide/midl-property-pages.md) 프로젝트의 속성 페이지 대화 상자에서\), 다음 프로젝트의.h 파일을 포함 합니다.  
  
##  <a name="vcconattributeprogrammmingfaqanchor7"></a> 특성에 의해 삽입 된 코드를 수정할 수 있습니까?  
 일부 특성은 프로젝트에 코드를 삽입 합니다.  사용 하 여 삽입 된 코드를 볼 수 있는  [\/Fx](../build/reference/fx-merge-injected-code.md) 컴파일러 옵션.  삽입 된 파일에서 코드를 복사 하 고 소스 코드에 붙여넣을 수 있습니다.  이 특성의 동작을 수정할 수 있습니다.  그러나, 함께 사용자 코드의 다른 부분을 수정 해야 합니다.  
  
 다음 샘플의 소스 코드 파일에 삽입 된 코드를 복사 결과입니다.  
  
```  
// attr_injected.cpp  
// compile with: comsupp.lib  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[ module(name="MyLibrary") ];  
  
// ITestTest  
[   
   object,  
   uuid("DADECE00-0FD2-46F1-BFD3-6A0579CA1BC4"),  
   dual,  
   helpstring("ITestTest Interface"),  
   pointer_default(unique)  
]  
  
__interface ITestTest : IDispatch {  
   [id(1), helpstring("method DoTest")]   
   HRESULT DoTest([in] BSTR str);  
};  
  
// _ITestTestEvents  
[  
   uuid("12753B9F-DEF4-49b0-9D52-A79C371F2909"),  
   dispinterface,  
   helpstring("_ITestTestEvents Interface")  
]  
  
__interface _ITestTestEvents {  
   [id(1), helpstring("method BeforeChange")] HRESULT BeforeChange([in] BSTR str, [in,out] VARIANT_BOOL* bCancel);  
};  
  
// CTestTest  
[  
   coclass,  
   threading(apartment),  
   vi_progid("TestATL1.TestTest"),  
   progid("TestATL1.TestTest.1"),  
   version(1.0),  
   uuid("D9632007-14FA-4679-9E1C-28C9A949E784"),  
   // this line would be commented out from original file  
   // event_source("com"),  
   // this line would be added to support injected code  
   source(_ITestTestEvents),  
   helpstring("TestTest Class")  
]  
  
class ATL_NO_VTABLE CTestTest : public ITestTest,  
// the following base classes support added injected code  
public IConnectionPointContainerImpl<CTestTest>,  
public IConnectionPointImpl<CTestTest, &__uuidof(::_ITestTestEvents), CComDynamicUnkArray>  
{  
public:  
   CTestTest() {  
   }  
   // this line would be commented out from original file  
   // __event __interface _ITestTestEvents;  
   DECLARE_PROTECT_FINAL_CONSTRUCT()  
   HRESULT FinalConstruct() {  
      return S_OK;  
   }  
  
void FinalRelease() {}  
  
public:  
   CComBSTR m_value;  
   STDMETHOD(DoTest)(BSTR str) {  
      VARIANT_BOOL bCancel = FALSE;  
      BeforeChange(str,&bCancel);  
      if (bCancel) {  
          return Error("Error : Someone don't want us to change the value");  
      }  
  
     m_value =str;  
     return S_OK;  
    }  
// the following was copied in from the injected code.  
HRESULT BeforeChange(::BSTR i1,::VARIANT_BOOL* i2) {  
   HRESULT hr = S_OK;  
   IConnectionPointImpl<CTestTest, &__uuidof(_ITestTestEvents), CComDynamicUnkArray>* p = this;  
   VARIANT rgvars[2];  
   Lock();  
   IUnknown** pp = p->m_vec.begin();  
   Unlock();  
   while (pp < p->m_vec.end()) {  
      if (*pp != NULL) {  
         IDispatch* pDispatch = (IDispatch*) *pp;  
         ::VariantInit(&rgvars[1]);  
         rgvars[1].vt = VT_BSTR;  
         V_BSTR(&rgvars[1])= (BSTR) i1;  
         ::VariantInit(&rgvars[0]);  
         rgvars[0].vt = (VT_BOOL | VT_BYREF);  
         V_BOOLREF(&rgvars[0])= (VARIANT_BOOL*) i2;  
         DISPPARAMS disp = { rgvars, NULL, 2, 0 };  
         VARIANT ret_val;  
         hr = __ComInvokeEventHandler(pDispatch, 1, 1, &disp, &ret_val);  
         if (FAILED(hr))  
            break;  
      }  
      pp++;  
   }  
   return hr;  
}  
  
BEGIN_CONNECTION_POINT_MAP(CTestTest)  
CONNECTION_POINT_ENTRY(__uuidof(::_ITestTestEvents))  
END_CONNECTION_POINT_MAP()  
// end added code section  
  
// _ITestCtrlEvents Methods  
public:  
};  
  
int main() {}  
```  
  
##  <a name="vcconattributeprogrammmingfaqhowcaniforwarddeclareanattributedinterface"></a> 어떻게 앞으로 특성 사용된 인터페이스를 선언할 수 있습니다.  
 특성 사용된 인터페이스의 정방향 선언 하는 경우 실제 인터페이스 선언에 적용 하는 전방 선언에 동일한 특성을 적용 해야 합니다.  또한 적용 해야는 [export](../windows/export.md) 에 전방 선언에 특성.  
  
##  <a name="vcconcaniuseattributesonclassderivedfromclassthatalsousesattributesanchor"></a> 특성에서는 특성을 사용 하는 클래스에서 파생 된 클래스에 사용할 수 있습니까?  
 또한 특성을 사용 하는 클래스에서 파생 된 클래스에 특성을 사용 하 여 아니오, 지원 되지 않습니다.  
  
## 참고 항목  
 [Concepts](../windows/attributed-programming-concepts.md)