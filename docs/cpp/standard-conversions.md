---
title: "표준 변환 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- standard conversions, categories of
- L-values [C++]
- conversions, standard
ms.assetid: ce7ac8d3-5c99-4674-8229-0672de05528d
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 97967ad789fe5491aec2be983f28a08e2c143b95
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="standard-conversions"></a>표준 변환
C++ 언어에서는 기본 형식 간의 변환을 정의합니다. 또한 포인터, 참조 및 멤버 포인터 파생 형식에 대한 변환도 정의합니다. 이러한 변환을 "표준 변환"이라고 합니다. (형식, 표준 형식 및 파생된 형식에 대 한 자세한 내용은 참조 [형식](http://msdn.microsoft.com/en-us/6882ee83-ea32-4373-8d57-c3efbbc15af0).)  
  
 이 단원에서는 다음과 같은 표준 변환에 대해 설명합니다.  
  
-   정수 계열 확장  
  
-   정수 계열 변환  
  
-   부동 변환  
  
-   부동 및 정수 계열 변환  
  
-   산술 변환  
  
-   포인터 변환  
  
-   참조 변환  
  
-   멤버 포인터 변환  
  
    > [!NOTE]
    >  사용자 정의 형식은 고유한 변환을 지정할 수 없습니다. 사용자 정의 형식 변환에 대해서는 [생성자](../cpp/constructors-cpp.md) 및 [변환](../cpp/user-defined-type-conversions-cpp.md)합니다.  
  
 다음 코드에서는 변환을 발생시킵니다(이 예제의 경우 정수 계열 확장).  
  
```  
long  long_num1, long_num2;  
int   int_num;  
  
// int_num promoted to type long prior to assignment.  
long_num1 = int_num;  
  
// int_num promoted to type long prior to multiplication.  
long_num2 = int_num * long_num2;  
```  
  
 참조 형식을 생성하는 경우에만 변환의 결과가 l-value입니다. 사용자 정의 변환으로 선언 하는 예를 들어 `operator int&()` 대 한 참조를 반환 하며 l-value입니다. 그러나로 선언 된 변환은 `operator int()`개체를 반환 하며 l-value가 아닙니다.  
  
## <a name="integral-promotions"></a>정수 계열 확장  
 정수 계열 형식의 개체를 더 포괄적인 다른 정수 계열 형식(광범위한 값 집합을 나타낼 수 있는 형식)으로 변환할 수 있습니다. 이렇게 변환 형식을 확대하는 것을 "정수 계열 확장"이라고 합니다. 정수 계열 확장을 사용하면 다른 형수 계열 형식을 사용할 때마다 식에 다음을 사용할 수 있습니다.  
  
-   `char` 및 `short int` 형식의 개체, 리터럴 및 상수  
  
-   열거형 형식  
  
-   `int` 비트 필드  
  
-   열거자  
  
 C++ 확장은 "값을 보존"합니다. 즉, 확장 후의 값이 확장 전의 값과 똑같습니다. 값을 보존하는 확장에서 `char`가 원래 형식의 전체 범위를 나타낼 수 있을 경우 짧은 정수 계열 형식의 개체(예: 비트 필드 또는 `int` 형식의 개체)가 `int` 형식으로 확장됩니다. `int`가 값의 전체 범위를 나타낼 수 없으면 개체가 `unsigned int` 형식으로 확장됩니다. 이 전략은 ANSI C에 사용되는 전략과 같지만 값을 보존하는 변환은 개체의 "부호 유무"를 보존하지 않습니다.  
  
 값을 보존하는 확장과 부호 유부를 보존하는 확장은 보통 동일한 결과를 생성합니다. 하지만 확장된 개체가 다음 중 하나일 경우 다른 결과가 생성될 수 있습니다.  
  
-   피연산자 ** / **, `%`, `/=`, `%=`, ** < **, ** \< = **, ** > **, 또는**>=**  
  
     이 연산자는 부호를 사용하여 결과를 확인합니다. 따라서 피연산자에 적용될 경우 값을 보존하는 확장과 부호를 보존하는 확장이 다른 결과를 생성합니다.  
  
-   왼쪽된 피연산자 ** >> ** 또는**>>=**  
  
     이 연산자는 시프트 연산을 수행할 때 부호 있는 수량과 부호 없는 수량을 다르게 처리합니다. 부호 있는 수량의 경우 수량을 오른쪽으로 이동하면 부호 비트가 빈 비트 위치로 전파됩니다. 부호 없는 수량의 경우 빈 비트 위치가 0으로 채워집니다.  
  
-   인수를 일치시키기 위해 해당 피연산자의 형식에 부호가 있는지 여부에 따라 결정되는 오버로드된 연산자의 피연산자 또는 오버로드된 함수의 인수입니다. (참조 [오버 로드 된 연산자](../cpp/operator-overloading.md) 오버 로드 된 연산자를 정의 하는 방법에 대 한 자세한 내용을.)  
  
## <a name="integral-conversions"></a>정수 계열 변환  
 정수 계열 변환은 정수 계열 형식 간에 수행됩니다. 정수 계열 형식은 `char`, `int`, 및 **긴** (및 **짧은**, **서명**, 및 `unsigned` 이러한 형식의 버전).  
  
 **Signed에서 unsigned**  
  
 부호가 있는 정수 계열 형식의 개체를 부호가 없는 해당 형식으로 변환할 수 있습니다. 이러한 변환이 발생할 때 실제 비트 패턴은 변경되지 않습니다. 그러나 데이터의 해석은 변경됩니다. 다음과 같은 코드를 생각해 볼 수 있습니다.  
  
```  
  
#include <iostream>  
  
using namespace std;  
int main()  
{  
    short  i = -3;  
    unsigned short u;  
  
    cout << (u = i) << "\n";  
}  
// Output: 65533  
  
```  
  
 위의 예제에서는 `signed short` `i`가 정의되고 음수로 초기화됩니다. 식 `(u = i)` 하면 `i` 를 변환할 수는 **부호 없는 short** 에 대 한 할당 하기 전에 `u`합니다.  
  
 **Unsigned에서 signed**  
  
 부호 없는 정수 계열 형식의 개체를 부호 있는 해당 형식으로 변환할 수 있습니다. 그러나 다음 예제에서와 같이 부호 없는 개체의 값이 부호 있는 형식으로 표현할 수 있는 범위 밖에 있는 경우 이러한 변환으로 인해 데이터가 잘못 해석될 수 있습니다.  
  
```  
  
#include <iostream>  
  
using namespace std;  
int main()  
{  
 short  i;  
 unsigned short u = 65533;  
  
 cout << (i = u) << "\n";  
}  
//Output: -3  
```  
  
 앞의 예제에서 `u` 는 `unsigned` **짧은** 식을 계산 하 고 서명 된 수량으로 변환 해야 하는 정수 계열 개체 `(i = u)`합니다. 해당 값을 `signed short`로 적절하게 표현할 수 없기 때문에 데이터가 볼 수 있는 바와 같이 잘못 해석됩니다.  
  
## <a name="floating-point-conversions"></a>부동 소수점 변환  
 부동 형식의 개체를 보다 정확한 부동 형식으로 안전하게 변환할 수 있습니다. 즉, 변환으로 인해 중요도가 떨어지지 않습니다. 변환 예를 들어 **float** 를 **double** 또는 **double** 를 `long double` 안전 하며 값은 변경 되지 않습니다.  
  
 부동 형식의 개체를 덜 정확한 형식으로 변환할 수도 있습니다.단, 해당 형식으로 표현할 수 있는 범위에 있어야 합니다. (참조 [부동 제한](../cpp/floating-limits.md) 부동 형식의 범위에 대 한 합니다.) 원래 값을 정확하게 표현할 수 없는 경우 다음으로 높거나 다음으로 낮은 표현 가능한 값으로 변환할 수 있습니다. 그러한 값이 없으면 결과가 정의되지 않습니다. 다음 예제를 참조하세요.  
  
```  
cout << (float)1E300 << endl;  
```  
  
 형식으로 표현할 수 있는 최대 값 **float** 3.402823466E38은-1E300 보다 훨씬 더 작은 수입니다. 따라서 숫자가 무한대로 변환되고 결과는 1.#INF입니다.  
  
## <a name="conversions-between-integral-and-floating-point-types"></a>정수 계열 및 부동 소수점 형식 간의 변환  
 특정 식은 부동 형식의 개체가 정수 계열 형식으로 변환되도록 하거나 그 반대로 변환되도록 할 수 있습니다. 정수 형식의 개체를 부동 형식으로 변환하고 원래 값을 정확하게 나타낼 수 없는 경우, 결과는 다음의 더 높은 표현 가능 값 또는 다음의 더 낮은 표현 가능 값 중 하나입니다.  
  
 부동 형식의 개체를 정수 계열 형식으로 변환하면 소수 부분이 잘립니다. 변환 프로세스에서 반올림은 수행되지 않습니다. 잘림 의미는 숫자 1.3 1 세대 및-1.3 변환할-1로 변환 됩니다.  
  
## <a name="arithmetic-conversions"></a>산술 변환  
 많은 이항 연산자 (에 설명 된 [이항 연산자가 있는 식](../cpp/expressions-with-binary-operators.md)) 인해 피연산자가 변환와 같은 방식으로 결과 생성 합니다. 이러한 연산자가 변환을 일으키는 방식을 "일반적인 산술 변환"이라고 합니다. 다양한 네이티브 형식의 피연산자에 대한 산술 변환은 다음 표에 나와 있는 대로 수행됩니다. typedef 형식은 해당 기본 네이티브 형식에 따라 동작합니다.  
  
### <a name="conditions-for-type-conversion"></a>형식 변환의 조건  
  
|조건 충족|변환|  
|--------------------|----------------|  
|형식의 피연산자가 **long double**합니다.|다른 피연산자는 형식으로 변환 됩니다 **long double**합니다.|  
|이전 조건이 충족 되지 않았고 피연산자 중 하나가 형식 **double**합니다.|다른 피연산자는 형식으로 변환 됩니다 **double**합니다.|  
|이전 조건이 충족 되지 않았고 피연산자 중 하나가 형식 **float**합니다.|다른 피연산자는 형식으로 변환 됩니다 **float**합니다.|  
|이전 조건이 충족되지 않았습니다(부동 형식인 피연산자가 없음).|정수 계열 확장이 다음과 같이 피연산자에 대해 수행됩니다.<br /><br /> -피연산자 중 하나가 형식인 경우 `unsigned` **긴**, 다른 피연산자는 형식으로 변환 됩니다 `unsigned long`합니다.<br />-이전 조건이 충족 되지 않았으며, 있으며 하면 피연산자 중 하나가 형식 **긴** 형식이 고 다른 `unsigned` `int`, 두 피연산자는 형식으로 변환 됩니다 `unsigned long`합니다.<br />-두 이전 조건이 충족 되지 않는, 있는 경우 및 형식의 피연산자 중 하나가 없으면 **긴**, 다른 피연산자는 형식으로 변환 됩니다 **긴**합니다.<br />-세 이전 조건이 충족 되지 않는, 있는 경우 및 형식의 피연산자 중 하나가 없으면 `unsigned int`, 다른 피연산자는 형식으로 변환 됩니다 `unsigned int`합니다.<br />-두 피연산자는 형식으로 변환 됩니다 none 이전 조건이 충족 되 면 `int`합니다.|  
  
 다음 코드에서는 표에 설명된 변환 규칙을 보여 줍니다.  
  
```  
  
double dVal;  
float fVal;  
int iVal;  
unsigned long ulVal;  
  
int main() {  
   // iVal converted to unsigned long  
   // result of multiplication converted to double  
   dVal = iVal * ulVal;  
  
   // ulVal converted to float  
   // result of addition converted to double  
   dVal = ulVal + fVal;  
}  
```  
  
 위의 예제에서 첫 번째 문은 `iVal`과 `ulVal`이라는 두 정수 계열 형식을 곱한 것입니다. 충족된 조건은 두 피연산자 모두 부동 형식이 아니고 한 피연산자가 `unsigned int` 형식이라는 것입니다. 따라서 다른 피연산자인 `iVal`이 `unsigned int` 형식으로 변환됩니다. 결과는 `dVal`에 할당됩니다. 충족 된 조건은 한 피연산자는 형식입니다는 **double**; 따라서는 `unsigned int` 곱하기의 결과 형식으로 변환 됩니다 **double**합니다.  
  
 앞의 예제에서 두 번째 문은 표시 추가 **float** 및 정수 계열 형식으로 `fVal` 및 `ulVal`합니다. `ulVal` 변수 형식으로 변환 됩니다 **float** (테이블의 세 번째 조건). 덧셈의 결과 형식으로 변환 됩니다 **double** (두 번째 테이블의 조건)에 할당 된 `dVal`합니다.  
  
## <a name="pointer-conversions"></a>포인터 변환  
 초기화, 할당, 비교 및 기타 식 실행 중에 포인터가 변환될 수 있습니다.  
  
### <a name="pointer-to-classes"></a>클래스 포인터  
 클래스에 대한 포인터가 기본 클래스에 대한 포인터로 변환될 수 있는 두 가지 경우가 있습니다.  
  
 첫 번째 경우는 지정된 기본 클래스에 액세스할 수 있고 변환이 명확한 경우입니다. (참조 [다중 기본 클래스](../cpp/multiple-base-classes.md) 모호한 기본 클래스 참조에 대 한 자세한 내용은.)  
  
 기본 클래스에 액세스할 수 있는지 여부는 파생에서 사용되는 상속의 종류에 따라 달라집니다. 다음 그림에 나와 있는 상속을 살펴보세요.  
  
 ![상속 그래프 보여 주는 기본 &#45; 클래스의 접근성](../cpp/media/vc38xa1.gif "vc38XA1")  
기본 클래스 접근성을 보여 주는 상속 그래프  
  
 다음 표에서는 그림에 나와 있는 상황에 대한 기본 클래스 접근성을 보여 줍니다.  
  
### <a name="base-class-accessibility"></a>기본 클래스의 접근성  
  
|함수 형식|파생|B*에서 A*로의 변환이<br /><br /> B *에서 A\* 법적?|  
|----------------------|----------------|-------------------------------------------|  
|외부(클래스 범위가 아닌) 함수|전용|아니요|  
||보호됨|아니요|  
||공용|예|  
|B 멤버 함수(B 범위에 있음)|전용|예|  
||보호됨|예|  
||공용|예|  
|C 멤버 함수(C 범위에 있음)|전용|아니요|  
||보호됨|예|  
||공용|예|  
  
 클래스에 대한 포인터가 기본 클래스에 대한 포인터로 변환될 수 있는 두 번째 경우는 명시적 형식 변환을 사용하는 경우입니다. (참조 [명시적 형식 변환이 있는 식](http://msdn.microsoft.com/en-us/060ad6b4-9592-4f3e-8509-a20ac84a85ae) 명시적 형식 변환에 대 한 자세한 내용은.)  
  
 이러한 변환의 결과는 기본 클래스에서 완전히 설명하는 개체의 일부인 "하위 개체"에 대한 포인터입니다.  
  
 다음 코드에서는 두 클래스 `A` 및 `B`를 정의합니다. `B`는 `A`에서 파생됩니다. (상속에 대 한 자세한 내용은 참조 하십시오. [파생 클래스](../cpp/inheritance-cpp.md).) 그런 다음 `bObject` 형식의 개체인 `B`를 정의하고 이 개체를 가리키는 두 포인터(`pA` 및 `pB`)를 정의합니다.  
  
```  
// C2039 expected  
class A  
{  
public:  
    int AComponent;  
    int AMemberFunc();  
};  
  
class B : public A  
{  
public:  
    int BComponent;  
    int BMemberFunc();  
};  
int main()  
{  
   B bObject;  
   A *pA = &bObject;  
   B *pB = &bObject;  
  
   pA->AMemberFunc();   // OK in class A  
   pB->AMemberFunc();   // OK: inherited from class A  
   pA->BMemberFunc();   // Error: not in class A  
}  
```  
  
 `pA` 포인터는 `A *` 형식이고, 이는 "`A` 형식의 개체에 대한 포인터"로 해석될 수 있습니다. 멤버 `bObject` `(`같은 `BComponent` 및 `BMemberFunc`) 입력에 고유한 `B` 를 통해 액세스할 수는 없으므로 및 `pA`합니다. `pA` 포인터는 `A` 클래스에서 정의된 개체의 특성(멤버 함수 및 데이터)에만 액세스할 수 있습니다.  
  
### <a name="pointer-to-function"></a>함수 포인터  
 함수에 대 한 포인터 형식으로 변환할 수 **void \* **경우 형식 **void \* ** 해당 포인터에 충분히 큰지 합니다.  
  
### <a name="pointer-to-void"></a>void 포인터  
 `void` 형식의 포인터는 다른 형식으로 변환할 수 있지만 C와 달리 명시적 형식 캐스팅과만 변환할 수 있습니다. (참조 [명시적 형식 변환이 있는 식](http://msdn.microsoft.com/en-us/060ad6b4-9592-4f3e-8509-a20ac84a85ae) 유형 캐스트에 대 한 자세한 내용은.) 입력 포인터를 `void` 형식에 대한 포인터로 암시적으로 변환할 수 있습니다. 형식의 incomplete 개체에 대한 포인터는 `void` 포인터로 변환되고(암시적으로) 다시 반대로 변환(명시적으로)될 수 있습니다. 이러한 변환 결과는 원래 포인터 값과 같습니다. 개체는 선언되지 않은 경우 완료되지 않은 것으로 간주되지만 크기 또는 기본 클래스를 확인하는 데 사용할 수 있는 정보가 부족합니다.  
  
 하지 않은 모든 개체에 대 한 포인터 **const** 또는 `volatile` 형식의 포인터에 암시적으로 변환할 수 **void \* **합니다.  
  
### <a name="const-and-volatile-pointers"></a>const 및 volatile 포인터  
 C + +에서 표준 변환을 제공 하지 않는 한 **const** 또는 `volatile` 형식이 아닌 형식으로 **const** 또는 `volatile`합니다. 하지만 모든 종류의 변환은 명시적 형식 캐스트를 사용하여 지정할 수 있습니다(안전하지 않은 변환 포함).  
  
> [!NOTE]
>  정적 멤버에 대한 포인터를 제외하고 멤버에 대한 C++ 포인터는 일반 포인터와 다르며 동일한 표준 변환이 적용되지 않습니다. 정적 멤버에 대한 포인터는 일반 포인터이며 일반 포인터와 동일한 변환이 적용됩니다.   
  
### <a name="null-pointer-conversions"></a>null 포인터 변환  
 0으로 계산되는 정수 계열 상수 식 또는 포인터 형식으로 캐스팅되는 이러한 식은 "null 포인터"라는 포인터로 변환됩니다. 이 포인터를 이용하여 유효한 개체 또는 함수의 포인터와 동일하지 않음을 비교할 수 있습니다. 단, 오프셋은 동일하지만 다른 개체를 가리키는 기본 개체에 대한 포인터는 제외됩니다.  
  
 C + + 11에서에서 [nullptr](../cpp/nullptr.md) 형식은 C 스타일 null 포인터를 기본 설정 해야 합니다.  
  
### <a name="pointer-expression-conversions"></a>포인터 식 변환  
 배열 형식의 식을 동일한 형식의 포인터로 변환할 수 있습니다. 변환 결과는 첫 번째 배열 요소의 포인터입니다. 다음 예제에서는 이러한 변환에 대해 설명합니다.  
  
```  
char szPath[_MAX_PATH]; // Array of type char.  
char *pszPath = szPath; // Equals &szPath[0].  
```  
  
 특정 형식을 반환하는 함수를 도출하는 식은 해당 형식을 반환하는 함수의 포인터로 변환됩니다. 단, 다음의 경우는 제외됩니다.  
  
-   해당 식이 주소 연산자에 대 한 피연산자로 사용 됩니다 (**&**).  
  
-   해당 식이 함수 호출 연산자의 피연산자로 사용됩니다.  
  
## <a name="reference-conversions"></a>참조 변환  
 클래스에 대한 참조는 다음과 같은 경우 기본 클래스에 대한 참조로 변환할 수 있습니다.  
  
-   지정 된 기본 클래스는 액세스할 수 있습니다.  
  
-   해당 변환은 명확합니다. (참조 [다중 기본 클래스](../cpp/multiple-base-classes.md) 모호한 기본 클래스 참조에 대 한 자세한 내용은.)  
  
 변환의 결과는 기본 클래스를 나타내는 하위 개체에 대한 포인터입니다.  
  
## <a name="pointer-to-member"></a>멤버 포인터  
 할당, 초기화, 비교 및 기타 식 실행 중에 클래스 멤버에 대한 포인터가 변환될 수 있습니다. 이 단원에서는 다음과 같은 멤버 포인터 변환에 대해 설명합니다.  
  
## <a name="pointer-to-base-class-member"></a>기본 클래스 멤버 포인터  
 기본 클래스의 멤버에 대한 포인터는 다음 조건이 충족될 때 파생되는 클래스의 멤버에 대한 포인터로 변환할 수 있습니다.  
  
-   포인터에서 파생 클래스 및 기본 클래스 포인터로의 역 변환에 액세스할 수 있습니다.  
  
-   파생 클래스가 기본 클래스에서 가상으로 상속하지 않습니다.  
  
 왼쪽 피연산자가 멤버에 대한 포인터인 경우 오른쪽 피연산자가 멤버 포인터 형식이거나 0으로 계산되는 상수 식이어야 합니다. 이 대입은 다음과 같은 경우에만 유효합니다.  
  
-   오른쪽 피연산자가 왼쪽 피연산자와 같은 클래스의 멤버에 대한 포인터입니다.  
  
-   왼쪽 피연산자가 오른쪽 피연산자의 클래스로부터 공개적으로 명확하게 파생 클래스의 멤버에 대한 포인터입니다.  
  
## <a name="integral-constant-conversions"></a>정수 계열 상수 변환  
 0으로 계산되는 정수 계열 상수 식은 "null 포인터"라는 포인터로 변환됩니다. 이 포인터를 이용하여 유효한 개체 또는 함수의 포인터와 동일하지 않음을 비교할 수 있습니다. 단, 오프셋은 동일하지만 다른 개체를 가리키는 기본 개체에 대한 포인터는 제외됩니다.  
  
 다음 코드에서는 `i` 클래스의 `A` 멤버에 대한 포인터 정의에 대해 설명합니다. `pai` 포인터는 0으로 초기화되어 null 포인터가 됩니다.  
  
```  
class A  
{  
public:  
 int i;  
};  
  
int A::*pai = 0;  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [C++ 언어 참조](../cpp/cpp-language-reference.md)
