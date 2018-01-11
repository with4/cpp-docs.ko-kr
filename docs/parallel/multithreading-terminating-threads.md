---
title: "다중 스레딩: 스레드 종료 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CREATE_SUSPENDED
dev_langs: C++
helpviewer_keywords:
- premature thread termination
- starting threads
- threading [MFC], terminating threads
- multithreading [C++], terminating threads
- threading [C++], stopping threads
- terminating threads
- stopping threads
- AfxEndThread method
ms.assetid: 4c0a8c6d-c02f-456d-bd02-0a8c8d006ecb
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8017d47f632374d8979d9a0850e1d1bfd8b9df07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-terminating-threads"></a>다중 스레딩: 스레드 종료
두 가지 일반적인 문제 때문 스레드가 종료: 제어 함수 종료 또는 스레드 실행을 완료할 수 없습니다. 백그라운드 인쇄를 위해 스레드를 사용 하는 워드 프로세서를 제어 하는 함수는 정상적으로 종료 성공적으로 완료 된 인쇄 하는 경우. 그러나 사용자가 인쇄 작업을 취소, 백그라운드 인쇄 스레드가 완전히 종료 되어야 합니다. 이 항목에는 각 상황을 구현 하는 방법 및 종료 된 후 스레드 종료 코드를 가져오는 방법을 모두 설명 합니다.  
  
-   [정상적인 스레드 종료](#_core_normal_thread_termination)  
  
-   [스레드 완전 종료](#_core_premature_thread_termination)  
  
-   [스레드 종료 코드를 검색합니다.](#_core_retrieving_the_exit_code_of_a_thread)  
  
##  <a name="_core_normal_thread_termination"></a>정상적인 스레드 종료  
 작업자 스레드에 대 한 일반 스레드 종료는 간단: 제어 함수를 종료 하 고 종료 이유를 나타내는 값을 반환 합니다. 하나를 사용할 수는 [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) 함수 또는 `return` 문. 일반적으로 0을 성공적으로 완료를 사용 하지만 사용자의 책임입니다.  
  
 사용자 인터페이스 스레드는 프로세스를 단순하게:에서 호출 하는 사용자 인터페이스 스레드 내에서 [경우도](http://msdn.microsoft.com/library/windows/desktop/ms644945) 에 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]합니다. 유일한 매개 변수는 **경우도** 하나 스레드 종료 코드입니다. 작업자 스레드 마찬가지로 0을 사용 하 여 성공적으로 완료 된 경우를 나타냅니다.  
  
##  <a name="_core_premature_thread_termination"></a>스레드 완전 종료  
 스레드를 완전히 종료 하는 것은 간단: 호출 [AfxEndThread](../mfc/reference/application-information-and-management.md#afxendthread) 에서 스레드 내에서. 원하는 종료 코드를 유일한 매개 변수로 전달 합니다. 이 스레드의 실행이 중지 되, 스레드의 스택 할당을 취소, 분리 하는 스레드에 연결 된 모든 Dll 및 스레드 개체가 메모리에서 삭제 합니다.  
  
 `AfxEndThread`스레드 종료 내에서 호출 되어야 합니다. 다른 스레드의 스레드를 종료 하려면 두 스레드 간의 통신 방법을 설정 해야 합니다.  
  
##  <a name="_core_retrieving_the_exit_code_of_a_thread"></a>스레드 종료 코드를 검색합니다.  
 사용자 인터페이스 스레드 또는 작업자의 종료 코드를 가져오려면 호출는 [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190) 함수입니다. 이 함수에 대 한 정보를 참조 하십시오.는 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]합니다. 이 함수는 스레드에 대 한 핸들을 사용 (에 저장 된는 `m_hThread` 데이터 멤버의 `CWinThread` 개체)의 주소는 `DWORD`합니다.  
  
 스레드가 아직 활성 상태인 경우 **GetExitCodeThread** 배치 **STILL_ACTIVE** 에 제공 된 `DWORD` 주소; 이외에 종료 코드는이 주소에 배치 합니다.  
  
 검색의 종료 코드 [CWinThread](../mfc/reference/cwinthread-class.md) 개체는 추가 단계를 사용 합니다. 기본적으로 때는 `CWinThread` 스레드가 종료, 스레드 개체를 삭제 합니다. 즉, 액세스할 수 없습니다는 `m_hThread` 데이터 멤버 때문에 `CWinThread` 개체가 없습니다. 이러한 상황을 방지 하려면 다음 중 하나를 수행 합니다.  
  
-   설정의 `m_bAutoDelete` 데이터 멤버를 **FALSE**합니다. 이 통해는 `CWinThread` 스레드가 종료 된 후 생존 하는 개체입니다. 에 액세스할 수 있습니다는 `m_hThread` 스레드가 종료 된 후 데이터 멤버입니다. 하지만이 기법을 사용 모르는 경우 제거 해야는 `CWinThread` 프레임 워크는 삭제 하지 않으므로 자동으로 사용자에 대 한 개체입니다. 이것은 기본 방법입니다.  
  
-   스레드 핸들을 별도로 저장 합니다. 스레드를 만든 후 복사 해당 `m_hThread` 데이터 멤버 (사용 하 여 **:: DuplicateHandle**)를 다른 변수에 해당 변수를 통해 액세스 합니다. 이러한 방식으로 개체 있습니다 수 이유를 알에 스레드가 종료 종료할 때 자동으로 삭제 됩니다. 스레드 핸들을 복제 하기 전에 종료 되지 않도록 주의 해야 합니다. 이 작업을 수행 하는 가장 안전한 방법은 전달 하는 **CREATE_SUSPENDED** 를 [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), 핸들을 저장 하 고 호출 하 여 스레드가 다시 [ResumeThread](../topic/../mfc/reference/cwinthread-class.md#resumethread)합니다.  
  
 두 방법 중 하나를 사용 하면 이유를 확인 하는 `CWinThread` 개체가 종료 된 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + + 및 MFC를 사용한 다중 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)   
 [_endthread, _endthreadex](../c-runtime-library/reference/endthread-endthreadex.md)   
 [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659)