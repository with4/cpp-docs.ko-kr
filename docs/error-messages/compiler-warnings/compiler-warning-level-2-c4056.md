---
title: "컴파일러 경고 (수준 2) C4056 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4056
dev_langs:
- C++
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 78b95111e69cdb8b27e65654fbf64756786d2097
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4056"></a>컴파일러 경고 (수준 2) C4056
부동 소수점 상수 산술 연산에서 오버플로가 발생 했습니다  
  
 부동 소수점 상수 산술 연산에 허용 되는 최대값을 초과 하는 결과 생성 합니다.  
  
 이 경고는 컴파일러 최적화 상수 산술 연산 중에 수행 하 여 발생할 수 있습니다. 최적화를 해제할 때 하는 경우이 경고는 무시 해도 ([/Od](../../build/reference/od-disable-debug.md)).  
  
 다음 샘플에서는 C4056 오류가 생성 됩니다.  
  
```  
// C4056.cpp  
// compile with: /W2 /LD  
#pragma warning (default : 4056)  
float fp_val = 1.0e300 * 1.0e300;   // C4056  
```