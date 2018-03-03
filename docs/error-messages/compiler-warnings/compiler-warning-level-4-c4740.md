---
title: "컴파일러 경고 (수준 4) C4740 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4740
dev_langs:
- C++
helpviewer_keywords:
- C4740
ms.assetid: 85528969-966a-44b4-8a2f-971704c64477
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 92a94e2f26a0781d736d7e8eeecd76ac62a81255
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4740"></a>컴파일러 경고(수준 4) C4740
내부 / 외부로 인라인 asm 코드 흐름을 선택 하면 전역 최적화  
  
 또는의 점프 경우는 `asm` 블록, 해당 함수에 대 한 전역 최적화가 해제 됩니다.  
  
 다음 샘플에서는 C4740 오류가 생성 됩니다.  
  
```  
// C4740.cpp  
// compile with: /O2 /W4  
// processor: x86  
int main() {  
   __asm jmp tester  
   tester:;  
}  
```