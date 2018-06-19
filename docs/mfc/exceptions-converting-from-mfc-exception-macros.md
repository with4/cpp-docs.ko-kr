---
title: '예외: MFC 예외 매크로에서 변환 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- converting exceptions [MFC]
- exception objects [MFC]
- conversions [MFC], code written with MFC macros
- keywords [MFC], macros
- macrosv, C++ keywords
- exception objects [MFC], deleting
- CException class [MFC], deleting CException class objects
- exceptions [MFC], converting
- exceptions [MFC], deleting exception objects
- catch blocks [MFC], delimiting
- exception handling [MFC], converting exceptions
ms.assetid: bd3ac3b3-f3ce-4fdd-a168-a2cff13ed796
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8953cc28e35974f7a2a63754533ffd851ca62a3e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350757"
---
# <a name="exceptions-converting-from-mfc-exception-macros"></a>예외: MFC 예외 매크로에서 변환
고급 항목입니다.  
  
 이 문서에서는 Microsoft Foundation Class 매크로로 작성 된 기존 코드를 변환 하는 방법을 설명- **시도**, **CATCH**, **THROW**등-c + + 예외 처리를 사용 하려면 키워드 **시도**, **catch**, 및 `throw`합니다. 다음과 같은 내용을 다룹니다.  
  
-   [변환 장점](#_core_advantages_of_converting)  
  
-   [C + + 예외 사용의 예외 매크로 사용 하 여 코드 변환](#_core_doing_the_conversion)  
  
##  <a name="_core_advantages_of_converting"></a> 변환의 이점  
 아마도 필요가 없습니다 기존 코드를 변환할 있지만 이전 버전에서 구현 및 mfc 버전 3.0 매크로 구현 방식 간의 차이점을 알고 있어야 합니다. 이러한 차이점 및 코드 동작의 후속 변경 내용은에 설명 되어 [예외: 버전 3.0의 예외 매크로 변경](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)합니다.  
  
 변환의 기본 이점은 다음과 같습니다.  
  
-   C + + 예외 처리 키워드를 사용 하는 코드를 약간 더 작은 컴파일합니다. EXE 또는 합니다. DLL입니다.  
  
-   C + + 예외 처리 키워드: 복사할 수 있는 모든 데이터 형식의 예외를 처리할 수 있도록 (`int`, **float**, `char`등), 클래스 의매크로처리하는반면,`CException` 클래스에서 파생 되 고 있습니다.  
  
 매크로 키워드 사이의 주요 차이점은 예외 범위를 벗어나면 "자동 으로" 매크로 사용 하 여 코드는 예외가 삭제 합니다. 키워드를 사용 하 여 코드는 그렇지 않으므로 예외가 명시적으로 삭제 해야 합니다. 자세한 내용은 문서 참조 [예외: 검색 및 삭제 하는 중 예외](../mfc/exceptions-catching-and-deleting-exceptions.md)합니다.  
  
 또 다른 차이점은 구문입니다. 세 가지 측면에서 매크로 키워드의 구문은 마다 다릅니다.  
  
1.  매크로 인수 및 예외 선언  
  
     A **CATCH** 매크로 호출에는 다음 구문을 가집니다.  
  
     **CATCH (** *exception_class*, *exception_object_pointer_name* **)**  
  
     클래스 이름 및 개체 포인터 이름 사이 쉼표가 확인 합니다.  
  
     에 대 한 예외 선언이 **catch** 키워드에서는이 구문을 사용 합니다.  
  
     **catch (** *exception_type* *exception_name * * *)**  
  
     이 예외 선언문 예외 catch의 유형을 나타내는 블록이 처리 합니다.  
  
2.  Catch 블록의 delimitation:  
  
     매크로 함께 **CATCH** (인수) 사용 하 여 매크로 첫 번째 catch 블록을 시작, `AND_CATCH` 이후 catch 블록을 시작 하는 매크로 및 `END_CATCH` 매크로 catch 블록의 시퀀스를 종료 합니다.  
  
     키워드와 함께 **catch** 예외 선언) (포함 키워드 각 catch 블록을 시작 합니다. 에 해당 하는 항목이 고 `END_CATCH` 매크로; 블록 끝의 닫는 중괄호와 함께 catch 합니다.  
  
3.  Throw 식:  
  
     매크로 사용 하 여 `THROW_LAST` 를 다시 현재 예외를 throw 합니다. `throw` 키워드 없는 인수를 사용 하는 같습니다.  
  
##  <a name="_core_doing_the_conversion"></a> 변환을 수행  
  
#### <a name="to-convert-code-using-macros-to-use-the-c-exception-handling-keywords"></a>매크로 사용 하 여 c + + 예외 처리 키워드를 사용 하도록 코드를 변환 하려면  
  
1.  MFC 매크로의 모든 문제를 찾고 **시도**, **CATCH**, `AND_CATCH`, `END_CATCH`, **THROW**, 및 `THROW_LAST`합니다.  
  
2.  교체 하거나 다음 매크로의 항목을 모두 삭제:  
  
     **시도** (바꿀 **시도**)  
  
     **CATCH** (바꿀 **catch**)  
  
     `AND_CATCH` (사용 하 여 대체 **catch**)  
  
     `END_CATCH` (삭제)  
  
     **THROW** (바꿀 `throw`)  
  
     `THROW_LAST` (사용 하 여 대체 `throw`)  
  
3.  유효한 예외 선언이 형성 매크로 인수를 수정 합니다.  
  
     예를 들어 변경  
  
     [!code-cpp[NVC_MFCExceptions#6](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_1.cpp)]  
  
     다음으로 변경:  
  
     [!code-cpp[NVC_MFCExceptions#7](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_2.cpp)]  
  
4.  필요에 따라 예외 개체를 삭제 하는 catch 블록의 코드를 수정 합니다. 자세한 내용은 문서 참조 [예외: 검색 및 삭제 하는 중 예외](../mfc/exceptions-catching-and-deleting-exceptions.md)합니다.  
  
 MFC 예외 매크로 사용 하 여 예외 처리 코드의 예를 들면 다음과 같습니다. 다음 예제에서 코드의 예외 매크로 사용 하기 때문에 사용자에 게 유의 `e` 자동으로 삭제 됩니다.  
  
 [!code-cpp[NVC_MFCExceptions#8](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_3.cpp)]  
  
 다음 예제에서 코드는 c + + 예외 키워드를 사용 하 여 예외를 명시적으로 삭제 해야 하므로:  
  
 [!code-cpp[NVC_MFCExceptions#9](../mfc/codesnippet/cpp/exceptions-converting-from-mfc-exception-macros_4.cpp)]  
  
 자세한 내용은 참조 [예외: MFC 매크로 및 c + + 예외 사용](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리](../mfc/exception-handling-in-mfc.md)

