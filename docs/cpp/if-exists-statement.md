---
title: "__if_exists 문 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__if_exists_cpp"
  - "__if_exists"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__if_exists 키워드[C++]"
  - "식별자, 존재 테스트"
  - "기호, 존재 테스트"
ms.assetid: d3eb34b6-f3a9-4063-a286-b62a28c0c7fa
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# __if_exists 문
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`__if_exists` 문은 지정된 식별자가 있는지 여부를 테스트합니다.  식별자가 있는 경우 지정된 문 블록이 실행됩니다.  
  
## 구문  
  
```  
__if_exists ( identifier ) {   
statements  
};  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`identifier`|존재 여부를 테스트할 식별자입니다.|  
|`statements`|`identifier`가 있는 경우 실행할 하나 이상의 문입니다.|  
  
## 설명  
  
> [!CAUTION]
>  가장 안정적인 결과를 얻으려면 다음 제약 조건하에서 `__if_exists` 문을 사용합니다.  
  
-   템플릿이 아니라 단순 형식에만 `__if_exists` 문을 적용합니다.  
  
-   클래스 내부 또는 외부 모두에서 `__if_exists` 문을 식별자에 적용합니다.  지역 변수에는 `__if_exists` 문을 적용하지 마십시오.  
  
-   함수의 본문에서만 `__if_exists` 문을 사용합니다.  함수의 본문 외부에서 `__if_exists` 문은 완전히 정의된 형식만 테스트할 수 있습니다.  
  
-   오버로드된 함수에 대해 테스트할 때 특정 양식의 오버로드를 테스트할 수 없습니다.  
  
 `__if_exists` 문을 보완하는 문은 [\_\_if\_not\_exists](../cpp/if-not-exists-statement.md)입니다.  
  
## 예제  
 다음 예제에서는 템플릿을 사용하지만, 이는 권장되는 방법은 아닙니다.  
  
```  
// the__if_exists_statement.cpp  
// compile with: /EHsc  
#include <iostream>  
  
template<typename T>  
class X : public T {  
public:  
   void Dump() {  
      std::cout << "In X<T>::Dump()" << std::endl;  
  
      __if_exists(T::Dump) {  
         T::Dump();  
      }  
  
      __if_not_exists(T::Dump) {  
         std::cout << "T::Dump does not exist" << std::endl;  
      }  
   }     
};  
  
class A {  
public:  
   void Dump() {  
      std::cout << "In A::Dump()" << std::endl;  
   }  
};  
  
class B {};  
  
bool g_bFlag = true;  
  
class C {  
public:  
   void f(int);  
   void f(double);  
};  
  
int main() {   
   X<A> x1;  
   X<B> x2;  
  
   x1.Dump();  
   x2.Dump();  
  
   __if_exists(::g_bFlag) {  
      std::cout << "g_bFlag = " << g_bFlag << std::endl;  
   }  
  
   __if_exists(C::f) {  
      std::cout << "C::f exists" << std::endl;  
   }  
  
   return 0;  
}  
```  
  
## Output  
  
```  
In X<T>::Dump()  
In A::Dump()  
In X<T>::Dump()  
T::Dump does not exist  
g_bFlag = 1  
C::f exists  
```  
  
## 참고 항목  
 [선택문](../cpp/selection-statements-cpp.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)   
 [\_\_if\_not\_exists 문](../cpp/if-not-exists-statement.md)