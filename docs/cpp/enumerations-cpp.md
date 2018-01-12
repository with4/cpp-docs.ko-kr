---
title: "열거형 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: enum_cpp
dev_langs: C++
helpviewer_keywords:
- declarations, enumerations
- enumerators, declaring
- enum keyword [C++]
- named constants, enumeration declarations
- declaring enumerations
ms.assetid: 081829db-5dca-411e-a53c-bffef315bcb3
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 96b1b29baaa779fda1e1f076daf3d8bd9335403b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="enumerations-c"></a>열거형(C++)
열거형은 열거자라는 명명된 정수 상수 집합으로 구성된 사용자 정의 형식입니다.  
  
> [!NOTE]
>  이 문서에서는 ISO 표준 C++ 언어 `enum` 형식과 C++11에 도입된 범위가 지정된(또는 강력한 형식의) `enum class` 형식을 다룹니다. 에 대 한 내용은 `public enum class` 또는 `private enum class` 형식에서 C + + /CLI 및 C + + /CX에서는 참조 [enum 클래스](../windows/enum-class-cpp-component-extensions.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
// unscoped enum:  
enum [identifier] [: type]  
{enum-list};   
  
// scoped enum:  
enum [class|struct]   
[identifier] [: type]   
{enum-list};  
```  
  
```  
// Forward declaration of enumerations  (C++11):  
enum A : int; // non-scoped enum must have type specified
enum class B; // scoped enum defaults to int but ...
enum class C : short;  // ... may have any integral underlying type
```  
  
## <a name="parameters"></a>매개 변수  
 `identifier`  
 열거형에 지정된 형식 이름입니다.  
  
 `type`  
 열거자의 기본 형식이며, 모든 열거자는 동일한 기본 형식을 갖습니다. 모든 정수 계열 형식이 가능합니다.  
  
 `enum-list`  
 열거형에서 열거자의 쉼표로 구분된 목록입니다. 범위에 있는 모든 열거자 또는 변수 이름은 고유해야 합니다. 하지만 값이 중복될 수 있습니다. 범위가 정해지지 않은 열거형에서 범위는 주변 범위이며 범위가 지정된 열거형에서 범위는 `enum-list` 자체입니다.  범위가 지정 된 열거형에 적용 된 새 정수 계열 형식을 정의 하는 목록 비어 있을 수 있습니다.
  
 `class`  
 이 키워드를 선언에 사용하여, 열거형의 범위가 지정되고 `identifier`가 제공되도록 지정합니다. `struct` 키워드를 `class` 대신 사용할 수도 있습니다. 이 컨텍스트에서는 이러한 키워드의 의미 체계가 같기 때문입니다.  
  
## <a name="enumerator-scope"></a>열거자 범위  
 열거형은 명명된 상수로 표현되고 열거자라고도 하는 값의 범위를 설명하기 위한 컨텍스트를 제공합니다. 원래 C 및 C++ 열거형 형식에서는 정규화되지 않은 열거자가 열거형이 선언되는 범위 전체에 표시됩니다. 범위가 지정된 열거형에서는 열거자 이름을 열거형 형식 이름으로 한정해야 합니다. 다음 예제에서는 두 가지 열거형의 이러한 기본적인 차이점을 보여 줍니다.  
  
```cpp  
namespace CardGame_Scoped  
{  
    enum class Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void PlayCard(Suit suit)  
    {  
        if (suit == Suit::Clubs) // Enumerator must be qualified by enum type  
        { /*...*/}  
    }  
}  
  
namespace CardGame_NonScoped  
{  
    enum Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void PlayCard(Suit suit)  
    {  
        if (suit == Clubs) // Enumerator is visible without qualification  
        { /*...*/  
        }  
    }  
}  
```  
  
 열거형의 각 이름은 열거형 값의 순서대로 해당 위치에 해당하는 정수 값이 할당됩니다. 기본적으로 첫 번째 값은 0이 할당되고 다음 값은 1이 할당되는 식이지만 여기에 나와 있는 대로 열거자의 값을 명시적으로 설정할 수 있습니다.  
  
```cpp  
enum Suit { Diamonds = 1, Hearts, Clubs, Spades };  
  
```  
  
 `Diamonds` 열거자에 값 `1`이 할당됩니다. 명시적인 값이 지정되지 않은 경우 다음 열거자는 이전 열거자에 1을 더한 값을 받습니다. 앞의 예제에서 `Hearts`의 값은 2, `Clubs`의 값은 3 등이 될 수 있습니다.  
  
 모든 열거자는 상수로 처리되며 `enum`이 정의되는 범위 내에(범위가 지정되지 않은 열거형의 경우) 또는 열거형 자체에(범위가 지정된 열거형의 경우) 고유한 이름이 있어야 합니다. 이름에 지정되는 값은 고유하지 않아도 됩니다. 예를 들어, 범위가 지정되지 않은 열거형 `Suit`의 선언이 다음과 같은 경우  
  
```cpp  
enum Suit { Diamonds = 5, Hearts, Clubs = 4, Spades };  
```  
  
 `Diamonds`, `Hearts`, `Clubs` 및 `Spades`의 값은 각각 5, 6, 4 및 5입니다. 5가 한 번 이상 사용되며 이는 의도한 것이 아니더라도 허용됩니다. 이러한 규칙은 범위가 지정된 열거형의 경우와 동일합니다.  
  
 ## <a name="casting-rules"></a>캐스팅 규칙  
  
 범위가 지정되지 않은 열거형 상수를 `int`로 암시적으로 변환할 수 있지만, `int`는 열거형 값으로 암시적으로 변환할 수 없습니다. 다음 예제에서는 `hand`에 `Suit`가 아닌 값을 할당하면 어떻게 되는지를 보여 줍니다.  
  
```cpp  
int account_num = 135692;  
Suit hand;  
hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'  
  
```  
  
 `int`를 범위가 지정된 열거자 또는 범위가 지정되지 않은 열거자로 변환하려면 캐스팅해야 합니다. 캐스팅하지 않고 범위가 지정된 열거자를 정수 값으로 승격할 수 있습니다.  
  
```cpp  
int account_num = Hearts; //OK if Hearts is in a unscoped enum  
```  
  
 이러한 방식으로 암시적 변환을 사용할 경우 의도하지 않은 문제가 발생할 수 있습니다. 범위가 지정되지 않은 열거형과 관련된 프로그래밍 오류를 제거하기 위해 범위가 지정된 열거형 값은 강력한 형식입니다. 다음 예제에 표시된 것처럼 범위가 지정된 열거자는 열거형 형식 이름(식별자)으로 한정되어야 하며 암시적으로 변환할 수 없습니다.  
  
```cpp  
namespace ScopedEnumConversions  
{  
    enum class Suit { Diamonds, Hearts, Clubs, Spades };  
  
    void AttemptConversions()  
    {  
        Suit hand;   
        hand = Clubs; // error C2065: 'Clubs' : undeclared identifier  
        hand = Suit::Clubs; //Correct.  
        int account_num = 135692;  
        hand = account_num; // error C2440: '=' : cannot convert from 'int' to 'Suit'  
        hand = static_cast<Suit>(account_num); // OK, but probably a bug!!!  
  
        account_num = Suit::Hearts; // error C2440: '=' : cannot convert from 'Suit' to 'int'  
        account_num = static_cast<int>(Suit::Hearts); // OK  
}  
  
```  
  
 선 `hand = account_num;`은 앞에서 보았듯이 범위가 지정되지 않은 열거형에 발생하는 오류를 초래합니다. 명시적 캐스트로 허용됩니다. 그러나 범위가 지정된 열거형을 사용하여 다음 문 `account_num = Suit::Hearts;`에서 시도된 변환은 명시적 캐스트 없이는 더 이상 허용되지 않습니다. 

## <a name="enums-with-no-enumerators"></a>없는 열거자 열거형
**Visual Studio 2017 버전 15.3 이상** (사용할 수 있는 [/std:c + + 17](../build/reference/std-specify-language-standard-version.md)): 명시적 기본 형식이 없는 열거자와는 enum (일반 또는 범위가 지정 된)를 정의 하 여 적용을 둘 수 있습니다는 새 하는 정수 계열 형식 다른 형식으로 암시적 변환이 있습니다. 기본 제공 기본 형식 대신이 형식을 사용 하 여 의도 하지 않은 암시적 변환으로 발생 하는 미묘한 오류에 대 한 가능성을 제거할 수 있습니다.  


```cpp
enum class byte : unsigned char { };
```

새 type 기본 형식으로의 정확한 복사본을 때문에 같은 호출 규칙 즉, 모든 성능 저하 없이 ABIs 간에 사용할 수 있습니다. 형식의 변수를 직접 목록 초기화를 사용 하 여 초기화 됩니다 캐스트는 필요 합니다. 다음 예제에서는 열거형을 다양 한 컨텍스트에서 없는 열거자로 초기화 하는 방법을 보여 줍니다.

```cpp
enum class byte : unsigned char { };

enum class E : int { };
E e1{ 0 };
E e2 = E{ 0 };

struct X 
{
    E e{ 0 };
    X() : e{ 0 } { }
};

E* p = new E{ 0 }; 

void f(E e) {};

int main()
{
    f(E{ 0 });
    byte i{ 42 };
    byte j = byte{ 42 };

    // unsigned char c = j; // C2440: 'initializing': cannot convert from 'byte' to 'unsigned char'
    return 0;
}
``` 
  
## <a name="see-also"></a>참고 항목  
 [C 열거형 선언](../c-language/c-enumeration-declarations.md)   
 [키워드](../cpp/keywords-cpp.md)