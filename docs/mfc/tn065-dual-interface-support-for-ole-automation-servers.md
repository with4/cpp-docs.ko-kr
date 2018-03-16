---
title: "TN065: OLE 자동화 서버에 대 한 이중 인터페이스 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.ole
dev_langs:
- C++
helpviewer_keywords:
- dual interfaces [MFC], OLE Automation
- TN065 [MFC]
- ACDUAL sample [MFC]
- Automation servers [MFC], dual-interface support
ms.assetid: b5c8ed09-2f7f-483c-80fc-2a47ad896063
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 959938be27e66a765ee0ae9e5aef9b3c1f1aed6f
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/16/2018
---
# <a name="tn065-dual-interface-support-for-ole-automation-servers"></a>TN065: OLE 자동화 서버에 대한 이중 인터페이스 지원
> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다. 따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다. 최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 이 노트에서는 MFC 기반 OLE 자동화 서버 응용 프로그램에 이중 인터페이스를 추가 하는 방법을 설명 합니다. [ACDUAL](../visual-cpp-samples.md) 예제에서는 이중 인터페이스 지원 및 ACDUAL에서이 정보에 예제 코드를 가져옵니다. 와 같은이 참고에 설명 된 매크로 `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, 및 `IMPLEMENT_DUAL_ERRORINFO`ACDUAL 샘플의 일부 이며 MFCDUAL에서 확인할 수 있습니다. 8.  
  
## <a name="dual-interfaces"></a>이중 인터페이스  
 OLE 자동화를 사용 하면 구현할 수 있지만 `IDispatch` 인터페이스, VTBL 인터페이스 또는 이중 인터페이스 (포괄 하는 둘 다), 표시 된 모든 OLE 자동화 개체에 대 한 이중 인터페이스를 구현 하는 적극 권장 합니다. 이중 인터페이스를 통해 중요 한 이점이 `IDispatch`-유일한 또는 VTBL 전용 인터페이스:  
  
-   바인딩 VTBL 인터페이스를 통해 컴파일 시 또는 런타임에 통해 수행 될 수 `IDispatch`합니다.  
  
-   VTBL 인터페이스를 사용할 수 있는 OLE 자동화 컨트롤러에서 향상 된 성능 이점을 얻을 수 있습니다.  
  
-   사용 하는 기존 OLE 자동화 컨트롤러는 `IDispatch` 인터페이스는 계속 작동 합니다.  
  
-   VTBL 인터페이스는 c + +에서 호출할 수 있습니다.  
  
-   이중 인터페이스는 Visual Basic 개체 지원 기능에 대 한 호환성을 위해 필요 합니다.  
  
## <a name="adding-dual-interface-support-to-a-ccmdtarget-based-class"></a>CCmdTarget 기반 클래스에 이중 인터페이스 지원 추가  
 이중 인터페이스에서 파생 된 사용자 지정 인터페이스 실제로 `IDispatch`합니다. 이중 인터페이스 지원에서 구현 하는 가장 간단한 방법은 `CCmdTarget`-정상적인 디스패치 MFC 및 클래스 마법사를 사용 하 여 클래스에 인터페이스 다음 나중에 사용자 지정 인터페이스를 추가 하는 첫 번째 구현에 따라 클래스는 합니다. 대부분의 경우 사용자 지정 인터페이스 구현에서 MFC에 다시 위임 단순히 `IDispatch` 구현 합니다.  
  
 첫째, 개체에 대 한 이중 인터페이스를 정의 하 여 서버에 대 한 ODL 파일을 수정 합니다. 대신에 인터페이스 문을 사용 해야 하는 이중 인터페이스를 정의 하려면는 `DISPINTERFACE` Visual c + + 마법사에서 생성 하는 문입니다. 기존 제거 하는 대신 `DISPINTERFACE` 문, 새 인터페이스 문을 추가 합니다. 유지 하 여는 `DISPINTERFACE` 폼 클래스 마법사를 사용 하 여 사용자 개체에 메서드와 속성을 추가 하려면를 계속할 수 있지만 인터페이스 문에 해당 하는 속성 및 메서드를 추가 해야 합니다.  
  
 이중 인터페이스에 대 한 인터페이스 문이 있어야는 **OLEAUTOMATION** 및 **이중** 특성과 인터페이스에서 파생 되어야 합니다 `IDispatch`합니다. 사용할 수는 [GUIDGEN](../visual-cpp-samples.md) 를 만들기 위한 샘플은 **IID** 이중 인터페이스에 대 한 합니다.  
  
```  
[ uuid(0BDD0E81-0DD7-11cf-BBA8-444553540000), // IID_IDualAClick  
    oleautomation, 
    dual 
]  
interface IDualAClick : IDispatch  
 {  
 };  
