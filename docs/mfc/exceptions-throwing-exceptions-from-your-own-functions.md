---
title: "예외: 자체 함수에서 예외를 Throw | Microsoft Docs"
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
- throwing exceptions [MFC], from functions
- functions [MFC], throwing exceptions
- exceptions [MFC], throwing
ms.assetid: 492976e8-8804-4234-8e8f-30dffd0501be
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 15aeb1af7f41cf2df8be3f69657ec6870c55ab34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-throwing-exceptions-from-your-own-functions"></a>예외: 자체 함수에서 예외 Throw
MFC 또는 다른 라이브러리의 함수에 의해 throw 된 예외를 catch 하는 데에 MFC 예외 처리 패러다임을 사용 하는 것이 불가능 합니다. 라이브러리 코드에서 throw 된 예외를 catch 하는 것 외에도 예외 조건이 발생할 수 있는 함수를 작성 하는 경우 사용자 고유의 코드에서 예외 throw 할 수 있습니다.  
  
 현재 함수의 실행이 중지 되 고에 직접 이동 예외가 발생 하는 경우는 **catch** 가장 안쪽의 예외 프레임의 블록입니다. 예외 메커니즘 함수에서 정상 종료 경로 무시합니다. 따라서 정상 종료에서 삭제 하려는 메모리 블록 삭제 해야 합니다.  
  
#### <a name="to-throw-an-exception"></a>예외를 throw 하려면  
  
1.  와 같은 MFC 도우미 함수 중 하나를 사용 `AfxThrowMemoryException`합니다. 이러한 함수는 적절 한 유형의 미리 할당 된 예외 개체를 throw 합니다.  
  
     다음 예제에서는에서 함수 개의 메모리 블록을 할당 하려고 시도 하 고 중 하나를 할당 하지 못한 경우 예외를 throw 합니다.  
  
     [!code-cpp[NVC_MFCExceptions#17](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_1.cpp)]  
  
     첫 번째 할당이 실패 하면 단순히 메모리 예외를 throw 할 수 있습니다. 첫 번째 할당은 성공 하는 경우 두 번째 실패 예외를 throw 하기 전에 첫 번째 할당 블록을 해제 해야 합니다. 두 할당이 성공 하는 경우에 정상적으로 진행 수 있으며 함수를 종료할 때 블록을 해제할 수 있습니다.  
  
     - 또는  
  
2.  문제 상태를 표시 하는 사용자 정의 예외를 사용 합니다. 모든 유형의 심지어는 전체 클래스 항목 예외로 throw 할 수 있습니다.  
  
     다음 예제에서는 웨이브 장치를 통해 소리를 재생 하 고 오류가 발생 하는 경우 예외를 throw 합니다.  
  
     [!code-cpp[NVC_MFCExceptions#18](../mfc/codesnippet/cpp/exceptions-throwing-exceptions-from-your-own-functions_2.cpp)]  
  
> [!NOTE]
>  MFC의 기본 처리 하는 예외에 대 한 포인터에만 적용 됩니다 `CException` 개체 (및 개체의 `CException`-파생 된 클래스). 위의 예제는 MFC의 예외 메커니즘을 무시합니다.  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리](../mfc/exception-handling-in-mfc.md)

