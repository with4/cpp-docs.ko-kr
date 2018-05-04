---
title: static_cast 연산자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- static_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- static_cast keyword [C++]
ms.assetid: 1f7c0c1c-b288-476c-89d6-0e2ceda5c293
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a0cd6ea7e2268940febca9e1e564f30d29dcff0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="staticcast-operator"></a>static_cast 연산자
변환는 *식* 유형과 *유형 id* 식에 있는 형식에 대해서만 기반으로 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
static_cast <type-id> ( expression )   
```  
  
## <a name="remarks"></a>설명  
 표준 C++에서는 변환의 안전성을 보장하기 위해 런타임 형식 검사가 수행되지 않습니다. C++/CX에서는 컴파일 시간 및 런타임 검사가 수행됩니다. 자세한 내용은 참조 [캐스팅](casting.md)합니다.  
  
 `static_cast` 연산자는 기본 클래스에 대한 포인터에서 파생된 클래스에 대한 포인터로의 변환과 같은 연산에 사용할 수 있습니다. 이러한 변환이 항상 안전한 것은 아닙니다.  
  
 일반적으로 열거형을 정수로 또는 정수를 부동 수로 변환하는 경우와 같이 숫자 데이터 형식을 변환할 때 변환에 사용할 데이터 형식을 확실히 아는 경우 `static_cast`를 사용합니다. `static_cast`는 `dynamic_cast`와 달리 런타임 형식 검사를 수행하지 않으므로 `static_cast` 변환은 `dynamic_cast` 변환만큼 안전하지 않습니다. 모호한 포인터에 대한 `dynamic_cast`는 실패하는 반면, `static_cast`는 잘못된 것이 없는 것처럼 반환합니다. 이는 위험할 수 있습니다. `dynamic_cast` 변환이 더욱 안전하기는 하지만 `dynamic_cast`는 포인터나 참조에서만 작동하며 런타임 형식 확인은 오버헤드입니다. 자세한 내용은 참조 [dynamic_cast Operator](../cpp/dynamic-cast-operator.md)합니다.  
  
 다음에 나오는 예제에서 `D* pd2 = static_cast<D*>(pb);` 줄은 `D`에서 `B`에 있지 않은 필드와 메서드를 가질 수 있기 때문에 안전하지 않습니다. 그러나 `B* pb2 = static_cast<B*>(pd);`는 항상 모든 `D`를 포함하기 때문에 `B` 줄의 변환은 안전합니다.  
  
```  
// static_cast_Operator.cpp  
// compile with: /LD  
class B {};  
  
class D : public B {};  
  
void f(B* pb, D* pd) {  
   D* pd2 = static_cast<D*>(pb);   // Not safe, D can have fields  
                                   // and methods that are not in B.  
  
   B* pb2 = static_cast<B*>(pd);   // Safe conversion, D always  
                                   // contains all of B.  
}  
```  
  
 달리 [dynamic_cast](../cpp/dynamic-cast-operator.md), 런타임 검사가 수행 되지 않습니다에 `static_cast` 변환 `pb`합니다. `pb`가 가리키는 개체는 유형 `D`의 개체가 아닐 수 있으며, 이 경우 `*pd2`를 사용하는 것은 매우 위험합니다. 예를 들어 `D` 클래스가 아닌 `B` 클래스의 멤버인 함수를 호출하면 액세스 위반이 발생할 수 있습니다.  
  
 `dynamic_cast` 및 `static_cast` 연산자는 클래스 계층 구조 전체에서 포인터를 이동시킵니다. 하지만 `static_cast`는 캐스트 문에서 제공하는 정보에 전적으로 의존하고 있으므로 안전하지 않을 수 있습니다. 예를 들어:  
  
```  
// static_cast_Operator_2.cpp  
// compile with: /LD /GR  
class B {  
public:  
   virtual void Test(){}  
};  
class D : public B {};  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  
   D* pd2 = static_cast<D*>(pb);  
}  
```  
  
 `pb`가 `D` 형식의 개체를 가리킬 경우 `pd1` 및 `pd2`는 동일한 값을 얻습니다. 또한 `pb == 0`일 경우 같은 값을 얻습니다.  
  
 `pb`가 완전한 `B` 클래스를 가리키지 않고 `D` 형식의 개체를 가리킬 경우 `dynamic_cast`는 0을 반환합니다. 그러나 `static_cast`는 프로그래머의 어설션에 사용되는 `pb` 형식의 개체인 `D` 형식을 가리키며 `D` 개체에 포인터를 반환합니다.  
  
 따라서 `static_cast`는 암시적 변환과 반대로 진행할 수 있습니다. 이 경우 결과는 정의되지 않습니다. 프로그래머는 `static_cast` 변환의 결과가 안전한지 확인해야 합니다.  
  
 이 동작은 클래스 형식 이외의 형식에도 적용됩니다. 예를 들어 `static_cast`는 정수를 `char`로 변환하는 데 사용할 수 있습니다. 하지만 결과로 나오는 `char`에는 충분한 비트가 없으므로 전체 `int` 값을 보유할 수 없습니다. 다시 남아 있는지 확인 하는 프로그래머를의 결과 `static_cast` 변환은 안전 합니다.  
  
 `static_cast` 연산자는 표준 변환 및 사용자 지정 변환을 포함하는 모든 암시적 변환에 사용할 수 있습니다. 예를 들어:  
  
```  
// static_cast_Operator_3.cpp  
// compile with: /LD /GR  
typedef unsigned char BYTE;  
  
void f() {  
   char ch;  
   int i = 65;  
   float f = 2.5;  
   double dbl;  
  
   ch = static_cast<char>(i);   // int to char  
   dbl = static_cast<double>(f);   // float to double  
   i = static_cast<BYTE>(ch);  
}  
```  
  
 `static_cast` 연산자는 명시적으로 정수 값을 열거 형식으로 변환할 수 있습니다. 정수 계열 형식의 값이 열거형 값 범위에 속하지 않으면 결과 열거형 값이 정의되지 않습니다.  
  
 `static_cast` 연산자는 null 포인터 값을 대상 형식의 null 포인터 값으로 변환합니다.  
  
 모든 식은 `static_cast` 연산자에 의해 void 형식으로 명시적으로 변환될 수 있습니다. 대상 void 형식은 선택적으로 `const`, `volatile` 또는 `__unaligned` 특성을 포함시킬 수 있습니다.  
  
 `static_cast` 연산자는 `const`, `volatile` 또는 `__unaligned` 특성과 떨어져 캐스팅할 수 없습니다. 참조 [const_cast 연산자](../cpp/const-cast-operator.md) 이러한 특성을 제거에 대 한 내용은 합니다.  
  
 재배치하는 가비지 컬렉션의 상단에서 확인되지 않은 캐스팅을 수행하는 위험으로 인해 올바르게 작동한다고 확신할 때만 성능에 중요한 코드에서만 `static_cast`를 사용해야 합니다. 사용 해야 할 경우 `static_cast` 릴리스 모드에서 사용 하 여 대체 [safe_cast](../windows/safe-cast-cpp-component-extensions.md) 성공을 위해 디버그 빌드에서 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [캐스팅 연산자](../cpp/casting-operators.md)   
 [키워드](../cpp/keywords-cpp.md)