```  
  
 인터페이스 문을 위치에 있으면 메서드 및 속성에 대 한 항목을 추가 하기 시작 합니다. 이중 인터페이스에 대 한 메서드 및 이중 인터페이스의 속성 접근자 함수를 반환 하는 매개 변수 목록을 다시 정렬 해야는 `HRESULT` 특성을 가진 매개 변수로 반환 값을 전달 `[retval,out]`합니다. 속성에는 필요 합니다 모두 읽기를 추가 하려면 (`propget`) 및 쓰기 (`propput`) 동일한 id 가진 함수에 액세스 합니다. 예를 들어:  
  
```  
[propput,
    id(1)] HRESULT text([in] BSTR newText);

[propget,
    id(1)] HRESULT text([out,
    retval] BSTR* retval);
```  
  
 메서드 및 속성을 정의한 후 coclass 문에서 인터페이스에 대 한 참조를 추가 해야 합니다. 예를 들어:  
  
```  
[ uuid(4B115281-32F0-11cf-AC85-444553540000) ]  
coclass Document  
{  
    dispinterface IAClick;  
 [default] interface IDualAClick;  
};  
```  
  
 ODL 파일을 업데이트 후 MFC의 인터페이스 맵 메커니즘을 사용 하 여 개체 클래스에 이중 인터페이스에 대 한 구현 클래스를 정의 하 고 mfc의 해당 항목을 확인 하려면 `QueryInterface` 메커니즘입니다. 에 있는 하나의 항목 필요는 `INTERFACE_PART` ODL의 인터페이스 문에서 각 항목 및 디스패치 인터페이스에 대 한 항목에 대 한 블록입니다. 각 ODL 항목으로는 **propput** 특성 라는 함수가 필요 `put_propertyname`합니다. 각 항목은 **propget** 특성 라는 함수가 필요 `get_propertyname`합니다.  
  
 이중 인터페이스에 대 한 구현 클래스를 정의 하려면 추가 `DUAL_INTERFACE_PART` 개체 클래스 정의에 블록입니다. 예를 들어:  
  
```  
BEGIN_DUAL_INTERFACE_PART(DualAClick,
    IDualAClick)  
    STDMETHOD(put_text)(THIS_ BSTR newText);

    STDMETHOD(get_text)(THIS_ BSTR FAR* retval);

    STDMETHOD(put_x)(THIS_ short newX);

    STDMETHOD(get_x)(THIS_ short FAR* retval);

    STDMETHOD(put_y)(THIS_ short newY);

    STDMETHOD(get_y)(THIS_ short FAR* retval);

    STDMETHOD(put_Position)(THIS_ IDualAutoClickPoint FAR* newPosition);

    STDMETHOD(get_Position)(THIS_ IDualAutoClickPoint FAR* FAR* retval);

    STDMETHOD(RefreshWindow)(THIS);

 STDMETHOD(SetAllProps)(THIS_ short x,
    short y,
    BSTR text);

    STDMETHOD(ShowWindow)(THIS);

END_DUAL_INTERFACE_PART(DualAClick) 
```  
  
 MFC의 이중 인터페이스를 연결할 [QueryInterface](http://msdn.microsoft.com/library/windows/desktop/ms687230) 메커니즘을 추가 `INTERFACE_PART` 인터페이스 맵에 항목:  
  
```  
BEGIN_INTERFACE_MAP(CAutoClickDoc,
    CDocument)  
    INTERFACE_PART(CAutoClickDoc,
    DIID_IAClick,
    Dispatch)  
    INTERFACE_PART(CAutoClickDoc,
    IID_IDualAClick,
    DualAClick)  
