---
title: "컴파일러 경고 (수준 1) C4319 | Microsoft Docs"
ms.custom: 
ms.date: 1/18/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4319
dev_langs:
- C++
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a492194003a639f684e84d125450067cd425276
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="compiler-warning-level-1-c4319"></a>컴파일러 경고(수준 1) C4319

> ' ~': 0 확장 '*type1*'to'*type2*' 더 큰

결과  **~**  (비트 보수) 연산자 서명 되지 않은 경우는 이며 다음 0 확장 더 큰 유형으로 변환 됩니다.

## <a name="example"></a>예

다음 예에서 `~(a - 1)` 32 비트 부호 없는 long 식으로 계산 되 고 다음 0 확장을 통해 64 비트로 변환 합니다. 따라서 예기치 않은 결과가 발생할 수 있습니다.

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
