---
title: "컴파일러 오류 C2362 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2362
dev_langs:
- C++
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e3a921084d696e6cf7abebc75d02d403cbcda2be
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2362"></a>컴파일러 오류 C2362
'identifier' 초기화가 'goto 레이블' 의해 생략 되었습니다.  
  
 로 컴파일할 때 [/Za](../../build/reference/za-ze-disable-language-extensions.md), 레이블로 점프 식별자를 초기화할 수 없습니다.  
  
 를 입력 하지 않으면 하는 블록에서 선언 둘러싸입니다 않으면 이니셜라이저와 함께 선언 점프할 수 없습니다 또는 변수가 이미 초기화 되었습니다.  
  
 다음 샘플에서는 C2326을 생성합니다.  
  
```  
// C2362.cpp  
// compile with: /Za  
int main() {  
   goto label1;  
   int i = 1;      // C2362, initialization skipped  
label1:;  
}  
```  
  
 해결 방법:  
  
```  
// C2362b.cpp  
// compile with: /Za  
int main() {  
   goto label1;  
   {  
      int j = 1;   // OK, this block is never entered  
   }  
label1:;  
}  
```
