---
title: "다중 스레딩: 작업자 스레드 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- multithreading [C++], worker threads
- background tasks [C++]
- threading [C++], worker threads
- worker threads [C++]
- threading [C++], creating threads
- threading [MFC], worker threads
- threading [C++], user input not required
ms.assetid: 670adbfe-041c-4450-a3ed-be14aab15234
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 94a047de82bebb03f681e1bfdf6f68d56554fe8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="multithreading-creating-worker-threads"></a>다중 스레딩: 작업자 스레드 만들기
작업자 스레드는 대개 사용자 응용 프로그램을 사용 하 여 계속 기다려야 없어야 하는 백그라운드 작업을 처리 합니다. 다시 계산 작업 하면서 인쇄 등의 작업은 작업자 스레드 수의 좋은 예입니다. 이 항목에서 작업자 스레드를 만드는 데 필요한 단계를 자세히 설명 합니다. 다음과 같은 내용을 다룹니다.  
  
-   [스레드 시작](#_core_starting_the_thread)  
  
-   [제어 함수를 구현합니다.](#_core_implementing_the_controlling_function)  
  
-   [예제](#_core_controlling_function_example)  
  
 작업자 스레드를 만드는 상대적으로 간단한 작업입니다. 두 단계만 수행 하면 스레드를 실행 하는 데 필요한: 제어 함수를 구현 하 고 스레드를 시작 합니다. 클래스를 파생 시켜 필요한 경우가 아니라면 [CWinThread](../mfc/reference/cwinthread-class.md)합니다. 특수 한 버전의 경우에 클래스를 파생 시켜 `CWinThread`, 있지만 대부분의 간단한 작업자 스레드에 대 한 필요는 없습니다. 사용할 수 있습니다 `CWinThread` 수정 하지 않고 있습니다.  
  
##  <a name="_core_starting_the_thread"></a>스레드 시작  
 두 가지 오버 로드 된 버전의 `AfxBeginThread`: 작업자 스레드를 만들 수 있는 고 다른 하나는 사용자 인터페이스 스레드와 작업자 스레드를 만들 수 있습니다. 첫 번째 오버 로드를 사용 하 여 작업자 스레드의 실행을 시작 하려면 호출 [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread), 다음 정보를 제공 합니다.  
  
-   주소 제어 함수입니다.  
  
-   제어 함수에 전달할 매개 변수입니다.  
  
-   (선택 사항) 스레드의 원하는 우선 순위입니다. 기본값은 보통 우선 순위입니다. 사용 가능한 우선 순위 수준에 대 한 자세한 내용은 참조 [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277) 에 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]합니다.  
  
-   (선택 사항) 스레드에 대 한 원하는 스택 크기입니다. 기본값은 만드는 스레드와 같은 크기 스택.  
  
-   (선택 사항) **CREATE_SUSPENDED** 스레드 일시 중단 된 상태로 만들 수를 선택 합니다. 기본값은 0으로, 또는 스레드를 정상적으로 시작 합니다.  
  
-   (선택 사항) 원하는 보안 특성입니다. 기본값은 부모 스레드는 동일한 액세스 권한을 부여 합니다. 이 보안 정보는 형식에 대 한 자세한 내용은 참조 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) 에 [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)]합니다.  
  
 `AfxBeginThread`만들고 초기화는 `CWinThread` 개체를 시작 하며 나중에 참조할 수 있도록 주소를 반환 합니다. 모든 개체가 제대로 할당 해제 생성 부분이 실패 해야 되도록 전체 프로시저에서 검사가 수행 됩니다.  
  
##  <a name="_core_implementing_the_controlling_function"></a>제어 함수를 구현합니다.  
 제어 함수는 스레드를 정의 합니다. 이 함수를 입력 한 경우 스레드가 시작 되 고 스레드가 종료 되 고 종료 합니다. 이 함수는 다음과 같은 프로토타입이 있어야 합니다.  
  
```  
UINT MyControllingFunction( LPVOID pParam );  
```  
  
 단일 값입니다. 이 매개 변수 (에서) 함수를 받는 값에는 스레드 개체를 만들 때 생성자에 전달 된 값이입니다. 제어 함수를 선택 하는 어떤 방식으로이 값을 해석할 수 있습니다. 여러 매개 변수를 포함 하는 구조체에 대 한 포인터 또는 스칼라 값으로 처리 될 수 또는 무시 될 수 있습니다. 매개 변수 구조체를 가리키는 경우 데이터를 전달 하는 호출자에서 스레드를 뿐만 아니라 스레드에서 다시 호출자에 게 데이터를 전달 하는 구조를 사용할 수 있습니다. 이러한 구조체를 사용 하 여 데이터를 다시 호출자에 게 전달 하는 경우 스레드 결과가 준비 되 면 호출자에 게 있어야 합니다. 호출자에 게 작업자 스레드에서 통신 하는 방법에 대 한 정보를 참조 하십시오. [다중 스레딩: 프로그래밍 팁](../parallel/multithreading-programming-tips.md)합니다.  
  
 함수가 종료 되 면 반환 해야는 **UINT** 종료 이유를 나타내는 값입니다. 일반적으로이 종료 코드는 성공을 표시 하기 위해 여러 종류의 오류를 나타내는 다른 값으로 0입니다. 이것은 종속 구현 합니다. 일부 스레드 개체의 사용 횟수를 유지 관리 하 고 사용 하 여 해당 개체의 현재 수를 반환할 수 있습니다. 응용 프로그램에서이 값을 검색 하는 방법을 알아보려면 참조 [다중 스레딩: 스레드 종료](../parallel/multithreading-terminating-threads.md)합니다.  
  
 MFC 라이브러리로 작성 된 다중 스레드 프로그램에서 수행할 수 있는 몇 가지 제한 사항이 있습니다. 참조에 대 한 이러한 제한 사항 및 기타 팁 스레드를 사용 하는 방법에 대 한 설명은 [다중 스레딩: 프로그래밍 팁](../parallel/multithreading-programming-tips.md)합니다.  
  
##  <a name="_core_controlling_function_example"></a>제어 함수 예제  
 다음 예제에서는 제어 함수를 정의 하는 프로그램의 다른 부분에서 사용 하는 방법을 보여 줍니다.  
  
```  
UINT MyThreadProc( LPVOID pParam )  
{  
    CMyObject* pObject = (CMyObject*)pParam;  
  
    if (pObject == NULL ||  
        !pObject->IsKindOf(RUNTIME_CLASS(CMyObject)))  
    return 1;   // if pObject is not valid  
  
    // do something with 'pObject'  
  
    return 0;   // thread completed successfully  
}  
  
// inside a different function in the program  
.  
.  
.  
pNewObject = new CMyObject;  
AfxBeginThread(MyThreadProc, pNewObject);  
.  
.  
.  
```  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [다중 스레딩: 사용자 인터페이스 스레드 만들기](../parallel/multithreading-creating-user-interface-threads.md)  
  
## <a name="see-also"></a>참고 항목  
 [C++ 및 MFC에서 다중 스레딩](../parallel/multithreading-with-cpp-and-mfc.md)