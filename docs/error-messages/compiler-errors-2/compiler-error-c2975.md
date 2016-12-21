---
title: "컴파일러 오류 C2975 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2975"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2975"
ms.assetid: 526f6b9d-6c76-4c12-9252-1b1d7c1e06c7
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2975
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg' : 'type'의 템플릿 인수가 잘못되었습니다. 컴파일 타임 상수 식이 필요합니다.  
  
 템플릿 인수가 템플릿 선언과 일치하지 않습니다. 상수 식은 꺾쇠 괄호로 묶어야 합니다.  변수는 템플릿 실제 인수로 사용할 수 없습니다.  템플릿 정의를 확인하여 올바른 형식을 알아보십시오.  
  
 다음 샘플에서는 C2975 오류가 발생하는 경우를 보여 줍니다.  
  
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
  
 [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)와 함께 \_\_LINE\_\_을 컴파일 타임 상수로 사용하는 경우에도 C2975가 발생할 수 있습니다.  한 가지 해결 방안은 **\/ZI** 대신 [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)로 컴파일하는 것입니다.  
  
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