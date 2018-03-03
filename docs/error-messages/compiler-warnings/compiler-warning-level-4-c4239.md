---
title: "컴파일러 경고 (수준 4) C4239 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4239
dev_langs:
- C++
helpviewer_keywords:
- C4239
ms.assetid: a23dc16a-649e-4870-9a24-275de1584fcd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18f1c6d700de0c621ebde02c7dcb2817091677cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4239"></a>컴파일러 경고(수준 4) C4239
비표준 확장이 사용 됨: 'token': 'type'에서 'type'으로 변환  
  
 이러한 형식 변환은 c + + 표준에서 허용 되지 않지만 특성이 확장 합니다. 이 경고 뒤에 항상 하나 이상 줄 설명이 언어 규칙을 위반 합니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 c 4239 합니다.  
  
```  
// C4239.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
void func(void) {  
   C & rC = C();   // C4239  
   const C & rC2 = C();   // OK  
   rC2;  
}  
```  
  
## <a name="example"></a>예  
 정수 계열 형식에서 열거형 형식 변환 엄격 하 게 허용 되지 않습니다.  
  
 다음 샘플에서는 c 4239 합니다.  
  
```  
// C4239b.cpp  
// compile with: /W4 /c  
enum E { value };   
struct S {   
   E e : 2;   
} s = { 5 };   // C4239   
// try the following line instead  
// } s = { (E)5 };  
```