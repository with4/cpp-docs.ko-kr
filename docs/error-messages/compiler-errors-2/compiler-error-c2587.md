---
title: 컴파일러 오류 C2587 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2587
dev_langs:
- C++
helpviewer_keywords:
- C2587
ms.assetid: 7637a2c7-35d4-4b5a-a8f2-515a7bda98fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 595e14f71f9e1570893111efa38155a6f97e5574
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2587"></a>컴파일러 오류 C2587
'identifier': 기본 매개 변수로 잘못 된 지역 변수 사용  
  
 지역 변수는 기본 매개 변수로 사용할 수 없습니다.  
  
 다음 샘플에서는 C2587 오류가 생성 됩니다.  
  
```  
// C2587.cpp  
// compile with: /c  
int i;  
void func() {  
   int j;  
   extern void func2( int k = j );  // C2587 -- local variable  
   extern void func3( int k = i );   // OK  
}  
```