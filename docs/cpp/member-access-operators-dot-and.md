---
title: "멤버 액세스 연산자: . 및 -&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "."
  - "->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ". operator"
  - "-> 연산자"
  - "점(.) 연산자"
  - "멤버 액세스"
  - "멤버 액세스, 식"
  - "멤버 액세스, 연산자"
  - "연산자[C++], 멤버 액세스"
  - "후위 연산자"
ms.assetid: f8fc3df9-d728-40c5-b384-276927f5f1b3
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 멤버 액세스 연산자: . 및 -&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
      postfix-expression   
      . name  
postfix-expression –> name  
```  
  
## 설명  
 멤버 액세스 연산자 **.** 및 **\-\>**는 구조체, 공용 구조체 및 클래스의 멤버를 참조하는 데 사용됩니다.  멤버 액세스 식에는 선택한 멤버의 값과 형식이 있습니다.  
  
 다음 두 가지 형태의 멤버 액세스 식이 있습니다.  
  
1.  첫 번째 형태에서 *postfix\-expression*은 구조체, 클래스 또는 공용 구조체 형식의 값을 나타내며, *name*은 지정된 구조체, 공용 구조체 또는 클래스의 멤버 이름을 지정합니다.  연산의 값은 *name*의 값이며 *postfix\-expression*이 l\-value인 경우 l\-value입니다.  
  
2.  두 번째 형태에서 *postfix\-expression*은 구조체, 공용 구조체 또는 클래스에 대한 포인터를 나타내며, *name*은 지정된 구조체, 공용 구조체 또는 클래스의 멤버 이름을 지정합니다.  값은 *name*의 값이며 l\-value입니다.  **–\>** 연산자는 포인터를 역참조합니다.  따라서 *e***–\>**`member` 및 **\(\****e***\)**.`member` 식\(여기서 *e*는 포인터를 나타냄\)은 동일한 결과를 생성합니다\(**–\>** 또는 **\*** 연산자가 오버로드되는 경우 제외\).  
  
## 예제  
 다음 예제에서는 두 가지 형태의 멤버 액세스 연산자를 보여 줍니다.  
  
```  
// expre_Selection_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
struct Date {  
   Date(int i, int j, int k) : day(i), month(j), year(k){}  
   int month;  
   int day;  
   int year;  
};  
  
int main() {  
   Date mydate(1,1,1900);  
   mydate.month = 2;     
   cout  << mydate.month << "/" << mydate.day  
         << "/" << mydate.year << endl;  
  
   Date *mydate2 = new Date(1,1,2000);  
   mydate2->month = 2;  
   cout  << mydate2->month << "/" << mydate2->day  
         << "/" << mydate2->year << endl;  
   delete mydate2;  
}  
```  
  
  **2\/1\/1900**  
**2\/1\/2000**   
## 참고 항목  
 [후위 식](../cpp/postfix-expressions.md)   
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [클래스 및 구조체](../cpp/classes-and-structs-cpp.md)   
 [구조체 및 공용 구조체 멤버](../c-language/structure-and-union-members.md)