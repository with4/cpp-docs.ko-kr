---
title: "negate 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "negate"
  - "std.negate"
  - "std::negate"
  - "xfunctional/std::negate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "negate 구조체"
  - "negate 클래스"
ms.assetid: 8a372686-786e-4262-b37c-ca13dc11e62f
caps.latest.revision: 20
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# negate 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

해당 인수에서 산술 부정 연산을 \(단항 `operator-`\) 수행하는 미리 정의된 함수 개체입니다.  
  
## 구문  
  
```  
template<class Type = void>  
   struct negate : public unary_function<Type, Type>   
   {  
      Type operator()(  
         const Type& Left  
      ) const;  
   };  
  
// specialized transparent functor for unary operator-  
template<>  
   struct negate<void>  
   {  
      template<class Type>  
      auto operator()(Type&& Left) const  
         -> decltype(-std::forward<Type>(Left));  
   };  
  
```  
  
#### 매개 변수  
 `Type`  
 유추 또는 지정된 형식의 피연산자를 사용하는 `operator-` 를 지원하는 모든 형식입니다.  
  
 `Left`  
 피연산자는 부정합니다.  특수화 되지 않은 템플릿은 암시된 `Type` 형식의 lvalue 및 rvalue 참조 인수 형식의 전달을 완벽히 수행합니다.  
  
## 반환 값  
 `-`   `Left.` 의 결과, 특수 템플릿은 형식은   `operator-` 단항에서 반환 되는 결과를 완벽히 전달한다.  
  
## 예제  
  
```  
// functional_negate.cpp  
// compile with: /EHsc  
#include <vector>  
#include <functional>  
#include <algorithm>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   vector <int> v1, v2 ( 8 );  
   vector <int>::iterator Iter1, Iter2;  
  
   int i;  
   for ( i = -2 ; i <= 5 ; i++ )  
   {  
      v1.push_back( 5 * i );  
   }  
  
   cout << "The vector v1 = ( " ;  
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )  
      cout << *Iter1 << " ";  
   cout << ")" << endl;  
  
   // Finding the element-wise negatives of the vector v1  
   transform ( v1.begin( ),  v1.end( ), v2.begin( ), negate<int>( ) );  
  
   cout << "The negated elements of the vector = ( " ;  
   for ( Iter2 = v2.begin( ) ; Iter2 != v2.end( ) ; Iter2++ )  
      cout << *Iter2 << " ";  
   cout << ")" << endl;  
}  
```  
  
  **벡터 v1 1 \= \( \-10 \-5 0 5 10 15 20 25 \)**  
**벡터의 부정된 요소 \= \(10 5 0\-5\-10\-15\-20\-25\)**   
## 요구 사항  
 **헤더:** \<기능\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [표준 템플릿 라이브러리](../misc/standard-template-library.md)