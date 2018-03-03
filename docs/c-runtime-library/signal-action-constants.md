---
title: "신호 작업 상수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SIG_IGN
- SIG_DFL
dev_langs:
- C++
helpviewer_keywords:
- signal action constants
- SIG_IGN constant
- SIG_DFL constant
ms.assetid: c3cb4f15-d39e-4d9d-84f9-0d33e3eb5993
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 256f11d3f8daa8a00e70e24aa19c31b71413c13c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="signal-action-constants"></a>신호 작업 상수
인터럽트 신호를 받을 때 수행되는 작업은 `func` 값에 따라 다릅니다.  
  
## <a name="syntax"></a>구문  
  
```  
#include <signal.h>  
```  
  
## <a name="remarks"></a>설명  
 `func` 인수는 함수 주소 또는 아래에 나열되고 SIGNAL.H에 정의된 매니페스트 상수 중 하나여야 합니다.  
  
 `SIG_DFL`  
 시스템 기본 응답을 사용합니다. 호출 프로그램이 스트림 I/O를 사용하는 경우 런타임 라이브러리에 의해 생성된 버퍼는 플러시되지 않습니다.  
  
 `SIG_IGN`  
 인터럽트 신호를 무시합니다. 프로세스의 부동 소수점 상태가 정의되지 않은 상태로 유지되므로 `SIGFPE`에 대해서는 이 값이 지정되지 않습니다.  
  
 `SIG_SGE`  
 신호에서 오류가 발생했음을 나타냅니다.  
  
 `SIG_ACK`  
 승인을 수신되었음을 나타냅니다.  
  
 `SIG_ERR`  
 오류가 발생했음을 나타내는 신호의 반환 형식  
  
## <a name="see-also"></a>참고 항목  
 [signal](../c-runtime-library/reference/signal.md)   
 [전역 상수](../c-runtime-library/global-constants.md)