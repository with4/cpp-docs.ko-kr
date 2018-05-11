---
title: 컴파일러 경고 (수준 3) C4018 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4018
dev_langs:
- C++
helpviewer_keywords:
- C4018
ms.assetid: 6e8cbb04-d914-4319-b431-cbc2fbe40eb1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5eb784c8a368b5f5836deaff17d07542519ba980
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4018"></a>컴파일러 경고 (수준 3) C4018
'expression': signed 또는 unsigned 일치 하지 않습니다.  
  
 부호 있는 정수와 부호 없는 숫자를 비교 해야 unsigned로 지정 된 값으로 변환 해야 합니다.  
  
 부호 있는 정수와 부호 없는 형식 테스트할 때 캐스팅 두 가지 유형 중 하는 경우이 경고를 해결할 수 있습니다.  
  
 다음 샘플에서는 C4018:  
  
```  
// C4018.cpp  
// compile with: /W3  
int main() {  
   unsigned int uc = 0;  
   int c = 0;  
   unsigned int c2 = 0;  
  
   if (uc < c) uc = 0;   // C4018  
  
   // OK  
   if (uc == c2) uc = 0;  
}  
```