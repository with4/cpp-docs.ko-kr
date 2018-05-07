---
title: 매크로 및 Dll을 관리 하기 위한 함수 | Microsoft Docs
ms.custom: ''
ms.date: 04/03/2017
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- module macros in MFC
ms.assetid: 303f4161-cb5e-4099-81ad-acdb11aa60fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5e79556bf6e3ae92f7a8d4975dbd30f199e2ca8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="macros-and-functions-for-managing-dlls"></a>매크로 및 Dll을 관리 하기 위한 함수

|||
|-|-|
|[AFX_EXT_CLASS](#afx_ext_class)]|클래스를 내보냅니다.|
|[AFX_MANAGE_STATE](#afx_manage_state)|DLL에서 내보낸된 함수를 보호 합니다.|
|[AfxOleInitModule](#afxoleinitmodule)|동적으로 MFC에 링크 하는 MFC 기본 DLL에서 OLE 지원을 제공 합니다.|
|[AfxNetInitModule](#afxnetinitmodule)|동적으로 MFC에 링크 하는 MFC 기본 DLL에서 MFC 소켓 지원을 제공 합니다.|
|[AfxGetAmbientActCtx](#afxgetambientactctx)|모듈 별로 상태 플래그의 현재 상태를 가져옵니다.|
|[AfxGetStaticModuleState](#afxgetstaticmodulestate)|초기화 하기 전에 및/또는 정리 후 이전 모듈 상태를 복원 하는 모듈 상태를 설정 합니다.|
|[AfxInitExtensionModule]()#afxinitextensionmodule|DLL을 초기화합니다.|
|[AfxSetAmbientActCtx](#afxsetambientactctx)|MFC의 WinSxS 동작에 영향을 주는 당 모듈 상태 플래그를 설정 합니다.|
|[AfxTermExtensionModule]()#afxtermextensionmodule)|MFC 할 있습니다 정리 MFC 확장을 DLL 각 프로세스 DLL에서 분리 하는 경우.|


## <a name="afx_ext_class"></a>  AFX_EXT_CLASS
[MFC 확장 Dll](../../build/extension-dlls.md) 매크로 사용 하 여 **AFX_EXT_CLASS** 내보낼 클래스, 클래스를 가져오려면 매크로 사용 하는 MFC 확장 DLL에 연결 된 실행 합니다.  
   
### <a name="remarks"></a>설명  
 와 **AFX_EXT_CLASS** 매크로, 동일한 헤더 DLL에 연결 하는 실행 파일과 함께 MFC 확장 DLL을 빌드하는 데 사용 되는 파일을 사용할 수 있습니다.  
  
 DLL의 헤더 파일에 추가 된 **AFX_EXT_CLASS** 키워드 다음과 같이 클래스의 선언에:  
  
```cpp
class AFX_EXT_CLASS CMyClass : public CDocument
{
// <body of class>
};
``` 
  
 자세한 내용은 참조 [내보내기 및 가져오기를 사용 하 여 AFX_EXT_CLASS](../../build/exporting-and-importing-using-afx-ext-class.md)합니다.  
   
### <a name="requirements"></a>요구 사항  
 헤더: **afxv_** dll.h  
   
## <a name="afx_manage_state"></a>  AFX_MANAGE_STATE
DLL에서 내보낸된 함수 보호 하기 위해이 매크로 호출 합니다.  
   
### <a name="syntax"></a>구문    
```
AFX_MANAGE_STATE(AFX_MODULE_STATE* pModuleState )  
```
### <a name="parameters"></a>매개 변수  
 `pModuleState`  
 에 대 한 포인터는 `AFX_MODULE_STATE` 구조입니다.  
   
### <a name="remarks"></a>설명  
 이 매크로 호출 하면 `pModuleState` 바로의 나머지 부분에 대 한 유효한 모듈 상태 범위를 포함입니다. 범위를 벗어나면 이전 유효한 모듈 상태로 자동으로 복원 됩니다.    
 `AFX_MODULE_STATE` 구조 즉, 푸시 되거나 팝 하는 모듈 상태의 일부 모듈에 대 한 글로벌 데이터를 포함 합니다.    
 기본적으로 MFC 리소스 템플릿을 로드 하는 주 응용 프로그램의 리소스 핸들을 사용 합니다. DLL의 대화 상자를 시작 하는 것과 같은 DLL에 내보낸된 함수를 포함 하는 경우이 서식 파일은 실제로 DLL 모듈에 저장 됩니다. 사용할 올바른 핸들에 대 한 모듈 상태를 전환 해야 합니다. 함수의 시작 부분에 다음 코드를 추가 하 여이 수행할 수 있습니다.    
```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));

```
 반환 된 상태와 현재 모듈 상태 서로 바뀝니다 [AfxGetStaticModuleState](#afxgetstaticmodulestate) 현재 범위의 끝까지 합니다.    
 모듈 상태와 MFC에 대 한 자세한 내용은 "관리는 데이터의 MFC 모듈 상태"를 참조 [새 문서 만들기, 창 및 뷰](../creating-new-documents-windows-and-views.md) 및 [기술 참고 58](../tn058-mfc-module-state-implementation.md)합니다.    
> [!NOTE]
>  사용 하 여 MFC 활성화 컨텍스트는 어셈블리를 만들 때 [AfxWinInit](#afxwininit) 컨텍스트를 생성 하 고 `AFX_MANAGE_STATE` 를 활성화 및 비활성화 합니다. 또한 `AFX_MANAGE_STATE` 사용자 DLL에서 선택한 해당 활성화 컨텍스트에서 실행 되도록 MFC 코드를 허용 하기 위해 정적 MFC 라이브러리와 MFC Dll에 대 한 사용 됩니다. 자세한 내용은 참조 [MFC 모듈 상태의 활성화 컨텍스트 지원](../support-for-activation-contexts-in-the-mfc-module-state.md)합니다.     
### <a name="requirements"></a>요구 사항  
 **헤더:** afxstat_.h  
   
### <a name="see-also"></a>참고 항목  
 [AfxGetStaticModuleState](#afxgetstaticmodulestate)

## <a name="a-nameafxoleinitmodulea-afxoleinitmodule"></a><a name="afxoleinitmodule"><a/> AfxOleInitModule
동적으로 MFC에 링크 하는 MFC 기본 DLL에서 OLE 지원에 대 한 기본 MFC DLL의에이 함수를 호출 `CWinApp::InitInstance` MFC OLE DLL을 초기화 하는 함수입니다.  
   
### <a name="syntax"></a>구문    
```
void AFXAPI AfxOleInitModule( );  
```  
   
### <a name="remarks"></a>설명  
 MFC OLE DLL이 MFC 확장 DLL; MFC 확장 DLL 가져오기에 유선 하려면에서는 **CDynLinkLibrary** 만들어야 하 체인은 **CDynLinkLibrary** 은 사용 하는 모든 모듈의 컨텍스트에서 개체입니다. `AfxOleInitModule` 만듭니다는 **CDynLinkLibrary** 기본 MFC DLL의 컨텍스트에서 개체에 유선 가져옵니다 있도록는 **CDynLinkLibrary** 체인 기본 MFC DLL의 개체입니다.  
  
 OLE 컨트롤을 작성 하는 사용 하는 경우 `COleControlModule`를 호출 하지 않아야 **AfxOleInitModule** 때문에 `InitInstance` 멤버 함수에 대 한 `COleControlModule` 호출 `AfxOleInitModule`합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더**: < afxdll_.h >  
   
### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)

## <a name="afxnetinitmodule"></a>  AfxNetInitModule
동적으로 MFC에 링크 하는 MFC 기본 DLL에서 MFC 소켓 지원, 기본 MFC DLL에이 함수에 대 한 호출 추가 **CWinApp::InitInstance** MFC 소켓 DLL을 초기화 하는 함수입니다.  
   
### <a name="syntax"></a>구문    
```
void AFXAPI AfxNetInitModule( );  
```  
   
### <a name="remarks"></a>설명  
 MFC 소켓 DLL은 MFC 확장 DLL; MFC 확장 DLL 가져오기에 유선 하려면에서는 **CDynLinkLibrary** 만들어야 하 체인은 **CDynLinkLibrary** 은 사용 하는 모든 모듈의 컨텍스트에서 개체입니다. `AfxNetInitModule` 만듭니다는 **CDynLinkLibrary** 기본 MFC DLL의 컨텍스트에서 개체에 유선 가져옵니다 있도록는 **CDynLinkLibrary** 체인 기본 MFC DLL의 개체입니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** < afxdll_.h >  
   
### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
 [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox)

## <a name="afxgetambientactctx"></a> AfxGetAmbientActCtx
MFC의 WinSxS 동작에 영향을 주는 당 모듈 상태 플래그의 현재 상태를 가져오려면이 함수를 사용 합니다.  
   
### <a name="syntax"></a>구문    
```  
BOOL AFXAPI AfxGetAmbientActCtx();   
```  
   
### <a name="return-value"></a>반환 값  
 모듈 상태 플래그 현재 값입니다.  
   
### <a name="remarks"></a>설명  
 플래그가 설정 되 면 (기본값임) 스레드가 이미 MFC 모듈 획득 시점과 (참조 [AFX_MANAGE_STATE](#afx_manage_state)), 모듈의 컨텍스트에서 사용할 수 있습니다.  
  
 플래그가 설정 되지 않은 경우 모듈의 컨텍스트 항목에 대해 활성화 되지 않았습니다.  
  
 모듈의 컨텍스트는 일반적으로 리소스 모듈에에서 포함 된 매니페스트에서에서 결정 됩니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxcomctl32.h  
   
### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
 [AFX_MANAGE_STATE](#afx_manage_state)   
 [MFC 모듈의 상태 데이터 관리](../managing-the-state-data-of-mfc-modules.md)   
 [AfxSetAmbientActCtx](#setambientactctx)
 
## <a name="afxgetstaticmodulestate"></a> AfxGetStaticModuleState
초기화 하기 전에 모듈 상태를 설정 및/또는 정리 후 이전 모듈 상태를 복원 하려면이 함수를 호출 합니다.  
   
### <a name="syntax"></a>구문    
```
AFX_MODULE_STATE* AFXAPI AfxGetStaticModuleState( );  
```  
   
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `AFX_MODULE_STATE` 구조입니다.  
   
### <a name="remarks"></a>설명  
 `AFX_MODULE_STATE` 구조 즉, 푸시 되거나 팝 하는 모듈 상태의 일부 모듈에 대 한 글로벌 데이터를 포함 합니다.  
  
 기본적으로 MFC 리소스 템플릿을 로드 하는 주 응용 프로그램의 리소스 핸들을 사용 합니다. DLL의 대화 상자를 시작 하는 것과 같은 DLL에 내보낸된 함수를 포함 하는 경우이 서식 파일은 실제로 DLL 모듈에 저장 됩니다. 사용할 올바른 핸들에 대 한 모듈 상태를 전환 해야 합니다. 함수의 시작 부분에 다음 코드를 추가 하 여이 수행할 수 있습니다.  
  
```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState( ));

```
  
 반환 된 상태와 현재 모듈 상태 서로 바뀝니다 `AfxGetStaticModuleState` 현재 범위의 끝까지 합니다.  
  
 모듈 상태와 MFC에 대 한 자세한 내용은 "관리는 데이터의 MFC 모듈 상태"를 참조 [새 문서 만들기, 창 및 뷰](../creating-new-documents-windows-and-views.md) 및 [기술 참고 58](../tn058-mfc-module-state-implementation.md)합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxstat_.h  
   

## <a name="afxinitextensionmodule"></a> AfxInitExtensionModule
MFC 확장 DLL의에이 함수를 호출 `DllMain` DLL을 초기화 합니다.  
   
### <a name="syntax"></a>구문    
```
BOOL AFXAPI AfxInitExtensionModule( AFX_EXTENSION_MODULE& state,  HMODULE hModule );  
```
### <a name="parameters"></a>매개 변수  
 `state`  
 에 대 한 참조는 [AFX_EXTENSION_MODULE 구조체](afx-extension-module-structure.md) 구조를 초기화 한 다음 MFC 확장 DLL 모듈의 상태를 포함 합니다. 일반 정적 개체가 생성 되기 전에 실행의 일부로 MFC 확장 DLL에서 초기화 된 런타임 클래스 개체의 복사본을 포함 하는 상태 `DllMain` 를 입력 합니다.  
  
 `hModule`  
 MFC 확장 DLL 모듈의 핸들입니다.  
   
### <a name="return-value"></a>반환 값  
 **True 이면** MFC 확장 DLL이 성공적으로 초기화 된 고, 그렇지 않으면 **FALSE**합니다.  
   
### <a name="remarks"></a>설명  
 예를 들어:  
  
```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;

```
  
 `AfxInitExtensionModule` dll의 복사본을 만들어 **HMODULE** 및 캡처 DLL의 런타임 클래스 (`CRuntimeClass` 구조)의 개체 팩터리 뿐만 아니라 (`COleObjectFactory` 개체) 사용 하기 위해 뒷부분에 나오는 경우에는 **CDynLinkLibrary**개체가 만들어집니다.    
 MFC 확장 Dll 두 가지를 수행 해야 자신의 `DllMain` 함수:    
-   호출 [AfxInitExtensionModule](#_mfc_afxinitextensionmodule) 반환 값을 확인 합니다.   
-   만들기는 **CDynLinkLibrary** DLL를 내보내는 경우 개체 [CRuntimeClass 구조](cruntimeclass-structure.md) 자체 사용자 지정 리소스 또는 개체입니다.    
 호출할 수 있습니다 `AfxTermExtensionModule` MFC 확장 DLL에서에서 각 프로세스를 분리할 때 MFC 확장 DLL 정리 하려면 (때나의 결과로 DLL이 언로드되어 프로세스가 종료 될 때 발생 하는 `AfxFreeLibrary` 호출).     

### <a name="requirements"></a>요구 사항  
 **헤더:** afxdll_.h     

### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
 [AfxTermExtensionModule](#afxtermextensionmodule)

 ## <a name="afxsetambientactctx"></a>  AfxSetAmbientActCtx
이 함수를 사용 하 여 MFC의 WinSxS 동작에 영향을 주는 당 모듈 상태 플래그를 설정 합니다.  
   
### <a name="syntax"></a>구문  
  ```
   void AFXAPI AfxSetAmbientActCtx( BOOL bSet  
);  
```
### <a name="parameters"></a>매개 변수  
 `bSet`  
 모듈 상태 플래그의 새 값입니다.  
   
### <a name="remarks"></a>설명  
 플래그가 설정 되 면 (기본값임) 스레드가 이미 MFC 모듈 획득 시점과 (참조 [AFX_MANAGE_STATE](#afx_manage_state)), 모듈의 컨텍스트에서 사용할 수 있습니다.    
 플래그가 설정 되지 않은 경우 모듈의 컨텍스트 항목에 대해 활성화 되지 않았습니다.    
 모듈의 컨텍스트는 일반적으로 리소스 모듈에에서 포함 된 매니페스트에서에서 결정 됩니다.  
   
### <a name="example"></a>예제  
 ```cpp
BOOL CMFCListViewApp::InitInstance()
{
   AfxSetAmbientActCtx(FALSE);
   // Remainder of function definition omitted.
```
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxcomctl32.h  
   
### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
 [AfxGetAmbientActCtx](#afxgetambientactctx)   
 [AFX_MANAGE_STATE](#afx_manage_state)   
 [MFC 모듈의 상태 데이터 관리](../managing-the-state-data-of-mfc-modules.md) 

## <a name="afxtermextensionmodule"></a>  AfxTermExtensionModule

이 함수를 허용 하도록 MFC 정리에 MFC 확장 DLL DLL에서 각 프로세스를 분리할 때 호출 (때나의 결과로 DLL이 언로드되어 프로세스가 종료 될 때 발생 하는 `AfxFreeLibrary` 호출).  
   
### <a name="syntax"></a>구문  
  ```
void AFXAPI AfxTermExtensionModule(  AFX_EXTENSION_MODULE& state,  BOOL bAll  = FALSE );  
```
### <a name="parameters"></a>매개 변수  
 `state`  
 에 대 한 참조는 [AFX_EXTENSION_MODULE](afx-extension-module-structure.md) MFC 확장 DLL 모듈의 상태를 포함 하는 구조입니다.  
  
 *클로즈업*  
 경우 **TRUE**정리, MFC 확장 DLL 모듈을 모두 합니다. 그렇지 않고 현재 DLL 모듈을 정리 합니다.  
   
### <a name="remarks"></a>설명  
 `AfxTermExtensionModule` 모듈에 연결 된 모든 로컬 저장소를 삭제 하 고 메시지 맵 캐시에서 항목을 제거 합니다. 예를 들어:  
  
```cpp
static AFX_EXTENSION_MODULE NVC_MFC_DLLDLL = { NULL, NULL };
extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    // Remove this if you use lpReserved
    UNREFERENCED_PARAMETER(lpReserved);

    if (dwReason == DLL_PROCESS_ATTACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Initializing!\n");

        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(NVC_MFC_DLLDLL, hInstance))
            return 0;

        new CMyDynLinkLibrary(NVC_MFC_DLLDLL);

    }
    else if (dwReason == DLL_PROCESS_DETACH)
    {
        TRACE0("NVC_MFC_DLL.DLL Terminating!\n");

        // Terminate the library before destructors are called
        AfxTermExtensionModule(NVC_MFC_DLLDLL);
    }
    return 1;   // ok
}

```
  
 응용 프로그램을 로드 하 MFC 확장 Dll을 동적으로 확보 하는 경우 호출 해야 `AfxTermExtensionModule`합니다. 이후 대부분 MFC 확장 Dll을 동적으로 로드 되지 않습니다 (일반적으로 연결 된 해당 가져오기 라이브러리를 통해)에 대 한 호출 `AfxTermExtensionModule` 일반적으로 필요 하지 않습니다.  
  
 MFC 확장 Dll을 호출할 필요는 [AfxInitExtensionModule](#afxinitextensionmodule) 에 자신의 `DllMain`합니다. DLL를 내보내는 경우 [CRuntimeClass](cruntimeclass-structure.md) 개체 또는 고유한 사용자 지정 리소스에 만들어야 할 한 **CDynLinkLibrary** 개체 `DllMain`합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxdll_.h  
   
### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
 [AfxInitExtensionModule](#afxinitextensionmodule)
 




