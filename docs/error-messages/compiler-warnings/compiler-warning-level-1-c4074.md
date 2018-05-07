---
title: 컴파일러 경고 (수준 1) C4074 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4074
dev_langs:
- C++
helpviewer_keywords:
- C4074
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9072728660ca78097a1e36e492670a614bb2b2f8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4074"></a>컴파일러 경고 (수준 1) C4074
이니셜라이저가 컴파일러 예약 초기화 영역  
  
 지정 된 컴파일러 초기화 영역 [#pragma init_seg](../../preprocessor/init-seg.md), Microsoft에서 예약 됩니다. C 런타임 라이브러리를 초기화 하기 전에이 영역에는 코드를 실행할 수 있습니다.  
  
 다음 샘플에서는 C4074 오류가 생성 됩니다.  
  
```  
// C4074.cpp  
// compile with: /W1  
#pragma init_seg( compiler )   // C4074  
  
// try this line to resolve the warning  
// #pragma init_seg(user)  
  
int main() {  
}  
```