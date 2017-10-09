---
title: _CRT_DISABLE_PERFCRIT_LOCKS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
dev_langs:
- C++
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: bb9a5662b15e6e4d0b6df09520263528f9fa72c5
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="crtdisableperfcritlocks"></a>_CRT_DISABLE_PERFCRIT_LOCKS
I/O 연산에서 성능이 중요한 잠금을 해제합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#define _CRT_DISABLE_PERFCRIT_LOCKS  
```  
  
## <a name="remarks"></a>설명  
 이 기호를 정의하면 모든 I/O 연산에서 단일 스레드 I/O 모델을 가정하도록 강제 지정하여 단일 스레드 I/O 바인딩 프로그램의 성능을 향상시킬 수 있습니다. [다중 스레드 라이브러리 성능](../c-runtime-library/multithreaded-libraries-performance.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [전역 상수](../c-runtime-library/global-constants.md)
