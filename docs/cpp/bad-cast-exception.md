---
title: bad_cast 예외 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bad_cast
- bad_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a37ae011ec2f06a505063678f481e6e41696c86
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401369"
---
# <a name="badcast-exception"></a>bad_cast 예외
합니다 **bad_cast** 예외를 throw 합니다 **dynamic_cast** 참조 형식에 실패 한 캐스팅 결과로 연산자.  
  
## <a name="syntax"></a>구문  
  
```  
catch (bad_cast)  
   statement  
```  
  
## <a name="remarks"></a>설명  
 에 대 한 인터페이스 **bad_cast** 됩니다.  
  
```cpp 
class bad_cast : public exception {  
public:  
   bad_cast(const char * _Message = "bad cast");  
   bad_cast(const bad_cast &);  
   virtual ~bad_cast();  
};  
```  
  
 다음 코드에는 실패 한의 예가 포함 되어 있습니다. **dynamic_cast** 을 throw 합니다 **bad_cast** 예외입니다.  
  
```cpp 
// expre_bad_cast_Exception.cpp  
// compile with: /EHsc /GR  
#include <typeinfo.h>  
#include <iostream>  
  
class Shape {  
public:  
   virtual void virtualfunc() const {}  
};  
  
class Circle: public Shape {  
public:  
   virtual void virtualfunc() const {}  
};  
  
using namespace std;  
int main() {  
   Shape shape_instance;  
   Shape& ref_shape = shape_instance;  
   try {  
      Circle& ref_circle = dynamic_cast<Circle&>(ref_shape);   
   }  
   catch (bad_cast b) {  
      cout << "Caught: " << b.what();  
   }  
}  
```  
  
 캐스팅될 개체(모양)가 지정된 캐스트 형식(원)에서 파생되지 않으므로 예외가 throw됩니다. 예외를 방지하려면 `main`에 다음과 같은 선언을 추가합니다.  
  
```cpp 
Circle circle_instance;  
Circle& ref_circle = circle_instance;  
```  
  
 다음의 캐스트 감각을 반전 합니다 **시도** 같이 차단:  
  
```cpp 
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);  
```  
  
## <a name="see-also"></a>참고자료  
 [dynamic_cast 연산자](../cpp/dynamic-cast-operator.md)   
 [키워드](../cpp/keywords-cpp.md)   
 [C++ 예외 처리](../cpp/cpp-exception-handling.md)