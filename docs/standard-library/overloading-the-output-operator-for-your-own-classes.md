---
title: "고유 클래스에 대해 &lt;&lt; 연산자 오버로드 | Microsoft Docs"
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
  - "연산자 <<, 사용자 고유의 클래스를 위한 오버로딩"
  - "operator<<, 사용자 고유의 클래스를 위한 오버로딩"
ms.assetid: ad1d2c49-d84e-48a8-9c09-121f28b10bf0
caps.latest.revision: 12
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 고유 클래스에 대해 &lt;&lt; 연산자 오버로드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Output streams use the insertion \(`<<`\) operator for standard types.  You can also overload the `<<` operator for your own classes.  
  
## 예제  
 The `write` function example showed the use of a `Date` structure.  A date is an ideal candidate for a C\+\+ class in which the data members \(month, day, and year\) are hidden from view.  An output stream is the logical destination for displaying such a structure.  This code displays a date using the `cout` object:  
  
```  
Date dt( 1, 2, 92 );  
cout << dt;  
```  
  
 To get `cout` to accept a `Date` object after the insertion operator, overload the insertion operator to recognize an `ostream` object on the left and a `Date` on the right.  The overloaded `<<` operator function must then be declared as a friend of class `Date` so it can access the private data within a `Date` object.  
  
```  
// overload_date.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
class Date  
{  
    int mo, da, yr;  
public:  
    Date(int m, int d, int y)  
    {  
        mo = m; da = d; yr = y;  
    }  
    friend ostream& operator<<(ostream& os, const Date& dt);  
};  
  
ostream& operator<<(ostream& os, const Date& dt)  
{  
    os << dt.mo << '/' << dt.da << '/' << dt.yr;  
    return os;  
}  
  
int main()  
{  
    Date dt(5, 6, 92);  
    cout << dt;  
}  
```  
  
  **5\/6\/92**   
## 설명  
 The overloaded operator returns a reference to the original `ostream` object, which means you can combine insertions:  
  
```  
cout << "The date is" << dt << flush;  
```  
  
## 참고 항목  
 [Output Streams](../standard-library/output-streams.md)