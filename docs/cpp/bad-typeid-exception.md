---
title: "bad_typeid 예외 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- bad_typeid
- bad_typeid_cpp
dev_langs:
- C++
helpviewer_keywords:
- bad_typeid exception
- exceptions [C++], bad_typeid
ms.assetid: 5963ed58-4ede-4597-957d-f7bbd06299c2
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: ea7dc85862622180038cf520ef92b752b65eba84
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="badtypeid-exception"></a>bad_typeid 예외
`bad_typeid` 예외를 throw 하는 [typeid 연산자](../cpp/typeid-operator.md) 때 피연산자 `typeid` 는 NULL 포인터입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      catch (bad_typeid)  
   statement  
```  
  
## <a name="remarks"></a>설명  
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
  
 다음 예제에서는 `typeid` 예외를 throw하는 `bad_typeid` 연산자를 보여 줍니다.  
  
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
  
## <a name="output"></a>출력  
  
```  
Object is NULL  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 형식 정보](../cpp/run-time-type-information.md)   
 [키워드](../cpp/keywords-cpp.md)
