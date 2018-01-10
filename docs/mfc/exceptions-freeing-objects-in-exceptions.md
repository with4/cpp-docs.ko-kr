---
title: "예외: 예외의 개체 해제 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- throwing exceptions [MFC], freeing objects in exceptions
- local exception handling
- memory leaks, caused by exception
- try-catch exception handling [MFC], destroying objects
- destroying objects [MFC]
- freeing objects [MFC]
- throwing exceptions [MFC], after destroying
- exception handling [MFC], destroying objects
ms.assetid: 3b14b4ee-e789-4ed2-b8e3-984950441d97
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a422347e319fabbd91f20e0ebf7897865f1ca4c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-freeing-objects-in-exceptions"></a>예외: 예외의 개체 해제
이 문서 필요성 및 예외가 발생 하면 개체를 해제 하는 방법을 설명 합니다. 다음과 같은 내용을 다룹니다.  
  
-   [로컬에서 예외 처리](#_core_handling_the_exception_locally)  
  
-   [개체를 삭제 한 후 예외를 throw 합니다.](#_core_throwing_exceptions_after_destroying_objects)  
  
 응용 프로그램 인터럽트 프로그램이 정상 흐름 또는 프레임 워크에 의해 발생 한 예외입니다. 따라서는 예외가 발생 하는 경우 제대로 그중에서 처리할 수 있도록 개체에 대를 유지 하는 매우 중요 합니다.  
  
 이렇게 하려면 두 가지 주요 방법 있습니다.  
  
-   예외를 사용 하 여 로컬로 처리는 **시도** 및 **catch** 키워드를 하나의 문으로 모든 개체를 삭제 합니다.  
  
-   모든 개체 삭제는 **catch** 추가로 처리 하기 위한 블록 외부 예외가 throw 되기 전에 차단 합니다.  
  
 이러한 두 접근 방법은 아래에서 설명에 다음 문제가 있는 예와 솔루션으로:  
  
 [!code-cpp[NVC_MFCExceptions#14](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_1.cpp)]  
  
 위에 쓰인 대로 `myPerson` 에서 예외가 throw 되 면 삭제 되지 것입니다 `SomeFunc`합니다. 실행이 일반적인 함수 종료 및 개체를 삭제 하는 코드를 무시 다음 외부 예외 처리기에 직접 이동 합니다. 개체에 대 한 포인터가 범위를 벗어날 예외 함수를 유지 하 고 프로그램이 실행 중인 상태로 개체에서 사용한 메모리는 복구할 수 없습니다. 이 메모리 누수가 발생 합니다. 메모리 진단을 사용 하 여 감지 됩니다.  
  
##  <a name="_core_handling_the_exception_locally"></a>로컬에서 예외 처리  
 **try/catch** 패러다임 메모리 누수를 방지 하 고, 예외가 발생 한 경우 사용자 개체가 소멸 되 확인에 대 한 프로그래밍 메서드를 제공 합니다. 예를 들어,이 문서의 앞부분에 표시 된 예는 다음과 같이 작성 될 수 없습니다.  
  
 [!code-cpp[NVC_MFCExceptions#15](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_2.cpp)]  
  
 이 새 예제에서는 예외를 catch 하 고 로컬로 처리 하는 예외 처리기를 설정 합니다. 그런 다음 함수를 정상적으로 종료 하 고 개체를 소멸 시킵니다. 이 예의 중요 한 측면은 예외를 catch 하는 컨텍스트가 설정 된는 **try/catch** 블록입니다. 로컬 예외 프레임 없이 함수는 예외가 throw 되었다는 사실 및가 정상적으로 종료 하 고 개체를 소멸 있는 기회를 갖지 않는 못합니다 하지 않습니다.  
  
##  <a name="_core_throwing_exceptions_after_destroying_objects"></a>개체를 삭제 한 후 예외를 throw 합니다.  
 예외를 처리 하는 다른 방법은 다음 외부 예외 처리 컨텍스트를 전달 하는 합니다. 사용자 **catch** 블록 로컬로 할당 된 개체의 몇 가지 정리 작업을 수행 하 고 추가 처리를 위해는 예외를 throw 합니다.  
  
 Throw 함수 수도 있습니다 힙 개체 할당을 취소할 필요가 없을 수도 있습니다. 함수도 할당을 취소 해야 힙 개체는 예외를 throw 하기 전에 다음 함수는 일반적인 경우에 반환 하기 전에 힙 개체를 할당 취소는 항상 하는 경우. 반면에 경우 함수는 할당 취소 하지 개체 일반적인 경우에 반환 하기 전에, 다음 결정 해야 상황별으로에 힙 개체를 할당 취소 해야 하는지 여부를 합니다.  
  
 다음 예제에서는 어떻게 로컬로 할당 된 개체 정리 될 수 있습니다.  
  
 [!code-cpp[NVC_MFCExceptions#16](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_3.cpp)]  
  
 프레임 개체를 자동으로 할당 취소 예외 메커니즘 프레임 개체의 소멸자는 라고도 합니다.  
  
 예외를 throw 할 수 있는 함수를 호출 하는 경우 사용할 수 있습니다 **try/catch** 블록에는 예외를 catch 하 고 자체적으로 만든 모든 개체 삭제 내용이 있는지 확인 합니다. 특히 많은 MFC 함수 예외를 throw 할 수 수 있습니다.  
  
 자세한 내용은 참조 [예외: 검색 및 삭제 하는 중 예외](../mfc/exceptions-catching-and-deleting-exceptions.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리](../mfc/exception-handling-in-mfc.md)

