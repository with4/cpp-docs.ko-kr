---
title: "CWinThread 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWinThread
- AFXWIN/CWinThread
- AFXWIN/CWinThread::CWinThread
- AFXWIN/CWinThread::CreateThread
- AFXWIN/CWinThread::ExitInstance
- AFXWIN/CWinThread::GetMainWnd
- AFXWIN/CWinThread::GetThreadPriority
- AFXWIN/CWinThread::InitInstance
- AFXWIN/CWinThread::IsIdleMessage
- AFXWIN/CWinThread::OnIdle
- AFXWIN/CWinThread::PostThreadMessage
- AFXWIN/CWinThread::PreTranslateMessage
- AFXWIN/CWinThread::ProcessMessageFilter
- AFXWIN/CWinThread::ProcessWndProcException
- AFXWIN/CWinThread::PumpMessage
- AFXWIN/CWinThread::ResumeThread
- AFXWIN/CWinThread::Run
- AFXWIN/CWinThread::SetThreadPriority
- AFXWIN/CWinThread::SuspendThread
- AFXWIN/CWinThread::m_bAutoDelete
- AFXWIN/CWinThread::m_hThread
- AFXWIN/CWinThread::m_nThreadID
- AFXWIN/CWinThread::m_pActiveWnd
- AFXWIN/CWinThread::m_pMainWnd
dev_langs:
- C++
helpviewer_keywords:
- worker threads
- threading [MFC], safety
- CWinThread class
- threading [MFC], creating threads
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 866e847f9c1d73d6f9882e50b1274fbad9e21a39
ms.lasthandoff: 02/24/2017