END_INTERFACE_MAP()  
```  
  
 다음으로, 인터페이스의 구현을 입력 해야 합니다. 대부분의 경우 기존 MFC에 위임할 수는 `IDispatch` 구현 합니다. 예를 들어:  
  
```  
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::AddRef()  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    return pThis->ExternalAddRef();

}  
STDMETHODIMP_(ULONG) CAutoClickDoc::XDualAClick::Release()  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    return pThis->ExternalRelease();

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::QueryInterface(
    REFIID iid,
    LPVOID* ppvObj)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    return pThis->ExternalQueryInterface(&iid,
    ppvObj);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfoCount(
    UINT FAR* pctinfo)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetTypeInfoCount(pctinfo);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetTypeInfo(
    UINT itinfo,
    LCID lcid,
    ITypeInfo FAR* FAR* pptinfo)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetTypeInfo(itinfo,
    lcid,
    pptinfo);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::GetIDsOfNames(
    REFIID riid,
    OLECHAR FAR* FAR* rgszNames,
    UINT cNames,  
    LCID lcid,
    DISPID FAR* rgdispid)   
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->GetIDsOfNames(riid,
    rgszNames,
    cNames,   
    lcid,
    rgdispid);

}  
STDMETHODIMP CAutoClickDoc::XDualAClick::Invoke(
    DISPID dispidMember,
    REFIID riid,
    LCID lcid,
    WORD wFlags,  
    DISPPARAMS FAR* pdispparams,
    VARIANT FAR* pvarResult,  
    EXCEPINFO FAR* pexcepinfo,
    UINT FAR* puArgErr)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDispatch = pThis->GetIDispatch(FALSE);

    ASSERT(lpDispatch != NULL);

    return lpDispatch->Invoke(dispidMember,
    riid,
    lcid,  
    wFlags,
    pdispparams,
    pvarResult,  
    pexcepinfo,
    puArgErr);

}  
```  
  
 개체의 메서드 및 속성 접근자 함수를 구현을 입력 해야 합니다. 메서드 및 속성 함수는 클래스 마법사를 사용 하 여 생성 하는 방법에 다시 일반적으로 위임할 수 있습니다. 그러나 변수를 직접 액세스 속성을 설정 하는 경우 코드 값을 변수에 get/put를 작성 해야 합니다. 예를 들어:  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick) *// MFC automatically converts from Unicode BSTR to *// Ansi CString,
    if necessary...  
    pThis->m_str = newText;  
    return NOERROR;  
}  
STDMETHODIMP CAutoClickDoc::XDualAClick::get_text(BSTR* retval)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick) *// MFC automatically converts from Ansi CString to *// Unicode BSTR,
    if necessary...  
    pThis->m_str.SetSysString(retval);

 return NOERROR;  
}  
```  
  
## <a name="passing-dual-interface-pointers"></a>이중 인터페이스 포인터를 전달합니다.  
 이중 인터페이스 포인터에 전달 되지를 호출 해야 하는 경우에 특히 간단 `CCmdTarget::FromIDispatch`합니다. `FromIDispatch` MFC의에 대해서만 작동 `IDispatch` 포인터입니다. 이 해결 하는 한 가지 방법은 원본에 대 한 쿼리를 `IDispatch` 포인터 MFC에 의해 집합과 해당 포인터를 필요로 하는 함수에 전달 합니다. 예를 들어:  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_Position(
    IDualAutoClickPoint FAR* newPosition)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDisp = NULL;  
    newPosition->QueryInterface(IID_IDispatch, (LPVOID*)&lpDisp);

    pThis->SetPosition(lpDisp);

 lpDisp->Release();
return NOERROR;  
}  
```  
  
 이중 인터페이스 메서드를 통해 다시 포인터를 전달 하기 전에 MFC에서 변환 해야 할 수 있습니다 `IDispatch` 이중 인터페이스 포인터에 대 한 포인터입니다. 예:  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::get_Position(
    IDualAutoClickPoint FAR* FAR* retval)  
{  
    METHOD_PROLOGUE(CAutoClickDoc,
    DualAClick)  
    LPDISPATCH lpDisp;  
    lpDisp = pThis->GetPosition();
lpDisp->QueryInterface(IID_IDualAutoClickPoint, (LPVOID*)retval);

    return NOERROR;  
}  
```  
  
