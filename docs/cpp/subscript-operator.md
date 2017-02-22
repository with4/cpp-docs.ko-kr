---
title: "아래 첨자 연산자: | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "연산자[C++], 아래 첨자"
  - "후위 연산자"
  - "[] 연산자"
  - "아래 첨자 연산자, 구문"
ms.assetid: 69c31494-52da-4dd0-8bbe-6ccbfd50f197
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 아래 첨자 연산자:
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
postfix-expression [ expression ]  
```  
  
## 설명  
 후위 식\(기본 식이 될 수도 있음\) 뒤에 첨자 연산자 **\[ \]**가 오면 배열 인덱싱이 지정됩니다.  
  
 관리되는 배열에 대한 자세한 내용은 [Arrays](../windows/arrays-cpp-component-extensions.md)을 참조하세요.  
  
 일반적으로 *postfix\-expression*으로 표현되는 값은 배열 식별자와 같은 포인터 값이며 *expression*은 열거 형식을 포함한 정수 계열 값입니다.  그러나 구문적 요구 사항은 식 중 하나가 포인터 형식이고 다른 하나는 정수 계열 형식이어야 한다는 것 밖에 없습니다.  따라서 정수 계열 값은 *postfix\-expression* 위치에 있을 수 있으며 포인터 값은 *expression*의 괄호 안 또는 첨자 위치에 있을 수 있습니다.  다음과 같은 코드 조각을 생각해 봅시다.  
  
```  
int nArray[5] = { 0, 1, 2, 3, 4 };  
cout << nArray[2] << endl;            // prints "2"  
cout << 2[nArray] << endl;            // prints "2"  
```  
  
 위의 예제에서 `nArray[2]` 식은 `2[nArray]`와 동일합니다.  이유는 첨자 식 *e1***\[** *e2* **\]**의 결과가 다음과 같이 제공되기 때문입니다.  
  
 **\*\( \(** *e2* **\)** *\+* **\(***e1***\) \)**  
  
 식에서 생성된 주소는 *e1* 주소의 *e2* 바이트가 아닙니다.  대신 *e2* 배열의 다음 개체가 생성되도록 주소의 크기가 조정됩니다.  예:  
  
```  
double aDbl[2];  
```  
  
 `aDb[0]` 및 `aDb[1]`의 주소는 **double** 형식의 개체 크기인 8바이트 떨어져 있습니다.  개체 형식에 따른 이 크기 조정은 C\+\+ 언어에 의해 자동으로 수행되며 포인터 형식 피연산자의 덧셈과 뺄셈에 대해 설명하는 [덧셈 연산자](../cpp/additive-operators-plus-and.md)에 정의되어 있습니다.  
  
 첨자 식에는 다음과 같이 여러 첨자가 있을 수도 있습니다.  
  
 *expression1* **\[***expression2***\] \[***expression3***\]**...  
  
 첨자 식은 왼쪽에서 오른쪽으로 연결합니다.  맨 왼쪽 첨자 식인 *expression1***\[***expression2***\]**가 먼저 계산됩니다.  *expression1* 및 *expression2*를 추가한 결과인 주소는 포인터 식을 형성합니다. 그런 다음 이 포인터 식에 *expression3*이 추가되어 새 포인터 식을 형성하고 마지막 첨자 식이 추가될 때까지 계속됩니다.  최종 포인터 값이 배열 형식을 해결하지 않으면 간접 참조 연산자\(**\***\)는 마지막 첨자 식이 계산된 후 적용됩니다.  
  
 여러 첨자가 포함된 식은 다차원 배열의 요소를 참조합니다.  다차원 배열은 요소가 배열인 배열입니다.  예를 들어 3차원 배열의 첫 번째 요소는 2차원 배열입니다.  다음 예제에서는 간단한 2차원 문자 배열을 선언 및 초기화합니다.  
  
```  
// expre_Subscript_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
#define MAX_ROWS 2  
#define MAX_COLS 2  
  
int main() {  
   char c[ MAX_ROWS ][ MAX_COLS ] = { { 'a', 'b' }, { 'c', 'd' } };  
   for ( int i = 0; i < MAX_ROWS; i++ )  
      for ( int j = 0; j < MAX_COLS; j++ )  
         cout << c[ i ][ j ] << endl;  
}  
```  
  
## 양수 및 음수 아래 첨자  
 배열의 첫 번째 요소는 요소 0입니다.  C\+\+ 배열의 범위는 *배열*\[0\]에서 *배열*\[*크기*  – 1\] 사이입니다.  하지만 C\+\+는 양수 및 음수 첨자를 지원합니다.  음수 첨자는 배열 경계 내에 속해야 하며, 그렇지 않으면 결과를 예측할 수 없습니다.  다음 코드에서는 양수 및 음수 배열 첨자를 보여 줍니다.  
  
```  
#include <iostream>  
using namespace std;  
  
int main() {  
    int intArray[1024];  
    for (int i = 0, j = 0; i < 1024; i++)  
    {  
        intArray[i] = j++;  
    }  
  
    cout << intArray[512] << endl;// 512  
  
    int *midArray = &intArray[512];  // pointer to the middle of the array  
  
    cout << midArray[-256] << endl;   // 256  
  
    cout << intArray[-256] << endl; // unpredictable  
}  
```  
  
 마지막 줄의 음수 첨자는 배열의 원점보다 256바이트 적은 메모리의 주소를 가리키기 때문에 런타임 오류를 발생시킬 수 있습니다.  `midArray` 포인터는 `intArray`의 중간으로 초기화되므로 양수 및 음수 배열 인덱스를 둘 다 사용할 수 있습니다.  배열 첨자 오류는 컴파일 타임 오류를 발생시키지 않지만 예측할 수 없는 결과를 생성합니다.  
  
 첨자 연산자는 가환적입니다.  따라서 *배열*\[*인덱스*\]와 *배열*\[*배열*\]은 첨자 연산자가 오버로드되지 않는 한\([오버로드된 연산자](../cpp/operator-overloading.md) 참조\) 동일한 것으로 보장됩니다.  첫 번째 형태가 가장 일반적인 코딩 방법이지만, 둘 다 작동합니다.  
  
## 참고 항목  
 [후위 식](../cpp/postfix-expressions.md)   
 [C\+\+ 연산자](../misc/cpp-operators.md)   
 [C\+\+ 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [배열](../cpp/arrays-cpp.md)   
 [1차원 배열](../c-language/one-dimensional-arrays.md)   
 [다차원 배열](../c-language/multidimensional-arrays-c.md)