---
title: "다중 스레딩: 스레드 종료 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CREATE_SUSPENDED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxEndThread 메서드"
  - "다중 스레딩[C++], 스레드 종료"
  - "스레드 완전 종료"
  - "스레드 시작"
  - "스레드 중지"
  - "스레드 종료"
  - "스레딩[C++], 스레드 중지"
  - "스레딩[MFC], 스레드 종료"
ms.assetid: 4c0a8c6d-c02f-456d-bd02-0a8c8d006ecb
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 다중 스레딩: 스레드 종료
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

제어 함수가 끝나거나 스레드 실행을 완료할 수 없는 경우 스레드는 정상적으로 종료됩니다.  워드 프로세서에서 백그라운드 인쇄를 수행하는 데 스레드를 사용한 경우 인쇄가 성공적으로 완료되면 제어 함수는 정상적으로 종료됩니다.  그러나 인쇄 작업을 취소하면 백그라운드 인쇄 스레드가 완전 종료되어야 합니다.  이 항목에서는 각 상황을 구현하는 방법과 스레드가 종료된 후 스레드의 종료 코드를 가져오는 방법에 대해 설명합니다.  
  
-   [정상적인 스레드 종료](#_core_normal_thread_termination)  
  
-   [스레드 완전 종료](#_core_premature_thread_termination)  
  
-   [스레드의 종료 코드 검색](#_core_retrieving_the_exit_code_of_a_thread)  
  
##  <a name="_core_normal_thread_termination"></a> 정상적인 스레드 종료  
 작업자 스레드의 경우 정상적인 스레드 종료는 간단합니다. 제어 함수를 끝내고 종료 이유를 나타내는 값을 반환하면 됩니다.  [AfxEndThread](../Topic/AfxEndThread.md) 함수 또는 `return` 문을 사용할 수 있습니다.  일반적으로 0을 사용하여 제대로 완료된 경우를 나타내지만 이 값은 사용자가 변경할 수도 있습니다.  
  
 사용자 인터페이스 스레드의 경우도 프로세스는 간단합니다. 사용자 인터페이스 스레드 내에서 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]의 [PostQuitMessage](http://msdn.microsoft.com/library/windows/desktop/ms644945)를 호출합니다.  **PostQuitMessage**가 사용하는 매개 변수는 스레드의 종료 코드뿐입니다.  작업자 스레드와 마찬가지로 0을 사용하여 제대로 완료된 경우를 나타냅니다.  
  
##  <a name="_core_premature_thread_termination"></a> 스레드 완전 종료  
 스레드를 완전히 종료시키는 프로세스도 간단합니다. 스레드에서 [AfxEndThread](../Topic/AfxEndThread.md)를 호출하면 됩니다.  원하는 종료 코드를 단일 매개 변수에 전달합니다.  이렇게 하면 스레드 실행이 중단되고, 스레드의 스택이 할당 해제되고, 스레드에 링크된 모든 DLL이 분리되고, 스레드 개체가 메모리에서 삭제됩니다.  
  
 `AfxEndThread`는 종료될 스레드 내에서 호출해야 합니다.  스레드를 다른 스레드에서 종료시키려면 두 스레드 사이에 통신 방법을 설정해야 합니다.  
  
##  <a name="_core_retrieving_the_exit_code_of_a_thread"></a> 스레드의 종료 코드 검색  
 작업자 스레드 또는 사용자 인터페이스 스레드의 종료 코드를 가져오려면 [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190) 함수를 호출합니다.  이 함수에 대한 자세한 내용은 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]를 참조하십시오.  이 함수는 `CWinThread` 개체의 `m_hThread` 데이터 멤버에 저장된 스레드에 대한 핸들과 `DWORD` 주소를 사용합니다.  
  
 스레드가 여전히 활성 상태이면 **GetExitCodeThread**는 제공된 `DWORD` 주소에 **STILL\_ACTIVE**를 표시합니다. 그렇지 않으면 종료 코드가 이 주소에 표시됩니다.  
  
 [CWinThread](../mfc/reference/cwinthread-class.md) 개체의 종료 코드를 검색하려면 한 단계를 추가로 수행합니다.  기본적으로 `CWinThread` 스레드가 종료되면 스레드 개체는 삭제됩니다.  이것은 `CWinThread` 개체가 더 이상 존재하지 않으므로 `m_hThread` 데이터 멤버에 액세스할 수 없음을 의미합니다.  이 상황을 방지하려면 다음 중 하나를 수행하십시오.  
  
-   `m_bAutoDelete` 데이터 멤버를 **FALSE**로 설정합니다.  이렇게 하면 스레드가 종료된 후에도 `CWinThread` 개체가 계속 존재할 수 있으므로  `m_hThread` 데이터 멤버에 액세스할 수 있습니다.  그러나 이 기법을 사용하면 프레임워크에서 자동으로 `CWinThread` 개체를 삭제하지 않으므로 사용자가 직접 소멸시켜야 합니다.  이것이 더 좋은 방법입니다.  
  
-   스레드의 핸들을 별도로 저장합니다.  스레드를 만든 다음 **::DuplicateHandle**로 `m_hThread` 데이터 멤버를 다른 변수에 복사하여 이 변수를 통해 액세스합니다.  이렇게 하면 스레드가 종료할 때 자동으로 개체가 삭제되지만 스레드가 종료된 이유를 알 수 있습니다.  핸들을 복제하기 전에 스레드가 종료되지 않도록 주의하십시오.  이 작업을 가장 안전하게 수행하는 방법은 **CREATE\_SUSPENDED**를 [AfxBeginThread](../Topic/AfxBeginThread.md)에 전달하고 핸들을 저장한 다음 [ResumeThread](../Topic/CWinThread::ResumeThread.md)를 호출하여 스레드를 다시 시작하는 것입니다.  
  
 두 방법 중 하나를 사용하여 `CWinThread` 개체가 종료된 이유를 확인할 수 있습니다.  
  
## 참고 항목  
 [C\+\+ 및 MFC에서 다중 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)   
 [\_endthread, \_endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)   
 [\_beginthread, \_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659)