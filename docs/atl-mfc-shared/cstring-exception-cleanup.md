---
title: "CString 예외 정리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 496fdfe6a609bd4eceae225c2568c915d38aef07
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cstring-exception-cleanup"></a>CString 예외 정리
이전 버전의 MFC 정리 하 중요 했습니다 [CString](../atl-mfc-shared/reference/cstringt-class.md) 개체 후 사용 합니다. MFC 버전 3.0 이상에서 명시적 정리 작업이 필요 없습니다.  
  
 C + + 예외 처리 메커니즘 이제 MFC를 사용 하는, 아래 예외 발생 후 정리를 걱정할 필요가 없습니다. 에 대 한 설명은 방법 c + + "는 스택을 해제" 예외가 후를 참조 하십시오. [try, catch 및 throw 문](../cpp/try-throw-and-catch-statements-cpp.md)합니다. MFC를 사용 하는 경우에 **시도**/**CATCH** c + + 키워드 대신 매크로 **시도** 및 **catch**, MFC는 c + +를 사용 합니다. 아래 예외 메커니즘 하므로 사용자는 여전히 않아도를 명시적으로 정리 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [문자열 (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [예외 처리](../mfc/exception-handling-in-mfc.md)

