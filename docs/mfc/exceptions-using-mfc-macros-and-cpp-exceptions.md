---
title: '예외: MFC 매크로 및 c + + 예외 사용 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- exception objects [MFC]
- memory leaks [MFC], exception object not deleted
- exception handling [MFC], MFC
- try-catch exception handling [MFC], mixing MFC macros and C++ keywords
- exception objects [MFC], deleting
- exceptions [MFC], MFC macros vs. C++ keywords
- catch blocks [MFC], mixed
- exception handling [MFC], mixed-language
- nested try blocks [MFC]
- catch blocks [MFC], explicitly deleting code in
- try-catch exception handling [MFC], nested try blocks
- heap corruption [MFC]
- nested catch blocks [MFC]
ms.assetid: d664a83d-879b-44d4-bdf0-029f0aca69e9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c50e7358d29e04c81a5e443d5b1a03881fed7f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>예외: MFC 매크로 및 C++ 예외 사용
MFC 예외 처리 매크로 c + + 예외 처리 키워드를 사용 하는 코드를 작성 하기 위한 고려 사항에 설명 합니다.  
  
 이 문서에서는 다음 항목을 다룹니다.  
  
-   [예외 키워드와 매크로](#_core_mixing_exception_keywords_and_macros)  
  
-   [Try catch 블록 내부는 블록](#_core_try_blocks_inside_catch_blocks)  
  
##  <a name="_core_mixing_exception_keywords_and_macros"></a> 예외 키워드와 매크로  
 MFC 예외 매크로 및 c + + 예외 키워드로 동일한 프로그램에서 함께 사용할 수 있습니다. 하지만 삭제 하므로 예외 개체가 자동으로 범위를 벗어나는 경우 예외 처리 키워드를 사용 하 여 코드 하지 않는 반면 동일한 블록에서 c + + 예외 키워드로 MFC 매크로 혼합할 수 없습니다. 자세한 내용은 문서 참조 [예외: 검색 및 삭제 하는 중 예외](../mfc/exceptions-catching-and-deleting-exceptions.md)합니다.  
  
 매크로 키워드 사이의 주요 차이점 매크로 예외 범위를 벗어나면 "자동으로"는 예외가 삭제 하입니다. 키워드를 사용 하 여 코드 하지 않습니다. catch 블록에서 발생 한 예외만 명시적으로 삭제 되어야 합니다. 매크로 c + + 예외 키워드로 혼합 예외 개체는 삭제 되지 때 메모리 손실을 유발할 하거나 예외를 두 번 삭제 되 면 손상 힙 수 있습니다.  
  
 예를 들어 다음 코드에서 예외 포인터를 무효화:  
  
 [!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]  
  
 문제가 발생 하기 때문에 `e` 실행 "내부" 밖으로 전달 하면 삭제 됩니다 **CATCH** 블록입니다. 사용 하는 `THROW_LAST` 대신 매크로 **THROW** 문을 하면는 "외부" **CATCH** 블록 유효한 포인터를 받을 수:  
  
 [!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]  
  
##  <a name="_core_try_blocks_inside_catch_blocks"></a> Try Catch 블록 내부는 블록  
 내에서 현재 예외 다시 throw 할 수는 **시도** 블록 내에 있는 한 **CATCH** 블록입니다. 다음 예에서는 유효 하지 않습니다.  
  
 [!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]  
  
 자세한 내용은 참조 [예외: 예외 내용 검사](../mfc/exceptions-examining-exception-contents.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리](../mfc/exception-handling-in-mfc.md)

