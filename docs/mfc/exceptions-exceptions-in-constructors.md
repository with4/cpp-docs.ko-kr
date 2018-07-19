---
title: '예외: 생성자의 예외 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8336700cc0137efe3bc106871ebd76b8de7a99af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33342633"
---
# <a name="exceptions-exceptions-in-constructors"></a>예외: 생성자의 예외
생성자에서는 예외를 throw 하는 경우에 설명 된 대로 된 예외를 throw 하기 전에 내용을 모든 개체 및 메모리 할당 정리 [예외: 사용자 자신의 함수에서 예외를 Throw](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)합니다.  
  
 생성자에서는 예외를 throw 하는 경우 개체 자체에 대 한 메모리가 이미 생성자가 호출 될 때 할당 되었습니다. 따라서 컴파일러 예외가 throw 되는 개체에서 사용한 메모리 자동으로 할당 취소 됩니다.  
  
 자세한 내용은 참조 [예외: 예외의 개체 해제](../mfc/exceptions-freeing-objects-in-exceptions.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리](../mfc/exception-handling-in-mfc.md)

