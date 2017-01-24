---
title: "하나의 인수를 포함하는 출력 스트림 조작자(int 또는 long) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "출력 스트림, int 또는 long 인수 조작자"
ms.assetid: 338f3164-b5e2-4c5a-a605-7d9dc3629ca1
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 하나의 인수를 포함하는 출력 스트림 조작자(int 또는 long)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

The iostream class library provides a set of macros for creating parameterized manipulators.  Manipulators with a single `int` or `long` argument are a special case.  To create an output stream manipulator that accepts a single `int` or `long` argument \(like `setw`\), you must use the \_Smanip macro, which is defined in \<iomanip\>.  This example defines a `fillblank` manipulator that inserts a specified number of blanks into the stream:  
  
## 예제  
  
```  
// output_stream_manip.cpp  
// compile with: /GR /EHsc  
#include <iostream>  
#include <iomanip>  
using namespace std;  
  
void fb( ios_base& os, int l )  
{  
   ostream *pos = dynamic_cast<ostream*>(&os);  
   if (pos)  
   {  
      for( int i=0; i < l; i++ )  
      (*pos) << ' ';  
   };  
}  
  
_Smanip<int>  
   __cdecl fillblank(int no)  
   {     
   return (_Smanip<int>(&fb, no));  
   }  
  
int main( )  
{  
   cout << "10 blanks follow" << fillblank( 10 ) << ".\n";  
}  
```  
  
## 참고 항목  
 [인수 포함 사용자 지정 조작자](../standard-library/custom-manipulators-with-arguments.md)