---
# <a name="cwinthread-class"></a>CWinThread 클래스
응용 프로그램 내의 실행 스레드를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CWinThread : public CCmdTarget  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CWinThread::CWinThread](#cwinthread)|`CWinThread` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CWinThread::CreateThread](#createthread)|실행을 시작 하는 `CWinThread` 개체입니다.|  
|[CWinThread::ExitInstance](#exitinstance)|스레드가 종료 될 때 정리를 수행 하려면이 옵션을 재정의 합니다.|  
|[CWinThread::GetMainWnd](#getmainwnd)|스레드에 대 한 주 창에 대 한 포인터를 검색합니다.|  
|[CWinThread::GetThreadPriority](#getthreadpriority)|현재 스레드의 우선 순위를 가져옵니다.|  
|[CWinThread::InitInstance](#initinstance)|스레드 인스턴스 초기화를 수행 하도록 재정의 합니다.|  
|[CWinThread::IsIdleMessage](#isidlemessage)|특별 한 메시지를 확인.|  
|[CWinThread::OnIdle](#onidle)|스레드 관련 유휴 시간 처리를 수행 하려면 재정의 합니다.|  
|[CWinThread::PostThreadMessage](#postthreadmessage)|메시지를 다른 게시 `CWinThread` 개체입니다.|  
|[CWinThread::PreTranslateMessage](#pretranslatemessage)|Windows 함수에 디스패치 되기 전에 메시지를 필터링 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934)합니다.|  
|[CWinThread::ProcessMessageFilter](#processmessagefilter)|응용 프로그램에 도달 하기 전에 특정 메시지를 차단 합니다.|  
|[CWinThread::ProcessWndProcException](#processwndprocexception)|스레드의 메시지 및 명령 처리기에 의해 throw 되는 모든 처리 되지 않은 예외를 가로챕니다.|  
|[CWinThread::PumpMessage](#pumpmessage)|스레드의 메시지 루프를 포함합니다.|  
|[CWinThread::ResumeThread](#resumethread)|스레드 a 감소 개수를 일시 중단합니다.|  
|[CWinThread::Run](#run)|메시지 펌프를 사용 하 여 스레드에 대 한 함수를 제어 합니다. 기본 메시지 루프를 사용자 지정 하려면 재정의 합니다.|  
|[CWinThread::SetThreadPriority](#setthreadpriority)|현재 스레드의 우선 순위를 설정합니다.|  
|[CWinThread::SuspendThread](#suspendthread)|증가 한 스레드 개수를 일시 중단합니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CWinThread::operator 핸들](#operator_handle)|핸들을 검색 된 `CWinThread` 개체입니다.|  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CWinThread::m_bAutoDelete](#m_bautodelete)|스레드 종료 시 개체를 삭제할 것인지 지정 합니다.|  
|[CWinThread::m_hThread](#m_hthread)|현재 스레드를 처리 합니다.|  
|[CWinThread::m_nThreadID](#m_nthreadid)|현재 스레드의 ID입니다.|  
|[CWinThread::m_pActiveWnd](#m_pactivewnd)|OLE 서버에 내부 활성화 되 면 컨테이너 응용 프로그램의 주 창에 대 한 포인터입니다.|  
|[CWinThread::m_pMainWnd](#m_pmainwnd)|응용 프로그램의 주 창에 대 한 포인터를 보유합니다.|  
  
## <a name="remarks"></a>주의  
 주 스레드 실행은 일반적으로에서 파생 된 개체에 의해 제공 `CWinApp`; `CWinApp` 에서 파생 된 `CWinThread`합니다. 추가 `CWinThread` 개체는 지정된 된 응용 프로그램 내에서 여러 스레드를 사용 합니다.  
  
 두 가지가 일반 스레드는 `CWinThread` 지원: 작업자 스레드 및 사용자 인터페이스 스레드입니다. 작업자 스레드 메시지 펌프가 없습니다: 스프레드시트 응용 프로그램에서 백그라운드 계산을 수행 하는 스레드는 예를 들어 있습니다. 사용자 인터페이스 스레드는 메시지 펌프가 및 시스템에서 받은 메시지를 처리 합니다. [CWinApp](../../mfc/reference/cwinapp-class.md) 및 클래스에서 파생 된 사용자 인터페이스 스레드에 속합니다. 다른 사용자 인터페이스 스레드에서 직접 파생 될 수도 있습니다 `CWinThread`합니다.  
  
 클래스의 개체 `CWinThread` 스레드의 기간 동안 일반적으로 존재 합니다. 이 동작을 수정 하려는 경우 설정 [m_bAutoDelete](#m_bautodelete) 를 **FALSE**합니다.  
  
 `CWinThread` 클래스는 하는 데 필요한 코드와 MFC 완전 한 스레드 안전 합니다. 스레드 관련 정보를 유지 하는 프레임 워크에서 사용 하는 스레드 로컬 데이터에서 관리 하는 `CWinThread` 개체입니다. 에 대 한이 종속성이로 인해 `CWinThread` 스레드 로컬 데이터를 처리 하려면 MFC를 사용 하는 모든 스레드에서 MFC에서 만든 해야 합니다. 예를 들어, 런타임 함수에서 만든 스레드 [_beginthread, _beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) MFC Api를 사용할 수 없습니다.  
  
 호출 스레드를 만들려면 [AfxBeginThread](application-information-and-management.md#afxbeginthread)합니다. 작업자 또는 사용자 인터페이스 스레드 여부에 따라 두 가지 형식이 있습니다. 에 전달 하는 사용자 인터페이스 스레드를 원한다 면 `AfxBeginThread` 에 대 한 포인터는 `CRuntimeClass` 의 프로그램 `CWinThread`-클래스를 파생 합니다. 에 전달 하는 작업자 스레드를 만들려는 경우 `AfxBeginThread` 제어 함수 및 매개 변수를 제어 하는 함수에 대 한 포인터입니다. 작업자 스레드 및 사용자 인터페이스 스레드 모두에 대 한 우선 순위, 스택 크기, 생성 플래그 및 보안 특성을 수정 하는 선택적 매개 변수를 지정할 수 있습니다. `AfxBeginThread`새 사용자에 대 한 포인터를 반환 합니다 `CWinThread` 개체입니다.  
  
 호출 하는 대신 `AfxBeginThread`를 생성할 수는 `CWinThread`-파생 개체와 호출 `CreateThread`합니다. 이&2; 단계 생성 메서드는 다시 사용 하려는 경우 유용는 `CWinThread` 개체 간에 연속 생성 및 스레드 실행의 종료를 표시 합니다.  
  
 대 한 자세한 내용은 `CWinThread`, 문서를 참조 [c + + 및 MFC에서 다중 스레딩](../../parallel/multithreading-with-cpp-and-mfc.md), [다중 스레딩: 사용자 인터페이스 스레드 만들기](../../parallel/multithreading-creating-user-interface-threads.md), [다중 스레딩: 작업자 스레드 만들기](../../parallel/multithreading-creating-worker-threads.md), 및 [다중 스레딩: 동기화 클래스를 사용 하는 방법을](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWinThread`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="createthread"></a>CWinThread::CreateThread  
 호출 프로세스의 주소 공간 내에서 실행 되도록 스레드를 만듭니다.  
  
```  
BOOL CreateThread(
    DWORD dwCreateFlags = 0,  
    UINT nStackSize = 0,  
    LPSECURITY_ATTRIBUTES lpSecurityAttrs = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwCreateFlags`  
 스레드 생성을 제어 하는 추가 플래그를 지정 합니다. 이 플래그는 두 값 중 하나를 포함할 수 있습니다.  
  
- **CREATE_SUSPENDED** 스레드는 일시 중단 횟수가 하나를 시작 합니다. 사용 하 여 **CREATE_SUSPENDED** 의 모든 멤버 데이터를 초기화 하려는 경우는 `CWinThread` 와 같은 개체를 [m_bAutoDelete](#m_bautodelete) 또는 스레드가 실행을 시작 하기 전에, 파생된 클래스의 멤버입니다. 사용 하 여 프로그램 초기화가 완료 되 면는 [CWinThread::ResumeThread](#resumethread) 실행 스레드를 시작 합니다. 스레드가 될 때까지 실행 되지 않는 `CWinThread::ResumeThread` 호출 됩니다.  
  
- **0** 을 만든 후 즉시 스레드를 시작 합니다.  
  
 `nStackSize`  
 새 스레드의 스택 바이트의 크기를 지정합니다. 경우 **0**, 스택 크기의 기본 스레드는 프로세스와 같은 크기의 기본값입니다.  
  
 `lpSecurityAttrs`  
 가리키는 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) 스레드에 대 한 보안 특성을 지정 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 스레드를 성공적으로 만드는 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 `AfxBeginThread` 를 스레드 개체를 만들고 한 번에 실행 합니다. 사용 하 여 `CreateThread` 연속 생성 및 종료 스레드는 실행 간에 스레드 개체를 다시 사용 하려는 경우.  
  
##  <a name="cwinthread"></a>CWinThread::CWinThread  
 `CWinThread` 개체를 생성합니다.  
  
```  
CWinThread();
```  
  
### <a name="remarks"></a>주의  
 호출 스레드의 실행을 시작 하려면는 [CreateThread](#createthread) 멤버 함수입니다. 일반적으로를 호출 하 여 스레드를 만들겠습니다 [AfxBeginThread](http://msdn.microsoft.com/library/e9e8684d-24f7-4599-8fdf-1f4f560a753b),이 생성자를 호출 합니다을 및 `CreateThread`합니다.  
  
##  <a name="exitinstance"></a>CWinThread::ExitInstance  
 거의 재정의 내에서 프레임 워크에서 호출 [실행](#run) 는 스레드를 종료 하려면 멤버 함수를 호출 하는 경우 또는 [InitInstance](#initinstance) 실패 합니다.  
  
```  
virtual int ExitInstance();
```  
  
### <a name="return-value"></a>반환 값  
 스레드 종료 코드입니다. 0은 오류를 나타내며 0 보다 큰 값에 오류가 발생 합니다. 호출 하 여이 값을 검색할 수 [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190)합니다.  
  
### <a name="remarks"></a>주의  
 호출 하지 마십시오이 멤버 함수 어디에서 나 하지만 내는 **실행** 멤버 함수입니다. 이 멤버 함수는 사용자 인터페이스 스레드에만 사용 됩니다.  
  
 이 함수의 기본 구현은 삭제는 `CWinThread` 개체 경우 [m_bAutoDelete](#m_bautodelete) 는 **TRUE**합니다. 스레드가 종료 될 때 추가 정리를 수행 하려는 경우이 함수를 재정의 합니다. 구현 `ExitInstance` 코드를 실행 한 후에 기본 클래스의 버전을 호출 해야 합니다.  
  
##  <a name="getmainwnd"></a>CWinThread::GetMainWnd  
 OLE 서버 응용 프로그램을 사용 하는 경우 호출를 직접 참조 하는 대신 응용 프로그램의 활성 주 창에 대 한 포인터를 검색 하려면이 함수는 `m_pMainWnd` application 개체의 멤버입니다.  
  
```  
virtual CWnd* GetMainWnd();
```  
  
### <a name="return-value"></a>반환 값  
 이 함수는 두 가지 유형의 windows 중 하나에 대 한 포인터를 반환합니다. 이 함수를 반환 하는 경우 스레드 OLE 서버의 일부인 되었으며 active 컨테이너 내에 내부 활성화 하는 개체는 [CWinApp::m_pActiveWnd](../../mfc/reference/cwinapp-class.md#m_pactivewnd) 의 데이터 멤버는 `CWinThread` 개체입니다.  
  
 이 함수를 반환 하는 경우 컨테이너 내에 내부 활성화 된 개체가 없거나 응용 프로그램이 OLE 서버가 없는 경우는 [m_pMainWnd](#m_pmainwnd) 스레드 개체의 데이터 멤버입니다.  
  
### <a name="remarks"></a>주의  
 사용자 인터페이스 스레드,이 값이를 직접 참조 하는 `m_pActiveWnd` 응용 프로그램 개체의 멤버입니다.  
  
 응용 프로그램이 OLE 서버가 아닌 경우 이 함수의 호출은 응용 프로그램 개체의 `m_pMainWnd` 멤버를 직접 참조하는 것과 동일합니다.  
  
 기본 동작을 수정 하려면이 함수를 재정의 합니다.  
  
##  <a name="getthreadpriority"></a>CWinThread::GetThreadPriority  
 이 스레드의 현재 스레드 우선 순위 수준을 가져옵니다.  
  
```  
int GetThreadPriority();
```  
  
### <a name="return-value"></a>반환 값  
 해당 우선 순위 클래스 내에서 현재 스레드 우선 순위 수준입니다. 반환 되는 값은 다음 중 하나가 됩니다 순위가 가장 높은 우선 순위를 나열 합니다.  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **THREAD_PRIORITY_LOWEST**  
  
- **THREAD_PRIORITY_IDLE**  
  
 이러한 우선 순위에 대 한 자세한 내용은 참조 하십시오. [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="initinstance"></a>CWinThread::InitInstance  
 `InitInstance`재정의 하는 사용자 인터페이스 스레드의 각 새 인스턴스를 초기화 해야 합니다.  
  
```  
virtual BOOL InitInstance();
```  
  
### <a name="return-value"></a>반환 값  
 초기화에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 재정의 하는 일반적으로 `InitInstance` 스레드를 처음 만들 때 완료 해야 하는 작업을 수행할 수 있습니다.  
  
 이 멤버 함수는 사용자 인터페이스 스레드에만 사용 됩니다. 에 전달 된 제어 함수에서 작업자 스레드는 초기화를 수행 [AfxBeginThread](application-information-and-management.md#afxbeginthread)합니다.  
  
##  <a name="isidlemessage"></a>CWinThread::IsIdleMessage  
 유지 하려면이 함수를 재정의할 **OnIdle** 에서 특정 메시지를 생성 한 후 호출 합니다.  
  
```  
virtual BOOL IsIdleMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>매개 변수  
 `pMsg`  
 현재 처리 중인 메시지를 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 값 `OnIdle` 처리 후에 호출 될 메시지 하 고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현에서는 호출 하지 않는 **OnIdle** 중복 마우스 메시지 및 메시지 캐럿 깜박임에 의해 생성 된 후입니다.  
  
 응용 프로그램에서 간단한 타이머를 만든 경우 **OnIdle** 호출할지 자주 인해 성능 문제가 발생 합니다. 이러한 응용 프로그램의 성능을 향상 시키기 위해 재정의 `IsIdleMessage` 응용 프로그램의 `CWinApp`-파생 클래스를 확인 하려면 `WM_TIMER` 다음과 같이 메시지:  
  
 [!code-cpp[NVC_MFCDocView #&189;](../../mfc/codesnippet/cpp/cwinthread-class_1.cpp)]  
  
 처리 `WM_TIMER` 이런 방식의 간단한 타이머를 사용 하는 응용 프로그램의 성능이 향상 됩니다.  
  
##  <a name="m_bautodelete"></a>CWinThread::m_bAutoDelete  
 스레드 종료 시 `CWinThread` 개체를 자동으로 삭제할지 여부를 지정합니다.  
  
```  
BOOL m_bAutoDelete;  
```  
  
### <a name="remarks"></a>주의  
 `m_bAutoDelete` 데이터 멤버는 형식의 공용 변수 **BOOL**합니다.  
  
 `m_bAutoDelete`의 값은 해당 스레드 핸들이 닫히는 방식에 영향을 주지 않습니다. 스레드 핸들은 항상 `CWinThread` 개체가 소멸될 때 닫힙니다.  
  
##  <a name="m_hthread"></a>CWinThread::m_hThread  
 이에 연결 된 스레드 핸들 `CWinThread`합니다.  
  
```  
HANDLE m_hThread;  
```  
  
### <a name="remarks"></a>주의  
 `m_hThread` 데이터 멤버는 형식의 공용 변수 `HANDLE`합니다. 현재 스레드를 기본 존재 하는 경우에 유효 합니다.  
  
##  <a name="m_nthreadid"></a>CWinThread::m_nThreadID  
 이에 연결 된 스레드의 ID `CWinThread`합니다.  
  
```  
DWORD m_nThreadID;  
```  
  
### <a name="remarks"></a>주의  
 **m_nThreadID** 데이터 멤버는 형식의 공용 변수 `DWORD`합니다. 현재 스레드를 기본 존재 하는 경우에 유효 합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [AfxGetThread](application-information-and-management.md#afxgetthread)합니다.  
  
##  <a name="m_pactivewnd"></a>CWinThread::m_pActiveWnd  
 이 데이터 멤버를 사용 하 여 스레드의 활성 창 개체에 대 한 포인터를 저장 합니다.  
  
```  
CWnd* m_pActiveWnd;  
```  
  
### <a name="remarks"></a>주의  
 창에서 참조 하는 경우 Microsoft Foundation Class 라이브러리 스레드를 자동으로 종료 됩니다 `m_pActiveWnd` 닫힙니다. 이 스레드는 응용 프로그램에 대 한 주 스레드, 응용 프로그램이 종료 됩니다. 이 데이터 멤버는 경우 **NULL**, 응용 프로그램의 활성 창을 `CWinApp` 개체 상속 됩니다. `m_pActiveWnd`형식의 공용 변수 **CWnd\***합니다.  
  
 보통 설정 하면이 멤버 변수를 재정의할 때 `InitInstance`합니다. 작업자 스레드에서이 데이터 멤버의 값은 부모 스레드에서 상속 됩니다.  
  
##  <a name="m_pmainwnd"></a>CWinThread::m_pMainWnd  
 이 데이터 멤버를 사용 하 여 스레드의 주 창 개체에 대 한 포인터를 저장 합니다.  
  
```  
CWnd* m_pMainWnd;  
```  
  
### <a name="remarks"></a>주의  
 창에서 참조 하는 경우 Microsoft Foundation Class 라이브러리 스레드를 자동으로 종료 됩니다 `m_pMainWnd` 닫힙니다. 이 스레드는 응용 프로그램에 대 한 주 스레드, 응용 프로그램이 종료 됩니다. 이 데이터 멤버는 경우 **NULL**, 응용 프로그램의 주 창 `CWinApp` 개체에서 스레드를 종료 하는 시기를 결정 하는 데 사용 됩니다. `m_pMainWnd`형식의 공용 변수 **CWnd\***합니다.  
  
 보통 설정 하면이 멤버 변수를 재정의할 때 `InitInstance`합니다. 작업자 스레드에서이 데이터 멤버의 값은 부모 스레드에서 상속 됩니다.  
  
##  <a name="onidle"></a>CWinThread::OnIdle  
 유휴 시간 처리를 수행 하려면이 멤버 함수를 재정의 합니다.  
  
```  
virtual BOOL OnIdle(LONG lCount);
```  
  
### <a name="parameters"></a>매개 변수  
 `lCount`  
 카운터 될 때마다 증가 `OnIdle` 는 스레드의 메시지 큐가 비어 있을 경우 호출 됩니다. 이 횟수가 새 메시지가 처리 될 때마다 0으로 재설정 됩니다. 사용할 수는 `lCount` 매개 변수에 지정 된 상대적 기간 동안 메시지를 처리 하지 않고 스레드는 유휴 상태 였습니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아니면 받을 더 유휴 처리 시간입니다. 유휴 처리 시간을 더 이상 필요한 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 `OnIdle`스레드의 메시지 큐가 비어 있을 경우 기본 메시지 루프에서 호출 됩니다. 재정의 사용 하 여 사용자 고유의 배경 유휴 처리기 작업을 호출.  
  
 `OnIdle`유휴 처리 시간이 없는 추가로 필요한 임을 나타내려면 0을 반환 해야 합니다. `lCount` 매개 변수는 각 시간 증가 `OnIdle` 메시지 큐가 비어 있고 새 메시지를 처리할 때마다 0으로 다시 설정 될 때 호출 됩니다. 이 수를 기반으로 하 여 다른 유휴 루틴을 호출할 수 있습니다.  
  
 이 멤버 함수의 기본 구현은 임시 개체와 사용 하지 않는 동적 연결 라이브러리에서 메모리를 해제합니다.  
  
 이 멤버 함수는 사용자 인터페이스 스레드에만 사용 됩니다.  
  
 응용 프로그램까지 메시지를 처리할 수 없습니다 때문에 `OnIdle` 반환 되 면이 함수에서 시간이 오래 걸리는 작업을 수행 하지 마십시오.  
  
##  <a name="operator_handle"></a>CWinThread::operator 핸들  
 핸들을 검색 된 `CWinThread` 개체입니다.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 스레드 개체가;의 핸들 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 Windows Api를 직접 호출 하려면 핸들을 사용 합니다.  
  
##  <a name="postthreadmessage"></a>CWinThread::PostThreadMessage  
 다른 사용자 정의 메시지를 게시 하기 위해 호출 `CWinThread` 개체입니다.  
  
```  
BOOL PostThreadMessage(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam);
```  
  
### <a name="parameters"></a>매개 변수  
 `message`  
 사용자 정의 메시지의 ID입니다.  
  
 `wParam`  
 첫 번째 메시지 매개 변수입니다.  
  
 `lParam`  
 두 번째 메시지 매개 변수입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 메시지 맵 매크로 의해 게시 된 메시지를 적절 한 메시지 처리기에 매핑되어 `ON_THREAD_MESSAGE`합니다.  
  
> [!NOTE]
>  Windows를 호출 하는 경우 [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946) 함수 MFC 응용 프로그램에서 MFC 메시지 처리기는 호출 되지 않습니다. 자세한 내용은 기술 자료 문서, "PRB:: MFC 메시지 처리기 하지 호출 된 PostThreadMessage()" (Q142415)을 참조 하십시오.  
  
##  <a name="pretranslatemessage"></a>CWinThread::PreTranslateMessage  
 창 메시지를 필터링 하려면이 함수를 재정의 하 여 Windows 함수에 디스패치 되기 전에 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934)합니다.  
  
```  
virtual BOOL PreTranslateMessage(MSG* pMsg);
```  
  
### <a name="parameters"></a>매개 변수  
 `pMsg`  
 가리키는 [MSG 구조체](../../mfc/reference/msg-structure1.md) 처리할 메시지를 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 메시지에서 완전히 처리 된 경우&0;이 아닌 `PreTranslateMessage` 하며 추가로 처리할 수 없습니다. 일반적인 방법으로 메시지를 처리 해야 하면&0;입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 사용자 인터페이스 스레드에만 사용 됩니다.  
  
##  <a name="processmessagefilter"></a>CWinThread::ProcessMessageFilter  
 프레임 워크의 후크 함수는 필터링 하 고 특정 Windows 메시지에 응답 하려면이 멤버 함수를 호출 합니다.  
  
```  
virtual BOOL ProcessMessageFilter(
    int code,  
    LPMSG lpMsg);
```  
  
### <a name="parameters"></a>매개 변수  
 `code`  
 후크 코드가 지정합니다. 이 멤버 함수는 코드를 사용 하 여 처리 하는 방법을 확인 하려면`lpMsg.`  
  
 `lpMsg`  
 Windows에 대 한 포인터 [MSG 구조체](../../mfc/reference/msg-structure1.md)합니다.  
  
### <a name="return-value"></a>반환 값  
 메시지를 처리 합니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 응용 프로그램의 일반 메시지를 보내기 전에 이벤트를 처리 하는 후크 함수를 처리 합니다.  
  
 이 고급 기능을 재정의 하는 경우 사용할 프레임 워크의 유지 관리 하는 기본 클래스 버전을 호출 해야 처리를 연결 합니다.  
  
##  <a name="processwndprocexception"></a>CWinThread::ProcessWndProcException  
 프레임 워크는 처리기 스레드의 메시지 또는 명령 처리기 중 하나에서 throw 된 예외를 catch 하지 않습니다 될 때마다이 멤버 함수를 호출 합니다.  
  
```  
virtual LRESULT ProcessWndProcException(
    CException* e,  
    const MSG* pMsg);
```  
  
### <a name="parameters"></a>매개 변수  
 *e*  
 처리 되지 않은 예외를 가리킵니다.  
  
 `pMsg`  
 가리키는 [MSG 구조체](../../mfc/reference/msg-structure1.md) 프레임 워크에 예외를 발생 시킨 windows 메시지에 대 한 정보를 포함 하 합니다.  
  
### <a name="return-value"></a>반환 값  
 -1을 반환 된 `WM_CREATE` 예외가 생성 됩니다; 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수를 직접 호출 하지 마십시오.  
  
 이 멤버 함수를 기본 구현에는 다음과 같은 메시지에서 생성 된 예외가 있을 때만 처리 합니다.  
  
|명령|작업|  
|-------------|------------|  
|`WM_CREATE`|실패 합니다.|  
|`WM_PAINT`|다른 하지 못하도록 하는 영향을 받는 창의 유효성을 검사 `WM_PAINT` 메시지 생성 되지 않도록 합니다.|  
  
 글로벌 사용자 예외 처리를 제공 하려면이 멤버 함수를 재정의 합니다. 기본 동작을 표시 하려는 경우에 기본 기능을 호출 합니다.  
  
 이 멤버 함수는 메시지 펌프가 스레드에만 사용 됩니다.  
  
##  <a name="pumpmessage"></a>CWinThread::PumpMessage  
 스레드의 메시지 루프를 포함합니다.  
  
```  
virtual BOOL PumpMessage();
```  
  
### <a name="remarks"></a>주의  
 `PumpMessage`스레드의 메시지 루프를 포함합니다. **PumpMessage** 호출한 `CWinThread` 스레드의 메시지 펌프를 합니다. 호출할 수 있습니다 `PumpMessage` 직접 처리할 메시지를 강제로 하거나 재정의할 수 있습니다 `PumpMessage` 해당 기본 동작을 변경 합니다.  
  
 호출 `PumpMessage` 직접 및 고급 사용자만 해당 기본 동작 재정의 권장 합니다.  
  
##  <a name="resumethread"></a>CWinThread::ResumeThread  
 호출 하 여 일시 중단 된 스레드의 실행을 다시 시작 하는 [있는 경우 SuspendThread](#suspendthread) 멤버 함수를 또는로 만든 스레드는 **CREATE_SUSPENDED** 플래그입니다.  
  
```  
DWORD ResumeThread();
```  
  
### <a name="return-value"></a>반환 값  
 스레드의 이전 일시 중단 횟수가 성공 하면 `0xFFFFFFFF` 그렇지 않은 경우. 반환 값이&0; 이면 현재 스레드의 일시 중단 하지 했습니다. 반환 값이&1; 이면 스레드가 일시 중단 되지만 다시 시작 됩니다. 스레드는 한 가지 방법은 보다 큰 모든 반환 값이 상태로 유지 됩니다.  
  
### <a name="remarks"></a>주의  
 현재 스레드의 일시 중단 횟수가 하나씩 감소 합니다. Suspend 수가 감소 하는 경우 스레드를&0;으로, 실행을 다시 시작 그렇지 않으면 스레드가 상태로 유지 됩니다.  
  
##  <a name="run"></a>CWinThread::Run  
 사용자 인터페이스 스레드에 대 한 기본 메시지 루프를 제공합니다.  
  
```  
virtual int Run();
```  
  
### <a name="return-value"></a>반환 값  
 `int` 스레드에 의해 반환 되는 값입니다. 호출 하 여이 값을 검색할 수 [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190)합니다.  
  
### <a name="remarks"></a>주의  
 **실행** 획득 및 응용 프로그램을 받을 때까지 Windows 메시지를 디스패치는 [WM_QUIT](http://msdn.microsoft.com/library/windows/desktop/ms632641) 메시지입니다. 스레드의 메시지 큐에 현재 없는 메시지를 포함 하는 경우 **실행** 호출 `OnIdle` 유휴 시간 처리를 수행 합니다. 들어오는 메시지 이동은 [PreTranslateMessage](#pretranslatemessage) 특수 한 처리 한 후 Windows 함수에 멤버 함수 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 표준 키보드 번역에 대 한 합니다. 마지막으로 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수를 호출 합니다.  
  
 **실행** 대부분 재정의 하지만 특별 한 동작을 구현 하도록 재정의할 수 있습니다.  
  
 이 멤버 함수는 사용자 인터페이스 스레드에만 사용 됩니다.  
  
##  <a name="setthreadpriority"></a>CWinThread::SetThreadPriority  
 이 함수는 해당 우선 순위 클래스 내에서 현재 스레드의 우선 순위 수준을 설정합니다.  
  
```  
BOOL SetThreadPriority(int nPriority);
```  
  
### <a name="parameters"></a>매개 변수  
 `nPriority`  
 해당 우선 순위 클래스 내에서 새 스레드 우선 순위 수준을 지정합니다. 이 매개 변수는 순위가 가장 높은 우선 순위를 나열 하는 다음 값 중 하나 여야 합니다.  
  
- **THREAD_PRIORITY_TIME_CRITICAL**  
  
- **THREAD_PRIORITY_HIGHEST**  
  
- **THREAD_PRIORITY_ABOVE_NORMAL**  
  
- **THREAD_PRIORITY_NORMAL**  
  
- **THREAD_PRIORITY_BELOW_NORMAL**  
  
- **THREAD_PRIORITY_LOWEST**  
  
- **THREAD_PRIORITY_IDLE**  
  
 이러한 우선 순위에 대 한 자세한 내용은 참조 하십시오. [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 함수에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 후에 호출할 수 [CreateThread](#createthread) 성공적으로 반환 합니다.  
  
##  <a name="suspendthread"></a>CWinThread::SuspendThread  
 현재 증가 스레드의 개수를 일시 중단 합니다.  
  
```  
DWORD SuspendThread();
```  
  
### <a name="return-value"></a>반환 값  
 스레드의 이전 일시 중단 횟수가 성공 하면 `0xFFFFFFFF` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 모든 스레드는 일시 중단 횟수가&0; 이상 있으면 해당 스레드가 실행 되지 않습니다. 스레드를 호출 하 여 다시 시작할 수 있습니다는 [ResumeThread](#resumethread) 멤버 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWinApp 클래스](../../mfc/reference/cwinapp-class.md)   
 [CCmdTarget 클래스](../../mfc/reference/ccmdtarget-class.md)

