---
title: "컴파일러 경고 (수준 1) C4028 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4028
dev_langs:
- C++
helpviewer_keywords:
- C4028
ms.assetid: c3e8b70b-e870-416c-a285-bba5f71dbfc6
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0041d795ed5afce50592f21f41986d3f32c71fe3
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-level-1-c4028"></a>컴파일러 경고 (수준 1) C4028
'number' 선언에서 다른 형식 매개 변수  
  
 형식 매개 변수의 형식 선언에서 해당 매개 변수와 함께 일치 하지 않습니다. 원래 선언에 형식이 사용 됩니다.  
  
 이 경고 C 소스 코드에 대해서만 유효합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4028 오류가 발생 합니다.  
  
```  
// C4028.c  
// compile with: /W1 /Za  
void f(int , ...);  
void f(int i, int j) {}   // C4028  
  
void g(int , int);  
void g(int i, int j) {}   // OK  
  
int main() {}  
```
