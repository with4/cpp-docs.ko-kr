---
title: "bad_typeid 예외 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "bad_typeid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_typeid 예외"
  - "예외, bad_typeid"
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# bad_typeid 예외
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`typeid`의 피연산자가 NULL 포인터인 경우 [typeid 연산자](../cpp/typeid-operator.md)가 `bad_typeid` 예외를 throw합니다.  
  
## 구문  
  
```  
  
      catch (bad_typeid)  
   statement  
```  
  
## 설명  
 `bad_typeid`의 인터페이스는 다음과 같습니다.  
  
```  
class bad_typeid : public exception  
{  
public:  
   bad_typeid(const char * _Message = "bad typeid");  
   bad_typeid(const bad_typeid &);  
   virtual ~bad_typeid();  
};  
```  
  
 다음 예제에서는 `bad_typeid` 예외를 throw하는 `typeid` 연산자를 보여 줍니다.  
  
```  
// expre_bad_typeid.cpp  
// compile with: /EHsc /GR  
#include <typeinfo.h>  
#include <iostream>  
  
class A{  
public:  
   // object for class needs vtable  
   // for RTTI  
   virtual ~A();  
};  
  
using namespace std;  
int main() {  
A* a = NULL;  
  
try {  
   cout << typeid(*a).name() << endl;  // Error condition  
   }  
catch (bad_typeid){  
   cout << "Object is NULL" << endl;  
   }  
}  
```  
  
## Output  
  
```  
Object is NULL  
```  
  
## 참고 항목  
 [런타임 형식 정보](../cpp/run-time-type-information.md)   
 [C\+\+ 키워드](../cpp/keywords-cpp.md)