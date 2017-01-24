---
title: "pair 구조체 | Microsoft Docs"
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
  - "utility/std::pair"
  - "pair"
  - "std::pair"
  - "std.pair"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pair 클래스"
ms.assetid: 539d3d67-80a2-4170-b347-783495d42109
caps.latest.revision: 20
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pair 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

두 개체를 단일 개체로 처리하는 기능을 제공하는 구조체입니다.  
  
## 구문  
  
```  
template<class T1, class T2>  
   struct pair   
   {  
   typedef T1 first_type;  
   typedef T2 second_type;  
   T1 first;  
   T2 second;  
  
   constexpr pair( );  
   constexpr pair(  
      const T1& Val1,   
      const T2& Val2  
   );  
  
   template<class Other1, class Other2>  
      constexpr pair(  
         const pair<Other1, Other2>& Right  
      );  
  
template<class Other1, class Other2>  
      constexpr pair(  
        const pair <Other1 Val1, Other2 Val2>&& Right  
      );  
  
   template<class Other1, class Other2>  
      constexpr pair(  
         Other1&& Val1, Other2&& Val2  
      );  
   };  
```  
  
#### 매개 변수  
 `Val1`  
 `pair`의 첫 번째 요소를 초기화하는 값입니다.  
  
 `Val2`  
 `pair`의 두 번째 요소를 초기화하는 값입니다.  
  
 `Right`  
 다른 쌍의 요소를 초기화하는 데 해당 값을 사용할 쌍입니다.  
  
## 반환 값  
 첫 번째\(기본값\) 생성자는 쌍의 첫 번째 요소를 **T1** 형식의 기본값으로 초기화하고, 두 번째 요소를 **T2** 형식의 기본값으로 초기화합니다.  
  
 두 번째 생성자는 쌍의 첫 번째 요소를 `Val1`로 초기화하고 두 번째 요소를 *Val2*로 초기화합니다.  
  
 세 번째\(템플릿\) 생성자는 쌍의 첫 번째 요소를 `Right`.**first**로 초기화하고 두 번째 요소를 `Right`.**second**로 초기화합니다.  
  
 네 번째 생성자는 [Rvalue 참조 선언자: &&](../cpp/rvalue-reference-declarator-amp-amp.md)를 사용하여 쌍의 첫 번째 요소를 `Val1`로 초기화하고 두 번째 요소를 *Val2*로 초기화합니다.  
  
## 설명  
 템플릿 구조체는 각각 **T1** 및 **T2** 형식의 개체 쌍을 저장합니다.  **first\_type** 형식은 템플릿 매개 변수 **T1**과 동일하고, **second\_type** 형식은 템플릿 매개 변수 **T2**와 동일합니다.  **T1** 및 **T2**는 각각 기본 생성자, 단일 인수 생성자 및 소멸자만 제공해야 합니다.  `pair` 형식의 모든 멤버는 형식이 **클래스**가 아니라 `struct`로 선언되었으므로 공용입니다.  쌍을 사용하는 두 가지 가장 일반적인 방법은 두 값을 반환하는 함수에 대한 반환 형식으로 사용하거나, 각 요소에 키와 값 형식이 둘 다 연결되어 있는 결합형 컨테이너 클래스 [map 클래스](../standard-library/map-class.md) 및 [multimap 클래스](../standard-library/multimap-class.md)에 대한 요소로 사용하는 것입니다.  후자의 경우 쌍 결합형 컨테이너에 대한 요구 사항을 충족하고 `pair`\<**const** `key_type`, `mapped_type`\> 형태의 값 형식을 갖습니다.  
  
## 예제  
  
```  
// utility_pair.cpp  
// compile with: /EHsc  
#include <utility>  
#include <map>  
#include <iomanip>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // Using the constructor to declare and initialize a pair  
   pair <int, double> p1 ( 10, 1.1e-2 );  
  
   // Compare using the helper function to declare and initialize a pair  
   pair <int, double> p2;  
   p2 = make_pair ( 10, 2.22e-1 );  
  
   // Making a copy of a pair  
   pair <int, double> p3 ( p1 );  
  
   cout.precision ( 3 );  
   cout << "The pair p1 is: ( " << p1.first << ", "   
        << p1.second << " )." << endl;  
   cout << "The pair p2 is: ( " << p2.first << ", "   
        << p2.second << " )." << endl;  
   cout << "The pair p3 is: ( " << p3.first << ", "   
        << p3.second << " )." << endl;  
  
   // Using a pair for a map element  
   map <int, int> m1;  
   map <int, int>::iterator m1_Iter;  
  
   typedef pair <int, int> Map_Int_Pair;  
  
   m1.insert ( Map_Int_Pair ( 1, 10 ) );  
   m1.insert ( Map_Int_Pair ( 2, 20 ) );  
   m1.insert ( Map_Int_Pair ( 3, 30 ) );  
  
   cout << "The element pairs of the map m1 are:";  
   for ( m1_Iter = m1.begin( ); m1_Iter != m1.end( ); m1_Iter++ )  
      cout << " ( " << m1_Iter -> first << ", "  
           << m1_Iter -> second << " )";  
   cout   << "." << endl;  
  
   // Using pair as a return type for a function  
   pair< map<int,int>::iterator, bool > pr1, pr2;  
   pr1 = m1.insert ( Map_Int_Pair ( 4, 40 ) );  
   pr2 = m1.insert ( Map_Int_Pair (1, 10 ) );  
  
   if( pr1.second == true )  
   {  
      cout << "The element (4,40) was inserted successfully in m1."  
           << endl;  
   }  
   else     
   {  
      cout << "The element with a key value of\n"  
           << " ( (pr1.first) -> first ) = " << ( pr1.first ) -> first   
           << " is already in m1,\n so the insertion failed." << endl;  
   }  
  
   if( pr2.second == true )  
   {  
      cout << "The element (1,10) was inserted successfully in m1."  
           << endl;  
   }  
   else     
   {  
      cout << "The element with a key value of\n"  
           << " ( (pr2.first) -> first ) = " << ( pr2.first ) -> first   
           << " is already in m1,\n so the insertion failed." << endl;  
   }  
}  
```  
  
  **쌍 p1은 \( 10, 0.011 \)입니다.  쌍 p2는 \( 10, 0.222 \)입니다.  쌍 p3은 \( 10, 0.011 \)입니다.  맵 m1의 요소 쌍은 \( 1, 10 \) \( 2, 20 \) \( 3, 30 \)입니다.  요소 \(4,40\)이 m1에 성공적으로 삽입되었습니다.  키 값이**  
 **\( \(pr2.first\) \-\> first \) \= 1인 요소가 이미 m1에 있으므로**  
 **삽입하지 못했습니다.**    
## 요구 사항  
 **헤더:** \<utility\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [Pair Logical 연산자](../misc/pair-logical-operator.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)