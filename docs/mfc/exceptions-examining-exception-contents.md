---
title: "예외: 예외 내용 검사 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- exception handling [MFC], MFC
- try-catch exception handling [MFC], MFC function exceptions
- catch blocks, MFC function exceptions
- CException class [MFC], class exceptions
- try-catch exception handling [MFC], exception contents
- throwing exceptions [MFC], exception contents
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 953dd61247f7d14ad04d5d5f85529c89f3aaad9d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-examining-exception-contents"></a>예외: 예외 내용 검사
하지만 한 **catch** 거의 모든 데이터 형식의 블록의 인수 수 있으며, MFC 함수는 클래스에서 파생 된 형식의 예외를 throw `CException`합니다. MFC 함수에 의해 throw 된 예외를 catch 하려면 한 다음, 작성 한 **catch** 포인터 인수가 블록에는 `CException` 개체 (에서 파생 된 개체 또는 `CException`와 같은 `CMemoryException`) 합니다. 예외에 대 한 정확한 형식에 따라 예외의 특정 원인에 대 한 정보를 수집 하는 예외 개체의 데이터 멤버를 검사할 수 있습니다.  
  
 예를 들어는 `CFileException` 형식에는 `m_cause` 파일 예외의 원인을 지정 하는 열거 형식에 포함 된 데이터 멤버입니다. 일부의 가능한 반환 값은 **CFileException::fileNotFound** 및 **CFileException::readOnly**합니다.  
  
 다음 예제에서는의 내용을 검사 하는 방법을 보여 줍니다.는 `CFileException`합니다. 마찬가지로 다른 예외 형식을 검사할 수 있습니다.  
  
 [!code-cpp[NVC_MFCExceptions#13](../mfc/codesnippet/cpp/exceptions-examining-exception-contents_1.cpp)]  
  
 자세한 내용은 참조 [예외: 예외의 개체 해제](../mfc/exceptions-freeing-objects-in-exceptions.md) 및 [예외: 검색 및 삭제 하는 중 예외](../mfc/exceptions-catching-and-deleting-exceptions.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리](../mfc/exception-handling-in-mfc.md)

