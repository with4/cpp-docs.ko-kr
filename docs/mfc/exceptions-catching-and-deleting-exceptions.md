---
title: "예외: 예외 Catch 및 삭제 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- exceptions [MFC], deleting
- AND_CATCH macro [MFC]
- try-catch exception handling [MFC], catching and deleting exceptions
- exception handling [MFC], catching and deleting exceptions
- catch blocks [MFC], catching and deleting exceptions
- execution [MFC], returns from within catch block
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8496b5228fe4002bb1ca80f8fbe793fd5e16ca81
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-catching-and-deleting-exceptions"></a>예외: 예외 Catch 및 삭제
다음 지침과 예제를 catch 하 고 예외를 삭제 하는 방법을 보여 줍니다. 대 한 자세한 내용은 **시도**, **catch**, 및 `throw` 키워드 참조 [c + + 예외 처리](../cpp/cpp-exception-handling.md)합니다.  
  
 예외 처리기는 예외를 삭제 하지 못하면 해당 코드는 예외를 catch 될 때마다 메모리 누수를 발생 시킵니다 때문에, 처리 된 예외 개체를 삭제 해야 합니다.  
  
 프로그램 **catch** 블록에서 예외를 삭제 해야 경우:  
  
-   **catch** 블록에는 새 예외를 throw 합니다.  
  
     물론, 동일한 예외를 다시 throw 되는 경우 예외를 삭제 해야 합니다.  
  
     [!code-cpp[NVC_MFCExceptions#3](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_1.cpp)]  
  
-   내에서 실행 하 여 반환 된 **catch** 블록입니다.  
  
> [!NOTE]
>  삭제할 때는 `CException`를 사용 하 여는 **삭제** 멤버 함수는 예외를 삭제 합니다. 사용 하지 마십시오는 **삭제** 키워드를 예외 힙에 없으면 실패할 수 있습니다.  
  
#### <a name="to-catch-and-delete-exceptions"></a>Catch 하 고 예외를 삭제 하려면  
  
1.  사용 하 여는 **시도** 를 설정 하는 키워드는 **시도** 블록입니다. 내에서 예외를 throw 할 수 있는 모든 프로그램 문을 실행 하는 **시도** 블록입니다.  
  
     사용 하 여는 **catch** 를 설정 하는 키워드는 **catch** 블록입니다. 예외 처리 코드를 추가 하는 **catch** 블록입니다. 코드는 **catch** 블록은 경우에 실행 됩니다 내의 코드는 **시도** 블록에 지정 된 형식의 예외를 throw는 **catch** 문.  
  
     스 켈 레 톤에서는 다음 방법을 **시도** 및 **catch** 블록은 일반적으로 정렬:  
  
     [!code-cpp[NVC_MFCExceptions#4](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_2.cpp)]  
  
     제어가 첫 번째 전달에서 예외가 throw 되 면 **catch** 블록 예외 선언이 예외의 형식과 일치 합니다. 다양 한 유형의 순차적를 사용 하 여 예외를 선택적으로 처리할 수 **catch** 아래와 같이 차단:  
  
     [!code-cpp[NVC_MFCExceptions#5](../mfc/codesnippet/cpp/exceptions-catching-and-deleting-exceptions_3.cpp)]  
  
 자세한 내용은 참조 [예외: MFC 예외 매크로에서 변환](../mfc/exceptions-converting-from-mfc-exception-macros.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리](../mfc/exception-handling-in-mfc.md)

