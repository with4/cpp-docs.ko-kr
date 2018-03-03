---
title: "오류 처리 및 알림 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- error handling, and notification
ms.assetid: b621cf60-d869-451a-b05e-dc86d78addaa
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 738721eb3fc37ba076157129cb88a22f2c90e464
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="error-handling-and-notification"></a>오류 처리 및 알림
오류 처리 및 알림에 대 한 자세한 내용은 참조 하십시오. [도우미 함수 이해](understanding-the-helper-function.md)합니다.  
  
 후크 함수에 대 한 자세한 내용은 참조 하십시오. [구조체 및 상수 정의](../../build/reference/structure-and-constant-definitions.md)합니다.  
  
 프로그램이 지연 로드 된 Dll를 사용 하는 경우 하므로 처리 해야 오류 강력 하 게 프로그램이 실행 되는 동안 발생 하는 실패 하면 처리 되지 않은 예외가 발생 합니다. 오류 처리는 두 부분으로 구성 됩니다.  
  
 후크를 통해 복구 합니다.  
 코드를 복구 하거나 실패 한 경우 대체 라이브러리 및 루틴을 제공 하는 경우 제공 하거나 문제를 해결할 수 있는 도우미 함수에 대 한 후크를 제공할 수 있습니다. 후크 라우팅 요구를 처리 하는 적합 한 값을 반환 하는 (HINSTANCE 또는 FARPROC) 계속할 수 또는 0을 예외가 발생 하도록 합니다. 자체 예외도 throw 할 수 있습니다 또는 **longjmp** 후크를 벗어났습니다. 알림 후크 및 오류 후크 됩니다.  
  
 예외를 통해 보고 합니다.  
 프로시저를 중단 하는 오류 처리에 필요한 모든으로 사용자 코드에서 예외를 처리할 수 없는 후크는 필요 합니다.  
  
 오류 처리 및 알림 다음 항목에 설명합니다.  
  
-   [알림 후크](../../build/reference/notification-hooks.md)  
  
-   [오류 후크](../../build/reference/failure-hooks.md)  
  
-   [예외](../../build/reference/exceptions-c-cpp.md)  
  
## <a name="see-also"></a>참고 항목  
 [링커의 지연 로드된 DLL 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)