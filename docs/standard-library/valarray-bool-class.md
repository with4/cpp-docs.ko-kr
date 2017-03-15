---
title: "valarray&lt;bool&gt; 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "valarray<bool>"
  - "valarray/std::valarray<bool>"
  - "std::valarray<bool>"
  - "std.valarray<bool>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "valarray<bool> 클래스"
ms.assetid: fc0e7121-4758-4ea5-86c3-f04448f04acf
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# valarray&lt;bool&gt; 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

A specialized version of the template class **valarray\<Type\>** to elements of type `bool`.  
  
## 구문  
  
```  
  
class valarray<bool>  
  
```  
  
## 예제  
  
```  
// valarray_bool.cpp  
// compile with: /EHsc  
#include <valarray>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   int i;  
  
   valarray<int> vaL ( 10 ), vaR ( 10 );  
   valarray<bool> vaBool ( 10 );  
   for ( i = 0 ; i < 10 ; i += 2 )   
      vaL [ i ] =  -i;  
   for ( i = 1 ; i < 10 ; i += 2 )   
      vaL [ i ] =  i;  
   for ( i = 0 ; i < 10 ; i++ )   
      vaR [ i ] =  i;  
  
   cout << "The initial Left valarray is: ( ";  
   for ( i = 0 ; i < 10 ; i++ )  
      cout << vaL [ i ] << " ";  
   cout << ")." << endl;  
  
   cout << "The initial Right valarray is: ( ";  
   for ( i = 0 ; i < 10 ; i++ )  
      cout << vaR [ i ] << " ";  
   cout << ")." << endl;  
  
   vaBool = ( vaL < vaR );  
   cout << "The result of the less-than comparison "  
   << "test is the\n valarray<bool>: ( ";  
   for ( i = 0 ; i < 10 ; i++ )  
      cout << vaBool [ i ] << " ";  
   cout << ")." << endl;  
}  
```  
  
  **The initial Left valarray is: \( 0 1 \-2 3 \-4 5 \-6 7 \-8 9 \).**  
**The initial Right valarray is: \( 0 1 2 3 4 5 6 7 8 9 \).**  
**The result of the less\-than comparison test is the**  
 **valarray\<bool\>: \( 0 0 1 0 1 0 1 0 1 0 \).**   
## 요구 사항  
 **Header:** \<valarray\>  
  
 **네임스페이스:** std  
  
## 참고 항목  
 [valarray 클래스](../standard-library/valarray-class.md)   
 [C\+\+ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)