## <a name="registering-the-applications-type-library"></a>응용 프로그램의 형식 라이브러리를 등록 하는 중  
 응용 프로그램 마법사는 시스템에는 OLE 자동화 서버 응용 프로그램의 형식 라이브러리를 등록 하는 코드를 생성 하지 않습니다. 형식 라이브러리를 등록 하는 다른 방법의 있을 때는 응용 프로그램을 업데이트 OLE 형식 정보, 즉, 응용 프로그램은 독립 실행형 실행 될 때마다 때 형식 라이브러리를 등록 하는 것입니다.  
  
 등록 하는 응용 프로그램이 실행 될 때마다 응용 프로그램의 형식 라이브러리 독립 실행형:  
  
-   AFXCTL 포함 됩니다. 표준 프로그램에 H STDAFX 헤더 파일에 포함 되어 있습니다. H의 정의 액세스 하는 `AfxOleRegisterTypeLib` 함수입니다.  
  
-   응용 프로그램에서 `InitInstance` 함수를 호출을 찾습니다 `COleObjectFactory::UpdateRegistryAll`합니다. 이 호출 다음에 대 한 호출을 추가 `AfxOleRegisterTypeLib`을 지정 하는 **LIBID** 에 형식 라이브러리로 형식 라이브러리의 이름과 함께 해당:  
  
 ' ' * / 서버 응용 프로그램을 독립 실행형 시작 되는 것이 좋습니다 / * / / 손상 된 경우 시스템 레지스트리를 업데이트 합니다.  
    m_server.UpdateRegistry(OAT_DISPATCH_OBJECT);

 COleObjectFactory::UpdateRegistryAll(); * / / DUAL_SUPPORT_START * / / 형식 라이브러리가 등록 되어 있거나 이중 인터페이스 작동 하지 않습니다 있는지 확인 합니다.  
AfxOleRegisterTypeLib(AfxGetInstanceHandle(), LIBID_ACDual, _T("AutoClik.TLB")); *// DUAL_SUPPORT_END  
 ```  
  
## Modifying Project Build Settings to Accommodate Type Library Changes  
 To modify a project's build settings so that a header file containing **UUID** definitions is generated by MkTypLib whenever the type library is rebuilt:  
  
1.  On the **Build** menu, click **Settings**, and then select the ODL file from the file list for each configuration.  
  
2.  Click the **OLE Types** tab and specify a filename in the **Output header** filename field. Use a filename that is not already used by your project, because MkTypLib will overwrite any existing file. Click **OK** to close the **Build Settings** dialog box.  
  
 To add the **UUID** definitions from the MkTypLib-generated header file to your project:  
  
1.  Include the MkTypLib-generated header file in your standard includes header file, STDAFX.H.  
  
2.  Create a new file, INITIIDS.CPP, and add it to your project. In this file, include your MkTypLib-generated header file after including OLE2.H and INITGUID.H:  
  
 ```  
    initIIDs.c: 이중 인터페이스의 Iid를 정의 합니다.  
    미리 컴파일된 헤더와 하지 구축 해야 합니다.  
      #<a name="include-ole2h"></a>< ole2.h >를 포함 합니다.  
      #<a name="include-initguidh"></a>< d. h >를 포함 합니다.  
      #<a name="include-acdualh"></a>include "acdual.h"  
 ```  
  
3.  On the **Build** menu, click **Settings**, and then select INITIIDS.CPP from the file list for each configuration.  
  
4.  Click the **C++** tab, click category **Precompiled Headers**, and select the **Not using precompiled headers** radio button. Click OK to close the **Build Settings** dialog box.  
  
## Specifying the Correct Object Class Name in the Type Library  
 The wizards shipped with Visual C++ incorrectly use the implementation class name to specify the coclass in the server's ODL file for OLE-creatable classes. While this will work, the implementation class name is probably not the class name you want users of your object to use. To specify the correct name, open the ODL file, locate each coclass statement, and replace the implementation class name with the correct external name.  
  
 Note that when the coclass statement is changed, the variable names of **CLSID**s in the MkTypLib-generated header file will change accordingly. You will need to update your code to use the new variable names.  
  
## Handling Exceptions and the Automation Error Interfaces  
 Your automation object's methods and property accessor functions may throw exceptions. If so, you should handle them in your dual-interface implementation and pass information about the exception back to the controller through the OLE Automation error-handling interface, **IErrorInfo**. This interface provides for detailed, contextual error information through both `IDispatch` and VTBL interfaces. To indicate that an error handler is available, you should implement the **ISupportErrorInfo** interface.  
  
 To illustrate the error-handling mechanism, assume that the ClassWizard-generated functions used to implement the standard dispatch support throw exceptions. MFC's implementation of **IDispatch::Invoke** typically catches these exceptions and converts them into an EXCEPTINFO structure that is returned through the `Invoke` call. However, when VTBL interface is used, you are responsible for catching the exceptions yourself. As an example of protecting your dual-interface methods:  
  
```  
STDMETHODIMP CAutoClickDoc::XDualAClick::put_text(BSTR newText)  
{  
    METHOD_PROLOGUE(CAutoClickDoc, DualAClick)  
    TRY_DUAL(IID_IDualAClick) {* / / MFC는 자동으로 유니코드 BSTR에서 변환 * / / Ansi CString, 필요한 경우...  
    pThis->m_str = newText;  
    NOERROR를 반환 합니다.  
 }  
    CATCH_ALL_DUAL }  
