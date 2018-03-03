---
title: "선언 자 개요 | Microsoft Docs"
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
- declarators, about declarators
ms.assetid: 0f2e2312-80bd-4154-8345-718bd9ed2173
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18a3f12ac87f0165c74aaa487913f679f1a9941e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="overview-of-declarators"></a>선언자 개요
선언자는 개체 또는 함수 이름을 지정하는 선언의 구성 요소입니다. 선언자는 명명된 개체가 개체, 포인터, 참조 또는 배열인지 여부도 지정합니다.  선언자는 기본 형식을 지정하지는 않지만, 포인터, 참조 및 배열과 같은 파생 형식을 지정하는 기본 형식의 형식 정보를 수정합니다.  함수에 적용되는 선언자는 형식 지정자와 함께 작동하여 개체, 포인터 또는 참조가 될 함수의 반환 형식을 완전히 지정합니다. (에 설명 된 지정자 [선언 및 정의](declarations-and-definitions-cpp.md), 형식 및 저장소 클래스와 같은 속성을 전달 합니다. 및이 섹션에 설명 된 한정자 [Microsoft 전용 한정자](../cpp/microsoft-specific-modifiers.md), 선언 자를 수정 합니다.) 다음 그림에서는 `MyFunction`의 전체 선언과 선언의 구성 요소를 보여 줍니다.  
  
 ![한정자, 지정자 및 선언 자](../cpp/media/vc38qy1.gif "vc38QY1")  
지정자, 한정자 및 선언자  
  
 **Microsoft 전용**  
  
 대부분의 Microsoft 확장 키워드를 파생 형식을 형성하기 위한 한정자로 사용할 수 있습니다. 해당 키워드는 지정자나 선언자가 아닙니다. (참조 [Microsoft 전용 한정자](../cpp/microsoft-specific-modifiers.md).)  
  
 **Microsoft 전용 종료**  
  
 선언자는 선택적인 지정자 목록 뒤의 선언 구문에 나타납니다. 이 지정자에 대해서는 설명 [선언 합니다.](declarations-and-definitions-cpp.md) 선언에는 둘 이상의 선언자가 포함될 수 있지만 각 선언자는 이름 하나만 선언합니다.  
  
 다음 샘플 선언에서는 전체 선언을 만들기 위해 지정자와 선언자를 결합하는 방법을 보여 줍니다.  
  
```  
const char *pch, ch;  
```  
  
 앞의 선언 키워드에서에서 **const** 및 `char` 지정자 목록으로 구성 합니다. 두 가지 선언자인 `*pch` 및 `ch`가 나열됩니다.  여러 엔터티를 선언하는 선언은 형식 지정자 다음에 쉼표로 구분된 선언자 목록이 이어지고 세미콜론으로 끝납니다.  
  
 **단순 개체에 대 한 선언 자**  
  
 int 또는 double과 같은 단순 개체의 선언자는 단순히 그러한 개체의 이름이며 괄호를 선택적으로 사용합니다.  
  
 `int i; // declarator is i`  
  
 `int (i); // declarator is (i)`  
  
 **포인터, 참조 및 배열에 대 한 선언 자**  
  
 이름 앞에 포인터 연산자가 삽입된 개체는 포인터 또는 참조가 됩니다.   **\***  연산자는 이름을 포인터로, 선언는  **&**  연산자는 참조로 선언 합니다.  
  
```  
int *i; // declarator is *i  
int **i; // declarator is **i;  
int &i = x; // declaratory is &i  
```  
  
 `const` 또는 `volatile`을 추가하면 이 특수 속성이 포인터에 전달됩니다.  형식 지정자와 반대로 이러한 선언자의 지정자를 사용하면 포인터가 가리키는 개체가 아닌 포인터의 속성이 변경됩니다.  
  
```  
char *const cpc; // const pointer to char   
const char *pcc; // pointer to const char   
const char *const cpcc; // const pointer to const char  
```  
  
 자세한 내용은에서 확인할 수 있습니다 [const 및 volatile 포인터](../cpp/const-and-volatile-pointers.md)합니다.  
  
 클래스 또는 구조체 멤버의 포인터는 적절한 중첩 이름 지정자를 사용하여 선언됩니다.  
  
```  
int X::* pIntMember;   
int ::X::* pIntMember; // the initial :: specifies X is in global scope  
char Outer::Inner::* pIntMember; // pointer to char in a nested class  
```  
  
 이름 뒤에 선택적인 상수 식을 묶는 대괄호는 개체를 배열로 만듭니다.  대괄호를 연속으로 사용하면 배열에 추가 차원이 선언됩니다.  
  
```  
int i[5]; // array with five elements of type int numbered from 0 to 4  
int i[]; // array of unknown size  
char *s[4]; // array of pointers to char  
int i[2][2]; // two dimensional array  
```  
  
 **함수 선언 자**  
  
 인수 목록이 포함된 괄호는 이름 뒤에서 함수를 선언하는 데 사용됩니다.  다음은 `int` 반환 형식의 함수 및 `int` 형식의 세 가지 인수를 선언합니다.  
  
```  
int f(int a, int b, int c);  
```  
  
 함수의 포인터 및 참조는 아래와 같이 함수 이름 앞에 포인터 또는 참조 연산자를 추가하여 선언됩니다.  괄호는 보통 선택적으로 사용되며, 함수의 포인터를 포인터를 반환하는 함수와 구별할 때 필요합니다.  
  
