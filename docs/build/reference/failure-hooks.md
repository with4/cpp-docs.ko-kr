---
title: 오류 후크 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be598a77ca48eeee03360a3b598b0567abc6ee4b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="failure-hooks"></a>오류 후크
오류 후크를 동일한 방식으로 사용 하 여 [알림 후크](../../build/reference/notification-hooks.md)합니다. 처리 되도록 적합 한 값을 반환 하려면 후크 라우팅 요구 (HINSTANCE 또는 FARPROC) 계속할 수 또는 0을 예외가 발생 하도록 합니다.  
  
 다음은 사용자 정의 함수를 참조 하는 포인터 변수가입니다.  
  
```  
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}  
ExternC  
PfnDliHook   __pfnDliFailureHook2;  
```  
  
 **DelayLoadInfo** 에서 값을 포함 하 여 오류의 정확한 보고 하는 데 필요한 모든 관련 데이터를 포함 하는 구조 `GetLastError`합니다.  
  
 알림이 **dliFailLoadLib**, 후크 함수를 사용 하 여 반환할 수 있습니다.  
  
-   오류를 처리할 수 없는 경우 0입니다.  
  
-   HMODULE 오류 후크 문제를 해결 하 고 자체 라이브러리를 로드 합니다.  
  
 알림이 **dliFailGetProc**, 후크 함수를 사용 하 여 반환할 수 있습니다.  
  
-   오류를 처리할 수 없는 경우 0입니다.  
  
-   유효한 proc 주소 (가져오기 함수 주소), 오류 후크가 경우 주소에서 성공 했습니다.  
  
## <a name="see-also"></a>참고 항목  
 [오류 처리 및 알림](../../build/reference/error-handling-and-notification.md)