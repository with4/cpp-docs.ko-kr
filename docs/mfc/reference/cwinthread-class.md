---
title: "CWinThread Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinThread 클래스"
  - "스레딩[MFC], 스레드 만들기"
  - "스레딩[MFC], 안전성"
  - "작업자 스레드"
ms.assetid: 10cdc294-4057-4e76-ac7c-a8967a89af0b
caps.latest.revision: 24
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinThread Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

응용 프로그램 내의 실행 스레드를 나타냅니다.  
  
## 구문  
  
```  
class CWinThread : public CCmdTarget  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CWinThread::CWinThread](../Topic/CWinThread::CWinThread.md)|`CWinThread` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CWinThread::CreateThread](../Topic/CWinThread::CreateThread.md)|실행이 시작 되는 `CWinThread` 개체입니다.|  
|[CWinThread::ExitInstance](../Topic/CWinThread::ExitInstance.md)|스레드가 종료 되 면 정리 하도록 재정의 하십시오입니다.|  
|[CWinThread::GetMainWnd](../Topic/CWinThread::GetMainWnd.md)|스레드 창에 대 한 포인터를 검색합니다.|  
|[CWinThread::GetThreadPriority](../Topic/CWinThread::GetThreadPriority.md)|현재 스레드의 우선 순위를 가져옵니다.|  
|[CWinThread::InitInstance](../Topic/CWinThread::InitInstance.md)|스레드 인스턴스 초기화를 수행 하도록 재정의 됩니다.|  
|[CWinThread::IsIdleMessage](../Topic/CWinThread::IsIdleMessage.md)|특별 한 메시지를 확인 합니다.|  
|[CWinThread::OnIdle](../Topic/CWinThread::OnIdle.md)|스레드별 유휴 시간 처리를 수행 하도록 재정의 됩니다.|  
|[CWinThread::PostThreadMessage](../Topic/CWinThread::PostThreadMessage.md)|다른 메시지는 `CWinThread` 개체입니다.|  
|[CWinThread::PreTranslateMessage](../Topic/CWinThread::PreTranslateMessage.md)|메시지를 Windows 함수를 디스패치하기 전에 필터링  [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및  [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934).|  
|[CWinThread::ProcessMessageFilter](../Topic/CWinThread::ProcessMessageFilter.md)|이러한 응용 프로그램에 도달 하기 전에 특정 메시지를 차단 합니다.|  
|[CWinThread::ProcessWndProcException](../Topic/CWinThread::ProcessWndProcException.md)|스레드의 메시지와 명령 처리기에서 throw 된 모든 처리 되지 않은 예외를 차단 합니다.|  
|[CWinThread::PumpMessage](../Topic/CWinThread::PumpMessage.md)|스레드의 메시지 루프가 포함 되어 있습니다.|  
|[CWinThread::ResumeThread](../Topic/CWinThread::ResumeThread.md)|스레드의 감소 시킵니다 카운트를 일시 중단합니다.|  
|[CWinThread::Run](../Topic/CWinThread::Run.md)|제어 함수에 메시지 펌프 스레드입니다.  사용자 기본 메시지 루프를 재정의 합니다.|  
|[CWinThread::SetThreadPriority](../Topic/CWinThread::SetThreadPriority.md)|현재 스레드의 우선 순위를 설정합니다.|  
|[CWinThread::SuspendThread](../Topic/CWinThread::SuspendThread.md)|증가 한 스레드의 개수를 일시 중단합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CWinThread::operator HANDLE](../Topic/CWinThread::operator%20HANDLE.md)|핸들의 검색은 `CWinThread` 개체입니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CWinThread::m\_bAutoDelete](../Topic/CWinThread::m_bAutoDelete.md)|개체 스레드 종료 시 삭제 여부를 지정 합니다.|  
|[CWinThread::m\_hThread](../Topic/CWinThread::m_hThread.md)|현재 스레드를 처리 합니다.|  
|[CWinThread::m\_nThreadID](../Topic/CWinThread::m_nThreadID.md)|현재 스레드의 ID입니다.|  
|[CWinThread::m\_pActiveWnd](../Topic/CWinThread::m_pActiveWnd.md)|OLE 서버를 현재 위치에서 활성화 될 때 컨테이너 응용 프로그램의 주 창에 대 한 포인터입니다.|  
|[CWinThread::m\_pMainWnd](../Topic/CWinThread::m_pMainWnd.md)|응용 프로그램의 주 창으로 포인터를 보유합니다.|  
  
## 설명  
 실행의 주 스레드에서 파생 개체에서 일반적으로 제공 됩니다 `CWinApp`.  `CWinApp`파생 된 `CWinThread`.  추가 `CWinThread` 개체를 지정 된 응용 프로그램 내에서 여러 스레드가 있습니다.  
  
 두 가지 유형의 스레드를 가지는 `CWinThread` 지원: 작업자 스레드와 사용자 인터페이스 스레드입니다.  작업자 스레드 메시지 펌프 없습니다 있습니다: 예를 들어, 배경 계산 스프레드시트 응용 프로그램에서 스레드.  사용자 인터페이스 스레드 메시지 펌프가 및 시스템에서 받은 메시지를 처리 합니다.  [CWinApp](../../mfc/reference/cwinapp-class.md) 및 여기에서 파생 된 클래스는 스레드 사용자 인터페이스의 예입니다.  직접 다른 사용자 인터페이스 스레드의 파생 될 수 `CWinThread`.  
  
 개체 클래스의 `CWinThread` 스레드 기간 동안 일반적으로 발생 합니다.  이 동작을 수정 하 고 싶다면 설정  [m\_bAutoDelete](../Topic/CWinThread::m_bAutoDelete.md) 에  **거짓**.  
  
 `CWinThread` 클래스는 MFC 코드와 완전 한 스레드 안전 확인 해야 합니다.  스레드 로컬 데이터 프레임 워크에서 사용 되는 스레드 관련 정보를 유지 관리 하는 것으로 `CWinThread` 개체입니다.  이에 대 한이 종속성 때문에 `CWinThread` 스레드 로컬 데이터를 처리 하기 위해 MFC를 사용 하 여 모든 스레드 MFC에서 만들어야 합니다.  예를 들어, 런타임 함수에 의해 만들어진 스레드  [\_beginthread, \_beginthreadex](../../c-runtime-library/reference/beginthread-beginthreadex.md) 는 MFC Api를 사용할 수 없습니다.  
  
 호출 스레드를 만들 수  [AfxBeginThread](../Topic/AfxBeginThread.md).  사용자 인터페이스 또는 작업자 스레드를 사용할 것인지에 따라 두 폼입니다.  사용자 인터페이스 스레드를 사용할 경우 전달 `AfxBeginThread` 에 대 한 포인터는 `CRuntimeClass` 의 `CWinThread`\-클래스를 파생 합니다.  작업자 스레드를 만들 경우 전달 `AfxBeginThread` 제어 함수 및 매개 변수를 제어 하는 함수에 대 한 포인터입니다.  작업자 스레드 및 스레드 사용자 인터페이스에 대 한 우선 순위, 쌓기, 생성 플래그 및 보안 특성을 수정 하는 선택적 매개 변수를 지정할 수 있습니다.  `AfxBeginThread`포인터를 새 반환 합니다 `CWinThread` 개체입니다.  
  
 대신 전화 `AfxBeginThread`을 만들 수 있습니다는 `CWinThread`\-파생 개체 및 다음 호출 `CreateThread`.  이 2 단계 생성 방법을 다시 사용 하려는 경우에 유용의 `CWinThread` 개체 간의 연속 생성과 종료 스레드 실행 합니다.  
  
 에 대 한 자세한 내용은 `CWinThread`, 문서를 참조 하십시오.  [C\+\+ 및 MFC 다중 스레딩](../../parallel/multithreading-with-cpp-and-mfc.md),  [다중 스레딩: 사용자 인터페이스 스레드 만들기](../../parallel/multithreading-creating-user-interface-threads.md),  [다중 스레딩: 작업자 스레드 만들기](../../parallel/multithreading-creating-worker-threads.md), 및  [다중 스레딩: 동기화 클래스 사용 방법](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CWinThread`  
  
## 요구 사항  
 **헤더:** afxwin.h  
  
## 참고 항목  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)