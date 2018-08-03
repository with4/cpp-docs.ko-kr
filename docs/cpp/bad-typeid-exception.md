---
title: bad_typeid 예외 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55718522bdbf618fb656eedc5c6afd59bfcaca08
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39409008"
---
# <a name="badtypeid-exception"></a>bad_typeid 예외
**bad_typeid** 예외를 throw 합니다 [typeid 연산자](../cpp/typeid-operator.md) 경우 피연산자 **typeid** 가 NULL 포인터.  
  
## <a name="syntax"></a>구문  
  
```  
catch (bad_typeid)  
   statement  
```  
  
## <a name="remarks"></a>설명  
 에 대 한 인터페이스 **bad_typeid** 됩니다.  
  
```cpp 
class bad_typeid : public exception  
{  
public:  
   bad_typeid(const char * _Message = "bad typeid");  
   bad_typeid(const bad_typeid &);  
   virtual ~bad_typeid();  
};  
```  
  
 다음 예제에서는 합니다 **typeid** 를 throw 하는 연산자는 **bad_typeid** 예외입니다.  
  
```cpp 
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
  
```Output 
Object is NULL  
```  
  
## <a name="see-also"></a>참고자료  
 [런타임 형식 정보](../cpp/run-time-type-information.md)   
 [키워드](../cpp/keywords-cpp.md)