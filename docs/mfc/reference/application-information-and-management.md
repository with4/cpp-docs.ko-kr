---
title: "응용 프로그램 정보 및 관리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- applications [MFC], managing
ms.assetid: b72f4154-24db-4e75-bca3-6873e2459c15
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3007e2fbae5bb0cee4472b6488be8ceb614bc1f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="application-information-and-management"></a>응용 프로그램 정보 및 관리
단일 응용 프로그램을 작성할 때 만들어야 [CWinApp](../../mfc/reference/cwinapp-class.md)-파생 된 개체입니다. 때때로 외부에서이 개체에 대 한 정보를 가져오는 경우가 `CWinApp`-파생 된 개체입니다. 또는 다른 전역 "mananger" 개체에 대 한 액세스를 할 수 있습니다.
  
 Microsoft Foundation Class 라이브러리는 이러한 작업을 수행할 수 있도록 다음과 같은 전역 함수를 제공 합니다.  
  
### <a name="application-information-and-management-functions"></a>응용 프로그램 정보 및 관리 기능  
  
|||  
|-|-|  
|[AfxBeginThread](#afxbeginthread)|새 스레드를 만듭니다.|  
|[AfxContextMenuManager](#afxcontextmenumanager)|전역에 대 한 포인터 [상황에 맞는 메뉴 관리자](ccontextmenumanager-class.md)합니다.|
|[AfxEndThread](#afxendthread)|현재 스레드가 종료 됩니다.|  
|[AfxFindResourceHandle](#afxfindresourcehandle)|에서는 리소스 체인에 설명 하 고 특정 리소스에서 리소스 ID와 리소스 종류를 찾습니다. |
|[AfxFreeLibrary](#afxfreelibrary)|코딩 된 동적 연결 라이브러리 (DLL) 모듈;의 참조 횟수를 감소 참조 횟수가 0에 도달 하면 모듈이 않았습니다.|  
|[AfxGetApp](#afxgetapp)|응용 프로그램에 대 한 포인터의 단일 반환 `CWinApp` 개체입니다.|  
|[AfxGetAppName](#afxgetappname)|응용 프로그램의 이름을 포함 하는 문자열을 반환 합니다.|  
|[AfxGetInstanceHandle](#afxgetinstancehandle)|반환 된 `HINSTANCE` 응용 프로그램의이 인스턴스를 나타내는입니다.|  
|[AfxGetMainWnd](#afxgetmainwnd)|비 OLE 응용 프로그램의 현재 "main" 창 또는 서버 응용 프로그램의 내부 프레임 창에 대 한 포인터를 반환합니다.|  
|[AfxGetPerUserRegistration](#afxgetperuserregistration)|이 함수를 사용 하 여 응용 프로그램에 대 한 레지스트리 액세스 리디렉션합니다 있는지 여부를 결정 하는 **HKEY_CURRENT_USER** ( **HKCU**) 노드.|  
|[AfxGetResourceHandle](#afxgetresourcehandle)|반환 된 `HINSTANCE` 응용 프로그램의 기본 리소스의 소스입니다. 이 사용 하 여 응용 프로그램의 리소스에 직접 액세스할 수 있습니다.|  
|[AfxGetThread](#afxgetthread)|현재에 대 한 포인터를 검색 [CWinThread](../../mfc/reference/cwinthread-class.md) 개체입니다.|  
|[AfxInitRichEdit](#afxinitrichedit)|버전을 1.0 서식 있는 편집 응용 프로그램에 대 한 제어를 초기화 합니다.|  
|[AfxInitRichEdit2](#afxinitrichedit2)|버전을 2.0 이상 서식 있는 편집 응용 프로그램에 대 한 제어를 초기화 합니다.| 
|[AfxIsExtendedFrameClass](#afxisextendedframeclass)|지정된 창이 확장된 프레임 개체인지 여부를 확인합니다.|
|[AfxIsMFCToolBar](#afxismfctoolbar)|지정된 된 창 도구 모음 개체 인지 확인 합니다.|
|[AfxKeyboardManager](#afxkeyboardmanager)|전역에 대 한 포인터 [키보드 관리자](ckeyboardmanager-class.md)합니다.|
|[AfxLoadLibrary](#afxloadlibrary)|DLL 모듈을 매핑하고 DLL 함수의 주소를 가져오는 데 사용할 수 있는 핸들을 반환 합니다.|  
|[AfxMenuTearOffManager](#afxmenutearoffmanager)|전역에 대 한 포인터 [맞춤 메뉴 관리자](cmenutearoffmanager-class.md)합니다.|
|[AfxMouseManager](#afxmousemanager)|전역에 대 한 포인터 [마우스 관리자](cmousemanager-class.md)합니다.|
|[AfxRegisterClass](#afxregisterclass)|MFC를 사용 하는 DLL의 창 클래스를 등록 합니다.|  
|[AfxRegisterWndClass](#afxregisterwndclass)|MFC에서 자동으로 등록 하는 것을 보완 하기 위해 Windows 창 클래스를 등록 합니다.|  
|[AfxSetPerUserRegistration](#afxsetperuserregistration)|응용 프로그램에 대 한 레지스트리 액세스 리디렉션하는지 여부를 설정 하는 **HKEY_CURRENT_USER** ( **HKCU**) 노드.|  
|[AfxSetResourceHandle](#afxsetresourcehandle)|설정의 `HINSTANCE` 핸들 응용 프로그램의 기본 리소스 로드 됩니다.|  
|[AfxShellManager](#afxshellmanager)|전역에 대 한 포인터 [셸 관리자](cshellmanager-class.md)합니다. |
|[AfxSocketInit](#afxsocketinit)|호출 된 `CWinApp::InitInstance` Windows 소켓을 초기화 하는 재정의 합니다.|  
|[AfxUserToolsManager](#afxusertoolsmanager)|전역에 대 한 포인터 [사용자 도구 관리자](cusertoolsmanager-class.md)합니다.|
|[AfxWinInit](#afxwininit)|MFC에서 제공한에 의해 호출 `WinMain` 의 일부로 함수는 [CWinApp](../../mfc/reference/cwinapp-class.md) 초기화 하는 GUI 기반 응용 프로그램을 MFC를 초기화 합니다. MFC를 사용 하는 콘솔 응용 프로그램에 대 한 직접 호출 되어야 합니다.|  
  

  
##  <a name="afxbeginthread"></a>AfxBeginThread  
 새 스레드를 만드는 데이 함수를 호출 합니다.  
  
```   
CWinThread* AfxBeginThread(
    AFX_THREADPROC pfnThreadProc,  
    LPVOID pParam,  
    int nPriority = THREAD_PRIORITY_NORMAL,  
    UINT nStackSize = 0,  
    DWORD dwCreateFlags = 0,  
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);

CWinThread* AfxBeginThread(
    CRuntimeClass* pThreadClass,  
    int nPriority = THREAD_PRIORITY_NORMAL,  
    UINT nStackSize = 0,  
    DWORD dwCreateFlags = 0,  
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL); 
```  
  
### <a name="parameters"></a>매개 변수  
 `pfnThreadProc`  
 작업자 스레드에 대 한 제어 함수를 가리킵니다. 일 수 없습니다 **NULL**합니다. 이 함수는 다음과 같이 선언 해야 합니다.  
  
 `UINT __cdecl MyControllingFunction( LPVOID pParam );`  
  
 *pThreadClass*  
 파생 된 개체의 RUNTIME_CLASS [CWinThread](../../mfc/reference/cwinthread-class.md)합니다.  
  
 *pParam*  
 에 있는 함수 선언이 매개 변수에서와 같이 제어 함수에 전달할 매개 변수 `pfnThreadProc`합니다.  
  
 `nPriority`  
 스레드의 원하는 우선 순위입니다. 전체 목록과 설명은 사용할 수 있는 우선 순위에 대 한 참조 [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) Windows sdk에서입니다.  
  
 `nStackSize`  
 새 스레드의 스택 바이트 단위로 크기를 지정합니다. 0 인 경우, 만드는 스레드와 동일한 크기 스택을 스택 크기의 기본값입니다.  
  
 `dwCreateFlags`  
 스레드 생성을 제어 하는 추가 플래그를 지정 합니다. 이 플래그는 두 값 중 하나를 포함할 수 있습니다.  
  
- **CREATE_SUSPENDED** 하나의 suspend 수로 스레드를 시작 합니다. 사용 하 여 **CREATE_SUSPENDED** 의 모든 멤버 데이터를 초기화 하려는 경우는 `CWinThread` 와 같은 개체를 [m_bAutoDelete](../../mfc/reference/cwinthread-class.md#m_bautodelete) 또는 스레드가 실행을 시작 하기 전에 파생된 클래스의 멤버입니다. 사용 하 여 프로그램 초기화가 완료 되 면 [CWinThread::ResumeThread](../../mfc/reference/cwinthread-class.md#resumethread) 실행 스레드를 시작 합니다. 스레드가 될 때까지 실행 되지 것입니다 `CWinThread::ResumeThread` 호출 됩니다.  
  
- **0** 을 만든 후 즉시 스레드를 시작 합니다.  
  
 `lpSecurityAttrs`  
 가리키는 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) 스레드에 대 한 보안 특성을 지정 하는 구조입니다. 경우 **NULL**, 동일한 보안 속성 다음과 같이 작성 사용 됩니다. 이 구조에 대 한 자세한 내용은 Windows SDK를 참조 하십시오.  
  
### <a name="return-value"></a>반환 값  
 새로 만든된 스레드 개체에 대 한 포인터 또는 **NULL** 오류가 발생 합니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 형태 `AfxBeginThread` 작업자 스레드를 만듭니다. 두 번째 형태 사용자 인터페이스 스레드 또는 작업자 스레드가 사용 될 수 있는 스레드를 만듭니다.  
  
 `AfxBeginThread`새 `CWinThread` 개체, 호출의 [CreateThread](../../mfc/reference/cwinthread-class.md#createthread) 함수는 스레드 실행을 시작 하 고 스레드에 대 한 포인터를 반환 합니다. 모든 개체가 제대로 할당 해제 생성 부분이 실패 해야 되도록 전체 프로시저에서 검사가 수행 됩니다. 호출 스레드를 종료 하려면 [AfxEndThread](#afxendthread) 에서 내에서 스레드 또는 작업자 스레드의 제어 함수에서 반환 합니다.  
  
 다중 스레딩 응용 프로그램으로 사용 하도록 설정 해야 합니다. 그렇지 않으면이 함수가 실패 합니다. 다중 스레딩을 사용에 대 한 자세한 내용은 참조 [/MD, /MT, /LD (런타임 라이브러리 사용)](../../build/reference/md-mt-ld-use-run-time-library.md) 아래 *Visual c + + 컴파일러 옵션*합니다.  
  
 대 한 자세한 내용은 `AfxBeginThread`, 문서를 참조 [다중 스레딩: 작업자 스레드 만들기](../../parallel/multithreading-creating-worker-threads.md) 및 [다중 스레딩: 사용자 인터페이스 스레드 만들기](../../parallel/multithreading-creating-user-interface-threads.md)합니다.  
  
### <a name="example"></a>예  
 예를 참조 [CSocket::Attach](../../mfc/reference/csocket-class.md#attach)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxwin.h  

## <a name="afxcontextmenumanager"></a>AfxContextMenuManager
전역에 대 한 포인터 [상황에 맞는 메뉴 관리자](ccontextmenumanager-class.md)합니다.  
   
### <a name="syntax"></a>구문    
```  
CContextMenuManager* afxContextMenuManager;  
```     
### <a name="requirements"></a>요구 사항  
 **헤더:** afxcontextmenumanager.h     

### <a name="see-also"></a>참고 항목   
 [CContextMenuManager 클래스](ccontextmenumanager-class.md)

  
##  <a name="afxendthread"></a>AfxEndThread  
 현재 실행 중인 스레드를 종료 하려면이 함수를 호출 합니다.  
  
```   
void AFXAPI AfxEndThread(
    UINT nExitCode,  
    BOOL bDelete  = TRUE); 
```  
  
### <a name="parameters"></a>매개 변수  
 *nExitCode*  
 스레드 종료 코드를 지정합니다.  
  
 *b 삭제*  
 메모리에서 스레드 개체를 삭제합니다.  
  
### <a name="remarks"></a>설명  
 스레드 종료 내에서 호출 되어야 합니다.  
  
 대 한 자세한 내용은 `AfxEndThread`, 문서를 참조 [다중 스레딩: 스레드 종료](../../parallel/multithreading-terminating-threads.md)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxwin.h  

  ## <a name="afxfindresourcehandle"></a>AfxFindResourceHandle
사용 하 여 `AfxFindResourceHandle` 을 리소스 체인을 탐색 하 고 특정 리소스에서 리소스 ID와 리소스 형식의 찾을 합니다.  
   
### <a name="syntax"></a>구문    
```
HINSTANCE AFXAPI AfxFindResourceHandle( LPCTSTR lpszName,  LPCTSTR lpszType );  
```
### <a name="parameters"></a>매개 변수  
 `lpszName`  
 리소스 ID를 포함 하는 문자열에 대 한 포인터    
 *lpszType*  
 리소스 형식에 대 한 포인터입니다. 목록이 리소스 종류에 대 한 참조 [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042) Windows sdk에서입니다.  
   
### <a name="return-value"></a>반환 값  
 리소스를 포함 하는 모듈에 대 한 핸들입니다.  
   
### <a name="remarks"></a>설명  
 `AfxFindResourceHandle`특정 리소스를 찾아 리소스가 포함 된 모듈에 대 한 핸들을 반환 합니다. MFC 확장 DLL 로드 한 모든 리소스가 있을 수 있습니다. `AfxFindResourceHandle`한 리소스에 알려 줍니다.  
  
 모듈은이 순서 대로 검색 됩니다.  
  
1.  주 모듈 (MFC 확장 DLL 경우).  
  
2.  비 시스템 모듈입니다.  
  
3.  언어별 모듈입니다.  
  
4.  주 모듈 (시스템 DLL 경우).  
  
5.  시스템 모듈입니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
   
### <a name="see-also"></a>참고 항목  
 [매크로 및 전역](mfc-macros-and-globals.md)   
  
##  <a name="afxfreelibrary"></a>AfxFreeLibrary  
 `AfxFreeLibrary` 및 `AfxLoadLibrary`는 각 코딩된 라이브러리 모듈에 대한 참조 횟수를 유지 관리합니다.  
  
```   
BOOL AFXAPI AfxFreeLibrary(HINSTANCE hInstLib); 
```  
  
### <a name="parameters"></a>매개 변수  
 *hInstLib*  
 로드된 라이브러리 모듈의 핸들입니다. [AfxLoadLibrary](#afxloadlibrary) 이 핸들을 반환 합니다.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 함수가 성공 하면; 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 `AfxFreeLibrary`는 로드된 DLL(동적 연결 라이브러리) 모듈의 참조 횟수를 감소시킵니다. 참조 횟수가 0에 도달하면, 호출 프로세스의 주소 공간에서 모듈이 매핑 해제되고 핸들이 더 이상 유효하지 않습니다. 이 참조 카운트는 `AfxLoadLibrary`가 호출될 때마다 매번 증가합니다.  
  
 라이브러리 모듈을 매핑 해제하기 전에 시스템은 DLL이 이를 사용하는 프로세스에서 분리할 수 있게 해줍니다. 이렇게 하면 DLL이 현재 프로세스를 대신해서 할당된 리소스를 정리할 수 있는 기회가 부여됩니다. 진입점 함수가 반환된 다음 라이브러리 모듈은 현재 프로세스의 주소 공간에서 제거됩니다.  
  
 `AfxLoadLibrary`를 사용해서 DLL 모듈을 매핑합니다.  
  
 사용 해야 `AfxFreeLibrary` 및 `AfxLoadLibrary` (Win32 함수 대신 **FreeLibrary** 및 **LoadLibrary**) 응용 프로그램은 여러 스레드를 사용 하는 경우. 사용 하 여 `AfxLoadLibrary` 및 `AfxFreeLibrary` MFC 확장 DLL이 로드 되거나 언로드될 전역 MFC 상태가 손상 되지 않는 경우 실행 하는 시작 및 종료 코드가 있는지 확인 합니다.  
  
### <a name="example"></a>예  
 예를 참조 [AfxLoadLibrary](#afxloadlibrary)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdll_.h  
  
##  <a name="afxgetapp"></a>AfxGetApp  
 주 메시지 디스패치 코드나 맨 위 창 등 응용 프로그램 정보에 액세스 하려면이 함수에서 반환 된 포인터를 사용할 수입니다.  
  
```   
CWinApp* AFXAPI AfxGetApp(); 
```  
  
### <a name="return-value"></a>반환 값  
 단일에 대 한 포인터 `CWinApp` 응용 프로그램에 대 한 개체입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드가 NULL을 반환 하는 경우는 응용 프로그램의 주 창이 초기화 되지 않은 완전히 아직를 나타낼 수 있습니다. 또한 문제를 나타낼 수 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#126](../../mfc/reference/codesnippet/cpp/application-information-and-management_1.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxwin.h  
  
##  <a name="afxgetappname"></a>AfxGetAppName  
 이 함수에서 반환 되는 문자열 임시 문자열 이름에 대 한 진단 메시지 또는 루트도 사용 될 수 있습니다.  
  
```   
LPCTSTR AFXAPI AfxGetAppName(); 
```  
  
### <a name="return-value"></a>반환 값  
 응용 프로그램의 이름을 포함 하는 null로 끝나는 문자열.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#127](../../mfc/reference/codesnippet/cpp/application-information-and-management_2.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxwin.h  
  
##  <a name="afxgetinstancehandle"></a>AfxGetInstanceHandle  
 이 함수를 사용 하면 현재 응용 프로그램의 인스턴스 핸들을 가져올 수 있습니다.  
  
```   
HINSTANCE  AFXAPI AfxGetInstanceHandle(); 
```  
  
### <a name="return-value"></a>반환 값  
 `HINSTANCE` 응용 프로그램의 현재 인스턴스를 합니다. MFC의 USRDLL 버전과 연결 된 DLL 내에서 호출 된 경우는 `HINSTANCE` DLL에 반환 됩니다.  
  
### <a name="remarks"></a>설명  
 `AfxGetInstanceHandle`항상 반환 된 `HINSTANCE` 실행 파일의 (합니다. EXE) DLL의 MFC USRDLL 버전과 연결 내에서 호출 합니다. 이 경우에 반환 된 `HINSTANCE` DLL에 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#128](../../mfc/reference/codesnippet/cpp/application-information-and-management_3.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxwin.h  
  
##  <a name="afxgetmainwnd"></a>AfxGetMainWnd  
 OLE 서버 응용 프로그램을 사용 하는 경우 호출를 직접 참조 하는 대신 응용 프로그램의 활성 주 창에 대 한 포인터를 검색 하려면이 함수는 [m_pMainWnd](../../mfc/reference/cwinthread-class.md#m_pmainwnd) application 개체의 멤버입니다.  
  
```   
CWnd* AFXAPI AfxGetMainWnd(); 
```  
  
### <a name="return-value"></a>반환 값  
 서버의 컨테이너 내에 내부 활성화된 개체가 있고 이 컨테이너가 활성 상태인 경우 이 함수는 내부 활성 문서가 포함된 프레임 창 개체에 대한 포인터를 반환합니다.  
  
 컨테이너 내에 내부 활성화된 개체가 없거나 응용 프로그램이 OLE 서버가 아닌 경우 이 함수는 단순히 응용 프로그램 개체의 `m_pMainWnd`를 반환합니다.  
  
 응용 프로그램의 기본 스레드에서 `AfxGetMainWnd`가 호출되는 경우 위의 규칙에 따라 응용 프로그램의 주 창이 반환됩니다. 함수가 응용 프로그램의 보조 스레드에서 호출되면 함수는 호출한 스레드에 연결된 주 창을 반환합니다.  
  
### <a name="remarks"></a>설명  
 응용 프로그램이 OLE 서버가 아닌 경우 이 함수의 호출은 응용 프로그램 개체의 `m_pMainWnd` 멤버를 직접 참조하는 것과 동일합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#129](../../mfc/reference/codesnippet/cpp/application-information-and-management_4.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxwin.h  
  
##  <a name="afxgetperuserregistration"></a>AfxGetPerUserRegistration  
 이 함수를 사용 하 여 응용 프로그램에 대 한 레지스트리 액세스 리디렉션합니다 있는지 여부를 결정 하는 **HKEY_CURRENT_USER** ( **HKCU**) 노드.  
  
```  
BOOL AFXAPI AfxGetPerUserRegistration();
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`레지스트리 정보가 지정은 나타냅니다는 **HKCU** 노드 `FALSE` 나타냅니다 응용 프로그램에 기본 노드 레지스트리 정보를 씁니다. 기본 노드는 **HKEY_CLASSES_ROOT** ( **HKCR**).  
  
### <a name="remarks"></a>설명  
 프레임 워크에 대 한 액세스 리디렉션합니다 레지스트리 리디렉션이 사용 하도록 설정 하면 **HKCR** 를 **HKEY_CURRENT_USER\Software\Classes**합니다. MFC 및 ATL frameworks 리디렉션의 영향을 받습니다.  
  
 응용 프로그램이 레지스트리 액세스 리디렉션하는지 여부를 변경 하려면 [AfxSetPerUserRegistration](#afxsetperuserregistration)합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxstat_.h    
  
##  <a name="afxgetresourcehandle"></a>AfxGetResourceHandle  
 사용 하 여는 `HINSTANCE` 응용 프로그램의 리소스에 직접 액세스할 수, 예를 들어 Windows 함수 호출에서이 함수에서 반환 된 핸들이 **FindResource**합니다.  
  
```   
extern HINSTANCE  AfxGetResourceHandle(); 
```  
  
### <a name="return-value"></a>반환 값  
 `HINSTANCE` 핸들 응용 프로그램의 기본 리소스 로드 됩니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#130](../../mfc/reference/codesnippet/cpp/application-information-and-management_5.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxwin.h  
  
##  <a name="afxgetthread"></a>AfxGetThread  
 에 대 한 포인터를 가져오려면이 함수를 호출 하 여 [CWinThread](../../mfc/reference/cwinthread-class.md) 현재 실행 중인 스레드를 나타내는 개체입니다.  
  
```   
CWinThread* AfxGetThread(); 
```  
  
### <a name="return-value"></a>반환 값  
 현재 실행 중인 스레드의;에 대 한 포인터 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 원하는 스레드에 내에서 호출 되어야 합니다.  
  
> [!NOTE]
>  MFC 프로젝트 호출을 이식 하는 경우 `AfxGetThread` Visual c + + 버전 4.2, 5.0 또는 6.0에서에서 `AfxGetThread` 호출 [AfxGetApp](#afxgetapp) 스레드가 없는 경우. 최신 버전의 컴파일러에서 `AfxGetThread` 반환 **NULL** 없는 스레드를 찾을 수 없으면입니다. 호출 해야 응용 프로그램 스레드를 사용 하도록 하려는 경우 `AfxGetApp`합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#132](../../mfc/reference/codesnippet/cpp/application-information-and-management_6.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxwin.h  
  
##  <a name="afxinitrichedit"></a>AfxInitRichEdit  
 응용 프로그램에 대 한 서식 있는 편집 컨트롤 (버전 1.0)을 초기화 하려면이 함수를 호출 합니다.  
  
```   
BOOL AFXAPI AfxInitRichEdit(); 
```  
  
### <a name="remarks"></a>설명  
 이 함수는 이전 버전과 호환성을 위해 제공 됩니다. 새 응용 프로그램 사용 해야 [AfxInitRichEdit2](#afxinitrichedit2)합니다.  
  
 `AfxInitRichEdit`RICHED32를 로드합니다. Rich edit 컨트롤의 버전 1.0을 초기화 하는 DLL입니다. 2.0 및 3.0 RICHED20 rich edit 컨트롤의 버전을 사용 하도록 DLL이 로드 되도록 해야 합니다. 호출 하 여 이렇게 [AfxInitRichEdit2](#afxinitrichedit2)합니다.  
  
 기존 Visual c + + 응용 프로그램을 버전 2.0에서 서식 있는 편집 컨트롤을 업데이트 하려면 열고는 합니다. RC 파일을 텍스트로 "RichEdit20a"를 "RICHEDIT"에서 각 rich edit 컨트롤의 클래스 이름을 변경 합니다. 그런 다음에 대 한 호출을 대체 `AfxInitRichEdit` 와 `AfxInitRichEdit2`합니다.  
  
 또한이 함수는 프로세스에 대 한 라이브러리 아직 초기화 되지 않은 경우 공용 컨트롤 라이브러리를 초기화 합니다. MFC 응용 프로그램에서 직접 rich edit 컨트롤을 사용 하는 경우에 MFC 서식 있는 편집 컨트롤 런타임을 제대로 초기화에 있도록 하기 위해이 함수를 호출 해야 합니다. Create 메서드를 호출 하는 경우 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), 또는 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), 일반적으로이 함수를 호출 하는 없지만 일부 경우에는 것이 필요 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxwin.h  
  
##  <a name="afxinitrichedit2"></a>AfxInitRichEdit2  
 응용 프로그램에 대 한 서식 있는 편집 컨트롤 (버전 2.0 이상)을 초기화 하려면이 함수를 호출 합니다.  
  
```   
BOOL AFXAPI AfxInitRichEdit2(); 
```  
  
### <a name="remarks"></a>설명  
 이 함수는 RICHED20 로드를 호출 합니다. DLL 및 초기화의 다양 한 버전 2.0에는 편집 컨트롤입니다. Create 메서드를 호출 하는 경우 [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md), [CRichEditView](../../mfc/reference/cricheditview-class.md), 또는 [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), 일반적으로이 함수를 호출 하는 없지만 일부 경우에는 것이 필요 합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxwin.h  

  ## <a name="afxisextendedframeclass"></a>AfxIsExtendedFrameClass
지정된 창이 확장된 프레임 개체인지 여부를 확인합니다.  
   
### <a name="syntax"></a>구문    
```  
BOOL AFXAPI AfxIsExtendedFrameClass( CWnd* pWnd );  
```
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 `CWnd`에서 파생된 개체에 대한 포인터입니다.  
   
### <a name="return-value"></a>반환 값  
 `TRUE`제공 된 창이 확장 된 프레임 개체; 이면 그렇지 않으면 `FALSE`합니다.  
   
### <a name="remarks"></a>설명  
 이 메서드는 `TRUE` 가 다음 클래스 중 하나에서 파생되는 경우 `pWnd` 를 반환합니다.  
  
-   `CFrameWndEx`  
  
-   `CMDIFrameWndEx`  
  
-   `COleIPFrameWndEx`  
  
-   `COleDocIPFrameWndEx`  
  
-   `CMDIChildWndEx`  
  
 이 메서드는 함수 또는 메서드 매개 변수가 확장된 프레임 창인지 확인해야 하는 경우에 유용합니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxpriv.h  
   
### <a name="see-also"></a>참고 항목  
 [CWnd 클래스](cwnd-class.md)   
 [CFrameWndEx 클래스](cframewndex-class.md)   

## <a name="afxismfctoolbar"></a>AfxIsMFCToolBar
지정된 된 창 도구 모음 개체 인지 확인 합니다.  
   
### <a name="syntax"></a>구문    
```  
BOOL AFXAPI AfxIsMFCToolBar(CWnd* pWnd);  
```
### <a name="parameters"></a>매개 변수  
 [in] `pWnd`  
 `CWnd`에서 파생된 개체에 대한 포인터입니다.  
   
### <a name="return-value"></a>반환 값  
 `TRUE`제공 된 창이 도구 모음 개체; 이면 그렇지 않으면 `FALSE`합니다.  
   
### <a name="remarks"></a>설명  
 이 메서드가 반환 `TRUE` 경우 `pWnd` 에서 파생 `CMFCToolBar`합니다. 이 메서드는 함수 또는 메서드 매개 변수 인지 확인 해야 할 경우에 유용는 `CMFCToolBar` 개체입니다.  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxpriv.h  
   
### <a name="see-also"></a>참고 항목  
 [CWnd 클래스](cwnd-class.md)   
 [CMFCToolBar 클래스](cmfctoolbar-class.md)

 
## <a name="afxkeyboardmanager"></a>AfxKeyboardManager
전역에 대 한 포인터 [키보드 관리자](ckeyboardmanager-class.md)합니다.  
   
### <a name="syntax"></a>구문    
```  
CKeyboardManager* afxKeyboardManager;  
```  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxkeyboardmanager.h  
   
### <a name="see-also"></a>참고 항목  

 [매크로, 전역 함수 및 전역 변수](mfc-macros-and-globals.md)   
 [CKeyboardManager 클래스](ckeyboardmanager-class.md)


##  <a name="afxloadlibrary"></a>AfxLoadLibrary  
 `AfxLoadLibrary`를 사용해서 DLL 모듈을 매핑합니다.  
  
```   
HINSTANCE AFXAPI AfxLoadLibrary(LPCTSTR lpszModuleName); 
```  
  
### <a name="parameters"></a>매개 변수  
 *lpszModuleName*  
 모듈의 이름을 포함 하는 null로 끝나는 문자열을 가리킵니다 (중 하나는 합니다. DLL 또는 합니다. EXE 파일)입니다. 지정 된 이름이 모듈의 파일 이름입니다.  
  
 문자열의 경로 지정 하 고 지정된 된 디렉터리에서 부분 파일이 함수가 실패 합니다.  
  
 경로가 지정 되지 않은 경우 파일 이름 확장명을 생략 하면 기본 확장 프로그램입니다. DLL이 추가 됩니다. 그러나 파일 이름 문자열이 모듈 이름에 확장명이 없는 있음을 나타내기 위해 후행 점 문자 (.)를 포함할 수 있습니다. 지정 된 경로가 함수는 다음과 같은 일련의 파일 검색.  
  
-   응용 프로그램이 로드 하는 디렉터리입니다.  
  
-   현재 디렉터리입니다.  
  
- **Windows 95/98:** Windows 시스템 디렉터리입니다. **Windows NT:** 32 비트 Windows 시스템 디렉터리입니다. 이 디렉터리의 이름은 SYSTEM32입니다.  
  
- **Windows NT 에서만:** 는 16 비트 Windows 시스템 디렉터리입니다. 이 디렉터리의 경로 가져오는 하는 Win32 함수가 있지만 검색 됩니다. 이 디렉터리의 이름은 시스템입니다.  
  
-   Windows 디렉터리입니다.  
  
-   PATH 환경 변수에 나열 된 디렉터리입니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공 하면 반환 값은 모듈에 대 한 핸들입니다. 함수가 실패 하면 반환 값은 NULL입니다.  
  
### <a name="remarks"></a>설명  
 사용할 수 있는 핸들을 반환 [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) DLL 함수의 주소를 가져옵니다. `AfxLoadLibrary`다른 실행 모듈을 매핑할 사용할 수도 있습니다.  
  
 각 프로세스는 각 코딩 된 라이브러리 모듈에 대 한 참조 횟수를 유지합니다. 이 참조 개수가 증가 될 때마다 `AfxLoadLibrary` 호출 되 고는 감소 될 때마다 `AfxFreeLibrary` 호출 됩니다. 참조 횟수가 0에 도달하면, 호출 프로세스의 주소 공간에서 모듈이 매핑 해제되고 핸들이 더 이상 유효하지 않습니다.  
  
 사용 해야 `AfxLoadLibrary` 및 `AfxFreeLibrary` (Win32 함수 대신 **LoadLibrary** 및 **FreeLibrary**) 응용 프로그램은 여러 스레드를 사용 하 고 있는 MFC를 동적으로 로드 되는 경우 확장 DLL입니다. 사용 하 여 `AfxLoadLibrary` 및 `AfxFreeLibrary` MFC 확장 DLL이 로드 되거나 언로드될 때 실행 되는 시작 및 종료 코드 전역 MFC 상태가 손상 되지 않는 시나리오입니다.  
  
 사용 하 여 `AfxLoadLibrary` 하려면; MFC의 DLL 버전에 동적으로 연결 해야 응용 프로그램에서 헤더 파일에 대 한 `AfxLoadLibrary`, Afxdll_.h은 MFC DLL로 응용 프로그램에 연결 된 경우를 포함 합니다. 이것은 설계를 사용 하거나 MFC 확장 Dll을 만들려면 MFC의 DLL 버전에 연결 해야 하기 때문에 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_DLLUser#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_7.cpp)]  
[!code-cpp[NVC_MFC_DLLUser#2](../../mfc/reference/codesnippet/cpp/application-information-and-management_8.cpp)]  
[!code-cpp[NVC_MFC_DLLUser#3](../../mfc/reference/codesnippet/cpp/application-information-and-management_9.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxdll_.h  
   
## <a name="afxmenutearoffmanager"></a>AfxMenuTearOffManager
전역에 대 한 포인터 [맞춤 메뉴 관리자](cmenutearoffmanager-class.md)합니다.  
   
### <a name="syntax"></a>구문    
```  
CMenuTearOffManager* g_pTearOffMenuManager;  
```  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxmenutearoffmanager.h  
   
### <a name="see-also"></a>참고 항목     
 [CMenuTearOffManager 클래스](cmenutearoffmanager-class.md)
 
## <a name="afxmousemanager"></a>AfxMouseManager
전역에 대 한 포인터 [마우스 관리자](cmousemanager-class.md)합니다.  
   
### <a name="syntax"></a>구문  
  ```  
CMouseManager* afxMouseManager;  
```  
### <a name="requirements"></a>요구 사항  
 **헤더:** afxmousemanager.h  
   
### <a name="see-also"></a>참고 항목  
 [CMouseManager 클래스](cmousemanager-class.md)
 

  
##  <a name="afxregisterclass"></a>AfxRegisterClass  
 이 함수를 사용 하 여 MFC를 사용 하는 DLL에 창 클래스를 등록 합니다.  
  
```   
BOOL AFXAPI AfxRegisterClass(WNDCLASS* lpWndClass); 
```  
  
### <a name="parameters"></a>매개 변수  
 *lpWndClass*  
 에 대 한 포인터는 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) 창 클래스를 등록 해야 하는 방법에 대 한 정보가 포함 된 구조입니다. 이 구조에 대 한 자세한 내용은 Windows SDK를 참조 하십시오.  
  
### <a name="return-value"></a>반환 값  
 **True 이면** 클래스가 있는 경우 성공적으로 등록, 그렇지 않으면 **FALSE**합니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하는 경우에 DLL이 언로드될 때 클래스 자동으로 등록이 취소 됩니다.  
  
 비 DLL 빌드에는 `AfxRegisterClass` 식별자가 Windows 함수에 매핑되는 매크로로 정의 되어 **RegisterClass**이므로 응용 프로그램에 등록 하는 클래스는 자동으로 등록 되지 않습니다. 사용 하는 경우 `AfxRegisterClass` 대신 **RegisterClass**, 코드를 응용 프로그램 및 DLL에서 변경 없이 사용할 수 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_DLL#3](../../atl-mfc-shared/codesnippet/cpp/application-information-and-management_10.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxwin.h  
  
##  <a name="afxregisterwndclass"></a>AfxRegisterWndClass  
 사용자 지정 창 클래스를 등록할 수 있습니다.  
  
```  
LPCTSTR AFXAPI AfxRegisterWndClass(
    UINT nClassStyle,  
    HCURSOR hCursor = 0,  
    HBRUSH hbrBackground = 0,  
    HICON hIcon = 0);  
```  
  
### <a name="parameters"></a>매개 변수  
 *nClassStyle*  
 Windows 클래스 스타일 또는 비트 OR를 사용 하 여 만든 스타일의 조합을 지정 ( **&#124;**) 창 클래스에 대 한 연산자입니다. 목록이 클래스 스타일에 대 한 참조는 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) Windows SDK에는 구조입니다. 경우 **NULL**, 기본값을 다음과 같이 설정 됩니다.  
  
-   마우스 스타일 설정 하는 **CS_DBLCLKS**, 어떤 보냅니다 마우스를 두 번 클릭할 때 메시지 창 프로시저를 두 번 클릭 합니다.  
  
-   화살표 커서 스타일 Windows 표준은을으로 설정 **IDC_ARROW**합니다.  
  
-   배경 브러시 설정 하는 **NULL**이므로 창 배경을 허무는 없습니다.  
  
-   표준, 없어 플래그 Windows 로고 아이콘 아이콘을 설정 합니다.  
  
 `hCursor`  
 창 클래스에서 만든 각 창에 설치 되도록 커서 리소스에 대 한 핸들을 지정 합니다. 기본값을 사용 하는 경우 **0**, 표준 받아볼 **IDC_ARROW** 커서입니다.  
  
 *hbrBackground*  
 창 클래스에서 만든 각 창에 설치 되어야 하는 브러시 리소스에 대 한 핸들을 지정 합니다. 기본값을 사용 하는 경우 **0**, 해야는 **NULL** 처리 하는 동안 배경 지워지지 배경 브러시 및 기본적으로 창 따르 [WM_ERASEBKGND](http://msdn.microsoft.com/library/windows/desktop/ms648055)합니다.  
  
 `hIcon`  
 창 클래스에서 만든 각 창에 설치 되어야 하는 아이콘 리소스에 대 한 핸들을 지정 합니다. 기본값을 사용 하는 경우 **0**, 표준, 없어 플래그 Windows 로고 아이콘을 얻게 됩니다.  
  
### <a name="return-value"></a>반환 값  
 클래스 이름이 포함 된 null로 끝나는 문자열입니다. 이 클래스 이름을 전달할 수 있습니다는 **만들기** 멤버 함수에 `CWnd` 또는 기타 **CWnd-**창을 만들기 위한 클래스를 파생 합니다. Microsoft Foundation 클래스 라이브러리에서의 이름이 생성 됩니다.  
  
> [!NOTE]
>  반환 값은 정적 버퍼에 대 한 포인터입니다. 이 문자열을 저장 하려면에 할당 한 `CString` 변수입니다.  
  
### <a name="remarks"></a>설명  
 Microsoft Foundation Class 라이브러리는 자동으로 사용자에 대 한 몇 가지 표준 창 클래스를 등록합니다. 사용자 지정 창 클래스 등록 하려는 경우이 함수를 호출 합니다.  
  
 클래스에 대해 등록 된 이름 `AfxRegisterWndClass` 매개 변수를 전적으로 의존 합니다. 호출 하는 경우 `AfxRegisterWndClass` 여러 번 동일한 매개 변수를 가진 것만 클래스 등록의 첫 번째 호출입니다. 에 대 한 후속 호출 `AfxRegisterWndClass` 동일한 매개 변수를 이미 등록 된 classname 작업만 반환 합니다.  
  
 호출 하는 경우 `AfxRegisterWndClass` 각 클래스에 대 한 별도 창 클래스를 가져오는 대신 동일한 매개 변수를 사용 하 여 여러 CWnd에서 파생 된 클래스에 대 한 각 클래스는 동일한 창 클래스를 공유 합니다. 이 문제가 발생할 수 있습니다는 **CS_CLASSDC** 클래스 스타일이 사용 됩니다. 여러 대신 **CS_CLASSDC** 창 클래스 /fd 하나 **CS_CLASSDC** 창 클래스와 같은 DC를 공유 하는 클래스를 사용 하는 모든 c + + 창. 이 문제를 방지 하려면 호출 [AfxRegisterClass](#afxregisterclass) 는 클래스를 등록 합니다.  
  
 기술적으로 설명 참조 [TN001: 창 클래스 등록](../../mfc/tn001-window-class-registration.md) 창 클래스 등록에 대 한 자세한 내용은 및 `AfxRegisterWndClass` 함수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#134](../../mfc/reference/codesnippet/cpp/application-information-and-management_11.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxwin.h  
  
##  <a name="afxsetperuserregistration"></a>AfxSetPerUserRegistration  
 응용 프로그램에 대 한 레지스트리 액세스 리디렉션하는지 여부를 설정 하는 **HKEY_CURRENT_USER** ( **HKCU**) 노드.  
  
```  
void AFXAPI AfxSetPerUserRegistration(BOOL bEnable);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 `TRUE`레지스트리 정보가 지정은 나타냅니다는 **HKCU** 노드 `FALSE` 나타냅니다 응용 프로그램에 기본 노드 레지스트리 정보를 씁니다. 기본 노드는 **HKEY_CLASSES_ROOT** ( **HKCR**).  
  
### <a name="remarks"></a>설명  
 하기 전에 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], 일반적으로 레지스트리를 액세스 하는 응용 프로그램 사용은 **HKEY_CLASSES_ROOT** 노드. 그러나 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], 응용 프로그램에 쓸 수 있는 관리자 모드에서 실행 해야 **HKCR**합니다.  
  
 이 메서드를 사용 하면 응용 프로그램을 읽고 레지스트리 액세스를 리디렉션하여 관리자 모드에서 실행 하지 않고 레지스트리에 쓰는 **HKCR** 를 **HKCU**합니다. 자세한 내용은 참조 [링커 속성 페이지](../../ide/linker-property-pages.md)합니다.  
  
 프레임 워크에 대 한 액세스 리디렉션합니다 레지스트리 리디렉션이 사용 하도록 설정 하면 **HKCR** 를 **HKEY_CURRENT_USER\Software\Classes**합니다. MFC 및 ATL frameworks 리디렉션의 영향을 받습니다.  
  
 기본 구현에서 레지스트리에 액세스 **HKCR**합니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxstat_.h    
  
##  <a name="afxsetresourcehandle"></a>AfxSetResourceHandle  
 이 함수를 사용 하 여 설정 하 여 `HINSTANCE` 응용 프로그램의 기본 리소스를 로드 하는 위치를 결정 하는 핸들입니다.  
  
```  
void AFXAPI AfxSetResourceHandle(HINSTANCE hInstResource);  
```  
  
### <a name="parameters"></a>매개 변수  
 `hInstResource`  
 인스턴스 또는 모듈에 대 한 핸들은 합니다. 응용 프로그램의 리소스는 로드 된 EXE 또는 DLL 파일입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#135](../../mfc/reference/codesnippet/cpp/application-information-and-management_12.cpp)]  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxwin.h  

## <a name="afxshellmanager"></a>AfxShellManager
전역에 대 한 포인터 [셸 관리자](cshellmanager-class.md)합니다.  
   
### <a name="syntax"></a>구문    
```  
CShellManager* afxShellManager;  
```  

### <a name="requirements"></a>요구 사항  
 **헤더:** afxshellmanager.h  
   
### <a name="see-also"></a>참고 항목  
 [CShellManager 클래스](cshellmanager-class.md)
  
##  <a name="afxsocketinit"></a>AfxSocketInit  
 이 함수를 호출 하면 `CWinApp::InitInstance` Windows 소켓을 초기화 하는 재정의 합니다.  
  
```  
BOOL AfxSocketInit(WSADATA* lpwsaData = NULL);  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpwsaData`  
 에 대 한 포인터는 [WSADATA](../../mfc/reference/wsadata-structure.md) 구조입니다. 경우 `lpwsaData` 과 같지 않은 `NULL`, 다음의 주소는 `WSADATA` 구조에 대 한 호출에서 채워진 `WSAStartup`합니다. 이 함수 또한 수 있도록 `WSACleanup` 응용 프로그램을 종료 하기 전에 사용자에 대해 호출 됩니다.  
  
### <a name="return-value"></a>반환 값  
 함수가 성공하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 정적으로 연결 된 MFC 응용 프로그램에서 보조 스레드에서 MFC 소켓을 사용 하는 경우 호출 해야 `AfxSocketInit` 소켓을 사용 하 여 소켓 라이브러리를 초기화 하는 각 스레드에 있습니다. 기본적으로 `AfxSocketInit` 기본 스레드에서만에서 호출 됩니다.  
  
### <a name="requirements"></a>요구 사항  
  **헤더** afxsock.h  

## <a name="afxusertoolsmanager"></a>AfxUserToolsManager
전역에 대 한 포인터 [사용자 도구 관리자](cusertoolsmanager-class.md)합니다.  
   
### <a name="syntax"></a>구문    
```  
CUserToolsManager* afxUserToolsManager;  
```  
   
### <a name="requirements"></a>요구 사항  
 **헤더:** afxusertoolsmanager.h  
   
### <a name="see-also"></a>참고 항목  
 [CUserToolsManager 클래스](cusertoolsmanager-class.md)
 
  
##  <a name="afxwininit"></a>AfxWinInit  
 MFC에서 제공 하 여이 함수는 호출 `WinMain` 의 일부로 함수는 [CWinApp](../../mfc/reference/cwinapp-class.md) 초기화 하는 GUI 기반 응용 프로그램을 MFC를 초기화 합니다.  
  
```  
BOOL AFXAPI AfxWinInit(
    HINSTANCE hInstance,  
    HINSTANCE hPrevInstance,  
    LPTSTR lpCmdLine,  
    int nCmdShow);  
```  
  
### <a name="parameters"></a>매개 변수  
 `hInstance`  
 현재 실행 중인 모듈의 핸들입니다.  
  
 *hPrevInstance*  
 응용 프로그램의 이전 인스턴스에 대 한 핸들입니다. Win32 기반 응용 프로그램의 경우이 매개 변수는 항상 **NULL**합니다.  
  
 `lpCmdLine`  
 응용 프로그램에 대 한 명령줄을 지정 하는 null로 끝나는 문자열을 가리킵니다.  
  
 `nCmdShow`  
 GUI 응용 프로그램의 주 창 표시 방법을 지정 합니다.  
  
### <a name="remarks"></a>설명  
 콘솔 응용 프로그램에 대 한는 사용 하지 않는 MFC에서 제공한 `WinMain` 호출 해야 함수를 `AfxWinInit` 직접를 MFC를 초기화 합니다.  
  
 호출 하는 경우 `AfxWinInit` 의 인스턴스를 선언 해야를 직접는 `CWinApp` 클래스입니다. 고유한 클래스를 파생 하지 선택할 수는 콘솔 응용 프로그램에 대 한 `CWinApp` 대신의 인스턴스를 사용 하 고 `CWinApp` 직접 합니다. 이 방법은 구현에서 응용 프로그램에 대 한 모든 기능을 유지 하려는 경우에 적절 한 **주**합니다.  
  
> [!NOTE]
>  어셈블리에 대 한 활성화 컨텍스트를 만들 때 MFC는 사용자 모듈에서 제공 하는 매니페스트 리소스를 사용 합니다. 활성화 컨텍스트는 `AfxWinInit`에서 만듭니다. 자세한 내용은 참조 [MFC 모듈 상태의 활성화 컨텍스트 지원](../../mfc/support-for-activation-contexts-in-the-mfc-module-state.md)합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_AfxWinInit#1](../../mfc/reference/codesnippet/cpp/application-information-and-management_13.cpp)]  

### <a name="requirements"></a>요구 사항  
  **헤더** afxwin.h  
    
## <a name="see-also"></a>참고 항목  
 [매크로 및 전역](../../mfc/reference/mfc-macros-and-globals.md)   
 [CWinApp 클래스](../../mfc/reference/cwinapp-class.md)