```  
int (*pf)(int); // pointer to function returning int  
int *f(int i); // function returning pointer to int  
int (&pf)(int); // reference to function   
```  
  
 멤버 함수의 포인터는 중첩 이름 지정자로 구별됩니다.  
  
```  
int (X::* pmf)(); // pointer to member function of X returning int  
int* (X::* pmf)(); // pointer to member function returning pointer to int  
```  
  
 참고 항목 [멤버의 포인터에](../cpp/pointers-to-members.md)합니다.  
  
 **함수와 같은 선언에는 개체**  
  
 함수 및 개체는 다음과 같이 동일한 선언으로 선언될 수 있습니다.  
  
```  
int i, *j, f(int k);  // int, pointer to int, function returning int  
```  
  
 이 구문은 일부 상황에서 잘못 인식될 수 있습니다.  다음의  
  
```  
int* i, f(int k);  // pointer to int, function returning int (not int*)  
```  
  
 선언은 `int` 포인터와 `int*`를 반환하는 함수의 선언 같지만, 그렇지 않습니다.  이는 *가 `i`에 대한 선언자의 일부이지만 `f`에 대한 선언자의 일부는 아니기 때문입니다.  
  
 **Typedef로 선언 자 구문 단순화**  
  
 그러나 더 나은 방법은 `typedef` 또는 괄호와 `typedef` 키워드의 조합을 사용하는 것입니다. 다음 함수 포인터의 배열 선언을 살펴보십시오.  
  
```  
//  Function returning type int that takes one   
//   argument of type char *.  
typedef int (*PIFN)( char * );  
//  Declare an array of 7 pointers to functions   
//   returning int and taking one argument of type   
//   char *.  
PIFN pifnDispatchArray[7];  
```  
  
 `typedef` 선언 없이 동일한 선언을 작성할 수 있지만 너무 복잡해서 장점보다 오류 발생 가능성이 더 많습니다.  
  
```  
int ( *pifnDispatchArray[7] )( char * );  
```  
  
 Typedef에 대 한 자세한 내용은 참조 하십시오. [별칭 및 typedef](aliases-and-typedefs-cpp.md)합니다.  
  
 단일 기본 형식의 포인터, 참조, 배열은 다음과 같이 쉼표로 구분된 단일 선언으로 결합할 수 있습니다.  
  
```  
int a, *b, c[5], **d, &e=a;  
```  
  
 **더 복잡 한 선언 자 구문**  
  
-   함수의 포인터 배열, 배열의 포인터 등과 같은 개체를 지정하기 위해 포인터, 참조, 배열 및 함수 선언자를 결합할 수 있습니다.  
  
-   포인터 선언자 구문은 다음 재귀 문법에서 완벽하게 설명됩니다.  
  
-   `declarator`는 다음 중 하나로 정의됩니다.  
  
```  
1. identifier   
2. qualified-name   
3. declarator ( argument-list ) [cv-qualfiers] [exception-spec]  
4. declarator [ [ constant-expression ] ]   
  
5. pointer-operatordeclarator   
6. ( declarator )  
```  
  
-   및 *포인터 연산자* 중 하나입니다.  
  
```  
  
      * [cv-qualifiers]  
& [cv-qualifiers]  
::nested-name-specifier * [cv-qualfiers]  
```  
  
 선언자에 선언자를 포함시킬 수 있기 때문에, 위의 규칙을 사용하여 포인터의 배열이나 함수 포인터의 배열을 반환하는 함수 같은 더욱 복잡한 파생 형식을 생성할 수 있습니다.  생성의 각 단계의 만들려면, 기본 데이터 형식을 표시하는 식별자로 시작하여 이전의 식을 `declarator`로 사용해 위의 구문 규칙을 적용해야 합니다.  구문 규칙을 적용하는 순서는 영어로 식을 만드는 방식의 반대입니다.  적용 하는 경우는 *포인터 연산자* 구문 규칙을 배열 또는 함수 식, 배열 또는 아래 표의 마지막 행에서와 같이 함수에 대 한 포인터를 원하는 경우 괄호를 사용 합니다.  
  
 다음 예제에서는 "int의 10개 포인터 배열의 포인터"의 생성을 보여 줍니다.  
  
|텍스트 식|선언자|구문 규칙 적용|  
|-----------------------|----------------|-------------------------|  
||`i`|1|  
|하나 이상의 포인터|`*i`|5|  
|요소가 10개인 배열|`(*i)[10]`|4|  
|포인터|`*((*i)[10])`|6 다음에 5|  
  
 여러 포인터, 참조, 배열 또는 함수 한정자가 사용될 때 선언자는 매우 복잡해질 수 있습니다.  항목 [더 복잡 한 선언 자 해석](../c-language/interpreting-more-complex-declarators.md) 더 복잡 한 선언 자 구문을 읽는 방법에 설명 합니다.  항목은 c + +, 어디에 있지만 C와 c + +, 모두에 적용할 수는 * MyClass 같은 정규화 된 이름은 포인터를 나타내는 데::\* 클래스의 멤버에 대 한 포인터를 지정 하는 데 사용 될 수 있습니다.