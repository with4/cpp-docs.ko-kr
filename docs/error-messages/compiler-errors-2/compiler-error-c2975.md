---
title: "컴파일러 오류 C2975 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2975
dev_langs:
- C++
helpviewer_keywords:
- C2975
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 07b2b96cd79364215c9a859a9fd0282768ff45e4
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2975"></a>컴파일러 오류 C2975
'arg': 'type', 필요한 컴파일 시간 상수 식에 대 한 잘못 된 템플릿 인수  
  
 템플릿 인수 템플릿 선언; 일치 하지 않습니다. 상수 식 꺾쇠 괄호 안에 표시 됩니다. 변수는 템플릿 실제 인수로 허용 되지 않습니다. 템플릿 정의를 확인하여 올바른 형식을 찾습니다.  
  
 다음 샘플에서는 C2975 오류가 생성 됩니다.  
  
```  
// C2975.cpp  
template<int I>  
class X {};  
  
int main() {  
   int i = 4, j = 2;  
   X<i + j> x1;   // C2975  
   X<6> x2;   // OK  
}  
```  
  
 C2975 __LINE를 사용 하는 경우에 발생 합니다\_ \_ 컴파일 타임 상수와 [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)합니다. 문제를 해결할 수로 컴파일하여 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) 대신 **/ZI**합니다.  
  
```  
// C2975b.cpp  
// compile with: /ZI  
// processor: x86  
template<long line>   
void test(void) {}  
  
int main() {  
   test<__LINE__>();   // C2975  
}  
```
