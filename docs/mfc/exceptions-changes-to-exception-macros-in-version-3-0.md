---
title: '예외: 버전 3.0의에서 예외 매크로 변경 사항 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- C++ exception handling [MFC], upgrade considerations
- CATCH macro [MFC]
- exceptions [MFC], what's changed
- THROW_LAST macro [MFC]
ms.assetid: 3aa20d8c-229e-449c-995c-ab879eac84bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 92d1691f9a61a11dc4d9dfe7e869ccb7899746bc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350014"
---
# <a name="exceptions-changes-to-exception-macros-in-version-30"></a>예외: 버전 3.0의 예외 매크로 변경 사항
고급 항목입니다.  
  
 MFC 버전 3.0 이상, 예외 처리 매크로 c + + 예외를 사용 하도록 변경 되었습니다. 이 문서는 해당 변경 내용을 매크로 사용 하는 기존 코드의 동작에 주는 영향 지시 합니다.  
  
 이 문서에서는 다음 항목을 다룹니다.  
  
-   [예외 형식 및 CATCH 매크로](#_core_exception_types_and_the_catch_macro)  
  
-   [예외가 다시 throw](#_core_re.2d.throwing_exceptions)  
  
##  <a name="_core_exception_types_and_the_catch_macro"></a> 예외 형식 및 CATCH 매크로  
 MFC의 이전 버전에서의 **CATCH** 예외의 형식이 결정 됩니다, 즉, catch 쪽에서; 매크로 MFC 런타임 형식 정보 예외의 형식을 결정 하는 데 사용 합니다. 그러나 C + + 예외와 예외 형식은 항상에 따라 결정 됩니다 throw 사이트 throw 되는 예외 개체의 형식입니다. 드물긴 하지만 throw 된 개체의 형식에서 throw 된 개체에 대 한 포인터의 유형이 다른 비 호환성 그러면 됩니다.  
  
 다음 예제는 MFC 버전 3.0 및 이전 버전 간의 이러한 차이의 결과입니다.  
  
 [!code-cpp[NVC_MFCExceptions#1](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_1.cpp)]  
  
 이 코드와 다르게 동작 버전 3.0의에서 컨트롤은 항상 첫 번째 전달 하기 때문에 **catch** 일치 하는 예외 선언이 사용 하 여 블록입니다. Throw 식의 결과  
  
 [!code-cpp[NVC_MFCExceptions#19](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_2.cpp)]  
  
 로 throw 되는 **CException\*** 로 생성 되는 경우에 한 **CCustomException**합니다. **CATCH** 이전 사용 하 여 MFC 버전 2.5에서 매크로 `CObject::IsKindOf` 형식을 테스트 하 고 런타임 시에 있습니다. 때문에 식  
  
 [!code-cpp[NVC_MFCExceptions#20](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_3.cpp)]  
  
 가 true 이면 첫 번째 catch 블록이 예외를 catch 합니다. C + + 예외를 사용 하 여 예외 처리 매크로의 대부분 구현 한다는 것을 버전 3.0, 두 번째 catch 블록에서 throw 된 일치 `CException`합니다.  
  
 다음과 같은 코드가 않습니다. 예외 개체는 일반 허용 하는 다른 함수에 전달 되 면 일반적으로 표시 **CException\***, "사전 throw" 처리를 수행 하 고 마지막으로 예외를 throw 합니다.  
  
 이 문제를 해결 하려면 throw 식에서 함수 호출 코드에 이동한 실제 예외를 생성할 때 컴파일러에 알려진 형식의 예외를 throw 합니다.  
  
##  <a name="_core_re.2d.throwing_exceptions"></a> 예외가 다시 Throw  
 Catch 블록에 있는 것 같은 예외 포인터 throw 할 수 없습니다.  
  
 이 코드의 이전 버전에서는 유효 하지만 갖습니다 예를 들어 버전 3.0의 예기치 않은 결과:  
  
 [!code-cpp[NVC_MFCExceptions#2](../mfc/codesnippet/cpp/exceptions-changes-to-exception-macros-in-version-3-0_4.cpp)]  
  
 사용 하 여 **THROW** catch 블록 하면 포인터가 `e` 외부 catch 사이트는 잘못 된 포인터를 받을 수 있도록 삭제 됩니다. 사용 하 여 `THROW_LAST` 를 다시 throw `e`합니다.  
  
 자세한 내용은 참조 [예외: 검색 및 삭제 하는 중 예외](../mfc/exceptions-catching-and-deleting-exceptions.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리](../mfc/exception-handling-in-mfc.md)

