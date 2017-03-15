---
title: "컴파일러 오류 C3535 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3535"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3535"
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3535
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type2'에서 'type1'의 형식을 추론할 수 없습니다.  
  
 `auto` 키워드로 선언된 변수의 형식은 초기화 식의 형식에서 추론할 수 없습니다.  예를 들어, 초기화 식이 형식이 아닌 `void`로 평가되는 경우 이 오류가 발생합니다.  
  
### 이 오류를 해결하려면  
  
1.  초기화 식의 형식이 `void`가 아닌지 확인합니다.  
  
2.  선언이 기본 형식에 대한 포인터가 아닌지 확인합니다.  자세한 내용은 [기본 형식](../../cpp/fundamental-types-cpp.md)을 참조하십시오.  
  
3.  선언이 형식에 대한 포인터인 경우 초기화 식이 포인터 형식인지 확인합니다.  
  
## 예제  
 다음 예제에서는 초기화 식이 `void`로 평가되기 때문에 C3535가 발생합니다.  
  
```  
// C3535a.cpp  
// Compile with /Zc:auto  
void f(){}  
int main()  
{  
   auto x = f();   //C3535  
   return 0;  
}  
```  
  
## 예제  
 다음 예제에서는 문에서 `x` 변수가 추론된 형식에 대한 포인터로 선언되지만 초기화 식의 형식은 double이기 때문에 C3535가 발생합니다.  따라서 컴파일러가 변수의 형식을 추론할 수 없습니다.  
  
```  
// C3535b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto* x = 123.0;   // C3535  
   return 0;  
}  
```  
  
## 예제  
 다음 예제에서는 `p` 변수가 추론된 형식에 대한 포인터로 선언되지만 초기화 식이 포인터 형식이 아니기 때문에 C3535가 발생합니다.  
  
```  
// C3535c.cpp  
// Compile with /Zc:auto  
class A { };  
A x;  
auto *p = x;  // C3535  
```  
  
## 참고 항목  
 [auto 키워드](../../cpp/auto-keyword.md)   
 [기본 형식](../../cpp/fundamental-types-cpp.md)