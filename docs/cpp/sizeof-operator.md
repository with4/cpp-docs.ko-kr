---
title: "sizeof 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- sizeof_cpp
dev_langs:
- C++
helpviewer_keywords:
- sizeof operator
ms.assetid: 8bc3b6fb-54a1-4eb7-ada0-05f8c5efc532
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 072dbd8d41a867f7cd31316ef0bc1c20660952ef
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="sizeof-operator"></a>sizeof 연산자
`char` 형식의 크기에 따라 피연산자의 크기를 결과로 생성합니다.  
  
> [!NOTE]
>  에 대 한 내용은 `sizeof ...` 연산자 참조 [Ellipses 및 Variadic 템플릿](../cpp/ellipses-and-variadic-templates.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
sizeof unary-expression  
sizeof  ( type-name )  
```  
  
## <a name="remarks"></a>설명  
 결과 `sizeof` 형식의 연산자는 `size_t`, 포함 파일에 정의 하는 정수 계열 형식을 \<stddef.h > 합니다. 이 연산자를 사용하면 프로그램에서 컴퓨터 종속 데이터 크기를 지정하지 않아도 됩니다.  
  
 `sizeof`의 피연산자는 다음 중 하나가 될 수 있습니다.  
  
-   형식 이름. 형식 이름과 함께 `sizeof`를 사용하려면 이름이 괄호로 묶여 있어야 합니다.  
  
-   식입니다. 식과 함께 사용하는 경우 `sizeof`는 괄호를 포함하거나 포함하지 않고 지정할 수 있습니다. 식은 계산되지 않습니다.  
  
 `sizeof` 연산자가 `char` 형식의 개체에 적용되면 1이 결과로 생성됩니다. `sizeof` 연산자가 배열에 적용되면 배열 식별자가 나타내는 포인터의 크기가 아닌 해당 배열의 전체 바이트 수가 결과로 생성됩니다. 배열 식별자가 나타내는 포인터의 크기를 구하려면 `sizeof`가 사용되는 함수에 매개 변수로 전달합니다. 예:  
  
## <a name="example"></a>예  
  
```  
#include <iostream>  
using namespace std;  
  
size_t getPtrSize( char *ptr )  
{  
   return sizeof( ptr );  
}  
  
int main()  
{  
   char szHello[] = "Hello, world!";  
  
   cout  << "The size of a char is: "  
         << sizeof( char )  
         << "\nThe length of " << szHello << " is: "  
         << sizeof szHello  
         << "\nThe size of the pointer is "  
         << getPtrSize( szHello ) << endl;  
}  
```  
  
## <a name="sample-output"></a>샘플 출력  
  
```  
The size of a char is: 1  
The length of Hello, world! is: 14  
The size of the pointer is 4  
```  
  
 `sizeof` 연산자가 `class`, `struct` 또는 `union` 형식에 적용되면 해당 형식 개체의 바이트 수와 함께 단어 경계에 멤버를 맞추기 위해 추가된 안쪽 여백이 결과로 생성됩니다. 결과는 개별 멤버의 저장소 요구 사항을 추가하여 계산된 크기와 일치하지 않을 수도 있습니다. [/Zp](../build/reference/zp-struct-member-alignment.md) 컴파일러 옵션 및 [팩](../preprocessor/pack.md) pragma 멤버에 대 한 맞춤 경계는 영향을 합니다.  
  
 빈 클래스인 경우라도 `sizeof` 연산자는 0을 결과로 생성하지 않습니다.  
  
 `sizeof` 연산자는 다음의 피연산자와 함께 사용할 수 없습니다.  
  
-   함수 (하지만, 함수의 포인터에는 `sizeof`를 적용할 수 없음)  
  
-   비트 필드  
  
-   정의되지 않은 클래스  
  
-   `void` 형식  
  
-   동적으로 할당된 배열  
  
-   외부 배열  
  
-   불완전한 형식  
  
-   괄호로 묶인 불완전한 형식의 이름  
  
 `sizeof` 연산자가 참조에 적용되는 경우 그 결과는 `sizeof`가 개체 자체에 적용되었을 때와 같습니다.  
  
 크기가 지정되지 않은 배열이 구조체의 마지막 요소인 경우 `sizeof` 연산자는 배열 없는 구조체의 크기를 반환합니다.  
  
 `sizeof` 연산자는 대개 다음과 같은 형태의 식을 통해 배열 내 요소의 개수를 계산하는 데 사용됩니다.  
  
```  
sizeof array / sizeof array[0]  
```  
  
## <a name="see-also"></a>참고 항목  
 [단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)   
 [키워드](../cpp/keywords-cpp.md)