```  
  
 `CATCH_ALL_DUAL` takes care of returning the correct error code when an exception occurs. `CATCH_ALL_DUAL` converts an MFC exception into OLE Automation error-handling information using the **ICreateErrorInfo** interface. (An example `CATCH_ALL_DUAL` macro is in the file MFCDUAL.H in the [ACDUAL](../visual-cpp-samples.md) sample. The function it calls to handle exceptions, `DualHandleException`, is in the file MFCDUAL.CPP.) `CATCH_ALL_DUAL` determines the error code to return based on the type of exception that occurred:  
  
- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) - In this case, `HRESULT` is constructed using the following code:  
  
 ```  
    hr = MAKE_HRESULT(SEVERITY_ERROR,
    FACILITY_ITF,   
 (e->m_wCode + 0x200));

 ```  
  
     This creates an `HRESULT` specific to the interface that caused the exception. The error code is offset by 0x200 to avoid any conflicts with system-defined `HRESULT`s for standard OLE interfaces.  
  
- [CMemoryException](../mfc/reference/cmemoryexception-class.md) - In this case, `E_OUTOFMEMORY` is returned.  
  
-   Any other exception - In this case, `E_UNEXPECTED` is returned.  
  
 To indicate that the OLE Automation error handler is used, you should also implement the **ISupportErrorInfo** interface.  
  
 First, add code to your automation class definition to show it supports **ISupportErrorInfo**.  
  
 Second, add code to your automation class's interface map to associate the **ISupportErrorInfo** implementation class with MFC's `QueryInterface` mechanism. The `INTERFACE_PART` statement matches the class defined for **ISupportErrorInfo**.  
  
 Finally, implement the class defined to support **ISupportErrorInfo**.  
  
 (The [ACDUAL](../visual-cpp-samples.md) sample contains three macros to help do these three steps, `DECLARE_DUAL_ERRORINFO`, `DUAL_ERRORINFO_PART`, and `IMPLEMENT_DUAL_ERRORINFO`, all contained in MFCDUAL.H.)  
  
 The following example implements a class defined to support **ISupportErrorInfo**. `CAutoClickDoc` is the name of your automation class and `IID_IDualAClick` is the **IID** for the interface that is the source of errors reported through the OLE Automation error object:  
  
```  
STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::AddRef()   
{  
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
    return pThis->ExternalAddRef();

}   
STDMETHODIMP_(ULONG) CAutoClickDoc::XSupportErrorInfo::Release()   
{   
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
    return pThis->ExternalRelease();

}   
STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::QueryInterface( REFIID iid, LPVOID* ppvObj)   
{   
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
    return pThis->ExternalQueryInterface(&iid, ppvObj);

}   
STDMETHODIMP CAutoClickDoc::XSupportErrorInfo::InterfaceSupportsErrorInfo( REFIID iid)   
{   
    METHOD_PROLOGUE(CAutoClickDoc, SupportErrorInfo)   
    반환 (iid IID_IDualAClick = =) S_OK: S_FALSE;   
}  
```  
  
## See Also  
 [Technical Notes by Number](../mfc/technical-notes-by-number.md)   
 [Technical Notes by Category](../mfc/technical-notes-by-category.md)

