---
title: "다중 스레딩: 작업자 스레드 만들기 | Microsoft Docs"
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
  - "백그라운드 작업[C++]"
  - "다중 스레딩[C++], 작업자 스레드"
  - "스레딩[C++], 스레드 만들기"
  - "스레딩[C++], 사용자 입력 필요 없음"
  - "스레딩[C++], 작업자 스레드"
  - "스레딩[MFC], 작업자 스레드"
  - "작업자 스레드[C++]"
ms.assetid: 670adbfe-041c-4450-a3ed-be14aab15234
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 다중 스레딩: 작업자 스레드 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

작업자 스레드는 일반적으로 사용자가 응용 프로그램을 사용하여 작업이 계속되도록 기다릴 필요가 없는 백그라운드 작업을 처리하는 데 사용됩니다.  다시 계산 또는 백그라운드 인쇄 등의 작업은 작업자 스레드의 좋은 예입니다.  이 항목에서는 작업자 스레드를 만드는 데 필요한 단계에 대해 설명합니다.  다음 내용을 다룹니다.  
  
-   [스레드 시작하기](#_core_starting_the_thread)  
  
-   [제어 함수 구현](#_core_implementing_the_controlling_function)  
  
-   [예제](#_core_controlling_function_example)  
  
 작업자 스레드를 만드는 작업은 비교적 간단합니다.  제어 함수를 구현하고 스레드를 시작하는 두 단계만 수행하면 스레드를 실행할 수 있습니다.  [CWinThread](../../mfc/reference/cwinthread-class.md)에서 클래스를 파생시킬 필요가 없습니다.  특별한 버전의 `CWinThread`가 필요한 경우 클래스를 파생시킬 수도 있지만 대부분의 단순한 작업자 스레드에는 그럴 필요가 없습니다.  `CWinThread`를 수정하지 않고 사용할 수 있습니다.  
  
##  <a name="_core_starting_the_thread"></a> 스레드 시작하기  
 `AfxBeginThread`는 두 가지 오버로드된 버전이 있습니다. 하나는 작업자 스레드만 만들 수 있고, 다른 하나는 사용자 인터페이스 스레드와 작업자 스레드를 모두 만들 수 있습니다.  첫 번째 오버로드를 사용하여 작업자 스레드를 실행하려면 다음과 같은 정보를 제공하여 [AfxBeginThread](../Topic/AfxBeginThread.md)를 호출합니다.  
  
-   제어 함수 주소  
  
-   제어 함수에 전달할 매개 변수  
  
-   \(선택적 요소\) 스레드의 원하는 우선 순위.  기본값은 보통 우선 순위입니다.  사용할 수 있는 우선 순위 수준에 대한 자세한 내용은 [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)]의 [SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277)를 참조하십시오.  
  
-   \(선택적 요소\) 스레드의 원하는 스택 크기.  기본값은 만드는 스레드와 스택의 크기가 동일합니다.  
  
-   \(선택적 요소\) 일시 중단된 상태에서 스레드가 만들어지기를 원하는 경우 **CREATE\_SUSPENDED**.  기본값은 0이며, 0이 아니면 스레드가 정상적으로 시작됩니다.  
  
-   \(선택적 요소\) 원하는 보안 특성.  기본값은 부모 스레드와 동일한 액세스입니다.  보안 정보 형식에 대한 자세한 내용은 [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)]의 [SECURITY\_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)를 참조하십시오.  
  
 `AfxBeginThread`는 사용자 대신 `CWinThread` 개체를 만들고 초기화하여 시작하며 사용자가 나중에 이 개체를 참조할 수 있도록 주소를 반환합니다.  작성의 일부가 실패한 경우 전체 프로시저에서 모든 개체가 제대로 할당 해제되었는지 확인합니다.  
  
##  <a name="_core_implementing_the_controlling_function"></a> 제어 함수 구현  
 제어 함수는 스레드를 정의합니다.  이 함수를 입력하면 스레드가 시작되고 함수가 종료되면 스레드도 종료됩니다.  제어 함수는 다음과 같은 프로토타입을 사용해야 합니다.  
  
```  
UINT MyControllingFunction( LPVOID pParam );  
```  
  
 매개 변수는 단일 값이며,  함수가 이 매개 변수에서 받는 값은 스레드 개체가 만들어졌을 때 생성자에 전달된 값입니다.  제어 함수는 선택한 모든 방법으로 이 값을 해석할 수 있습니다.  스칼라 값 또는 여러 매개 변수를 포함하는 구조체에 대한 포인터로 처리되거나 무시될 수도 있습니다.  매개 변수가 구조체를 참조하는 경우 구조체를 사용하여 호출자에서 스레드로 데이터를 전달할 뿐만 아니라 스레드에서 호출자로 데이터를 다시 전달할 수 있습니다.  이러한 구조체를 사용하여 데이터를 다시 호출자에게 전달하는 경우 스레드는 호출자에게 결과를 알려 주어야 합니다.  작업자 스레드에서 호출자로 통신하는 데 대한 내용은 [다중 스레딩: 프로그래밍 팁](../../parallel/multithreading-programming-tips.md)을 참조하십시오.  
  
 함수가 종료되면 종료 이유를 나타내는 **UINT** 값을 반환해야 합니다.  일반적으로 종료 코드가 0이면 성공을 나타내고 0 이외의 값이면 각각에 해당하는 오류 유형을 나타냅니다.  이것은 구현 방식에 따라 다릅니다.  일부 스레드는 개체의 사용 횟수를 유지 관리하여 해당 개체의 현재 사용 횟수를 반환할 수 있습니다.  응용 프로그램에서 이 값을 검색하는 방법을 보려면 [다중 스레딩: 스레드 종료](../../parallel/multithreading-terminating-threads.md)를 참조하십시오.  
  
 MFC 라이브러리로 작성된 다중 스레드 프로그램에서 수행할 수 있는 작업에는 몇 가지 제한 사항이 있습니다.  이러한 제한 사항에 대한 설명 및 스레드 사용에 대한 기타 팁을 보려면 [다중 스레딩: 프로그래밍 팁](../../parallel/multithreading-programming-tips.md)을 참조하십시오.  
  
##  <a name="_core_controlling_function_example"></a> 제어 함수 예제  
 다음 예제는 제어 함수를 정의하여 프로그램의 다른 부분에서 이 함수를 사용하는 방법을 보여 줍니다.  
  
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
  
## 추가 정보  
  
-   [다중 스레딩: 사용자 인터페이스 스레드 만들기](../../parallel/multithreading-creating-user-interface-threads.md)  
  
## 참고 항목  
 [C\+\+ 및 MFC에서 다중 스레딩](../../parallel/multithreading-with-cpp-and-mfc.md)