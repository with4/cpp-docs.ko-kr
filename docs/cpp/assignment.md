---
title: 할당 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], assignment
- assignment operators [C++], overloaded
ms.assetid: d87e4f89-f8f5-42c1-9d3c-184bca9d0e15
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27e78f7429c4d2a0f83ff7184460eb2ae69df129
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960988"
---
# <a name="assignment"></a>할당
대입 연산자 (**=**)는 엄밀 하, 이항 연산자입니다. 할당 연산자의 선언은 다음을 제외하고 다른 모든 이항 연산자와 동일합니다.  
  
-   비정적 멤버 함수여야 합니다. 아니오 **연산자 =** 비멤버 함수로 선언할 수 있습니다.  
  
-   파생 클래스가 상속하지 않습니다.  
  
-   기본값 **연산자 =** 존재 하지 않는 경우 클래스 형식에 대해 컴파일러에서 함수를 생성할 수 있습니다.  
  
 다음 예제에서는 할당 연산자를 선언하는 방법을 보여 줍니다.  
  
```cpp 
// assignment.cpp  
class Point  
{  
public:  
   Point &operator=( Point & );  // Right side is the argument.  
   int _x, _y;  
};  
  
// Define assignment operator.  
Point &Point::operator=( Point &ptRHS )  
{  
   _x = ptRHS._x;  
   _y = ptRHS._y;  
  
   return *this;  // Assignment operator returns left side.  
}  
  
int main()  
{  
}  
```  
  
 제공된 인수는 식의 오른쪽입니다. 연산자는 개체를 반환하여 할당 연산자의 동작을 보존하고, 할당 연산자는 할당이 완료된 후 왼쪽의 값을 반환합니다. 이에 따라 다음과 같은 문을 작성할 수 있습니다.  
  
```cpp 
pt1 = pt2 = pt3;  
```  
  
## <a name="see-also"></a>참고 항목  
 [연산자 오버로드](../cpp/operator-overloading.md)