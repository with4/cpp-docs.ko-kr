---
title: "명시적 형식 변환 연산자: () | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- explicit data type conversion operator
- conversions [C++], explicit
- operators [C++], explicit type conversion
- data type conversion [C++], explicit
- type conversion [C++], explicit conversions
ms.assetid: 54272006-5ffb-45ed-8283-27152ab97529
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 806a943ff9f5ebd0c6971340b66266aa7da9c0c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="explicit-type-conversion-operator-"></a>명시적 형식 변환 연산자: ()
C++에서는 함수 호출 구문과 유사한 구문을 사용하여 명시적인 형식 변환을 수행할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
simple-type-name ( expression-list )  
```  
  
## <a name="remarks"></a>설명  
 A *단순 형식 이름* 이어서는 *식 목록* 괄호 구문에서 지정 된 식을 사용 하 여 지정 된 형식의 개체를 포함 합니다. 다음 예제에서는 int 형식으로의 명시적 형식 변환을 보여 줍니다.  
  
```  
int i = int( d );  
```  
  
 다음 예제에서는 한 `Point` 클래스입니다.  
  
## <a name="example"></a>예  
  
```  
// expre_Explicit_Type_Conversion_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
class Point  
{  
public:  
    // Define default constructor.  
    Point() { _x = _y = 0; }  
    // Define another constructor.  
    Point( int X, int Y ) { _x = X; _y = Y; }  
  
    // Define "accessor" functions as  
    // reference types.  
    unsigned& x() { return _x; }  
    unsigned& y() { return _y; }  
    void Show()   { cout << "x = " << _x << ", "  
                         << "y = " << _y << "\n"; }  
private:  
    unsigned _x;  
    unsigned _y;  
};  
  
int main()  
{  
    Point Point1, Point2;  
  
    // Assign Point1 the explicit conversion  
    //  of ( 10, 10 ).  
    Point1 = Point( 10, 10 );  
  
    // Use x() as an l-value by assigning an explicit  
    //  conversion of 20 to type unsigned.  
    Point1.x() = unsigned( 20 );  
    Point1.Show();  
  
    // Assign Point2 the default Point object.  
    Point2 = Point();  
    Point2.Show();  
}  
```  
  
## <a name="output"></a>출력  
  
```  
x = 20, y = 10  
x = 0, y = 0  
```  
  
 위의 예제에서는 상수를 사용한 명시적 형식 변환을 보여 주지만 개체에서 이러한 변환을 수행할 때도 동일한 기술을 사용할 수 있습니다. 다음 코드 조각에서 이를 보여 줍니다.  
  
```  
int i = 7;  
float d;  
  
d = float( i );  
```  
  
 "캐스트" 구문을 사용하여 명시적 형식 변환을 지정할 수도 있습니다. 캐스트 구문을 사용하여 다시 작성한 이전 예제는 다음과 같습니다.  
  
```  
d = (float)i;  
```  
  
 캐스트 스타일 변환과 함수 스타일 변환 모두 단일 값에서 변환할 때 동일한 결과를 생성합니다. 그러나 함수 스타일 구문에서는 변환을 위해 인수를 둘 이상 지정할 수 있습니다. 이 차이점은 사용자 정의 형식의 경우 중요합니다. `Point` 클래스 및 해당 변환을 고려해 보십시오.  
  
```  
struct Point  
{  
    Point( short x, short y ) { _x = x; _y = y; }  
    ...  
    short _x, _y;  
};  
...  
Point pt = Point( 3, 10 );  
```  
  
 앞의 예에서 함수 스타일 변환을 사용 하는 두 값을 변환 하는 방법을 보여 줍니다 (에 대 한 *x* 되 고 다른 하나 *y*) 사용자 정의 형식에 `Point`합니다.  
  
> [!CAUTION]
>  명시적 형식 변환은 C++ 컴파일러의 기본 제공 형식 검사를 재정의하므로 신중하게 사용하십시오.  
  
 [캐스트](../cpp/cast-operator-parens.md) 표기법을 사용 하 여가 없는 형식으로의 변환 해야는 *단순 형식 이름* (예: 포인터 또는 참조 형식). 변환으로 표현할 수 있는 형식에는 *단순 형식 이름* 둘 중 하나의 형태로 작성할 수 있습니다. 참조 [형식 지정자](http://msdn.microsoft.com/en-us/34b6c737-0ef1-4470-9b77-b26e46c0bbd4) 구성 하는 항목에 대 한 자세한 내용은 *단순 형식 이름*합니다.  
  
 캐스트 내의 형식 정의는 올바르지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [후 위 식](../cpp/postfix-expressions.md)   
 [C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)