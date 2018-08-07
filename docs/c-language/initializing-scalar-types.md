---
title: 스칼라 형식 초기화 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- initializing scalar types
- register variables
- initialization, scalar types
- initializing variables, scalar types
- scalar types
- static variables, initializing
- automatic storage class, initializing scalar types
- automatic storage class
- types [C], initializing
ms.assetid: 73c516f5-c3ad-4d56-ab3b-f2a82b621104
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fef7356768a594694e0fcf3415c66ef63568a7cf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392363"
---
# <a name="initializing-scalar-types"></a>스칼라 형식 초기화
스칼라 형식을 초기화할 때 *assignment-expression*의 값이 변수에 할당됩니다. 할당에 대한 변환 규칙이 적용됩니다. (변환 규칙에 대한 자세한 내용은 [형식 변환](../c-language/type-conversions-c.md)을 참조하세요.)  
  
## <a name="syntax"></a>구문  
 `declaration`:  
 *declaration-specifiers init-declarator-list* opt **;**  
  
 *declaration-specifiers*:  
 *storage-class-specifier declaration-specifiers* opt  
  
 *type-specifier declaration-specifiers* opt  
  
 *type-qualifier declaration-specifiers* opt  
  
 *init-declarator-list*:  
 *init-declarator*  
  
 *init-declarator-list*  **,**  *init-declarator*  
  
 *init-declarator*:  
 *declarator*  
  
 *declarator*  **=**  *initializer* /* 스칼라 초기화용 \*/  
  
 *initializer*:  
 *assignment-expression*  
  
 다음 규칙에 따라 모든 형식의 변수를 초기화할 수 있습니다.  
  
-   파일 범위 수준에서 선언된 변수를 초기화할 수 있습니다. 외부 수준에서 변수를 명시적으로 초기화하지 않는 경우 해당 변수는 기본적으로 0으로 초기화됩니다.  
  
-   상수 식을 사용하면 **static** *storage-class-specifier*로 선언된 모든 전역 변수를 초기화할 수 있습니다. **static**으로 선언될 변수는 프로그램 실행이 시작될 때 초기화됩니다. 전역 **static** 변수를 명시적으로 초기화하지 않는 경우 해당 변수는 기본적으로 0으로 초기화되고 포인터 형식을 갖는 모든 멤버에 null 포인터가 할당됩니다.  
  
-   **auto** 또는 **register** 저장소 클래스 지정자로 선언된 변수는 해당 변수가 선언된 블록에 실행 제어가 전달될 때마다 초기화됩니다. **auto** 또는 **register** 변수의 선언에서 이니셜라이저를 생략하는 경우 변수의 초기 값이 정의되지 않습니다. 자동 및 레지스터 값의 경우 이니셜라이저는 상수가 되는 것으로 제한되지 않습니다. 따라서 이니셜라이저는 함수가 호출되어도 이전에 정의된 값을 포함하는 모든 식일 수 있습니다.  
  
-   외부 변수 선언 및 모든 **static** 변수에 대한 초기 값은 외부 또는 내부인지에 상관없이 상수 식이어야 합니다. 자세한 내용은 [상수 식](../c-language/c-constant-expressions.md)을 참조하세요. 외부 선언 또는 정적 변수의 주소는 상수이므로 이러한 주소를 사용하면 내부적으로 선언된 **static** 포인터 변수를 초기화할 수 있습니다. 그러나 **auto** 변수의 주소는 블록의 각 실행에 대해 서로 다를 수 있으며 정적 이니셜라이저로 사용될 수 없습니다. 상수 또는 변수 값을 사용하여 **auto** 및 **register** 변수를 초기화할 수 있습니다.  
  
-   식별자 선언에 블록 범위가 있으며 식별자에 외부 링크가 있는 경우 선언이 초기화를 가질 수 없습니다.  
  
## <a name="examples"></a>예제  
 다음 예제에서는 초기화를 보여 줍니다.  
  
```  
int x = 10;   
```  
  
 정수 변수 `x`는 상수 식 `10`으로 초기화됩니다.  
  
```  
register int *px = 0;  
```  
  
 `px` 포인터는 0으로 초기화되어 "null" 포인터를 생성합니다.  
  
```  
const int c = (3 * 1024);  
```  
  
 이 예제에서는 상수 식 `(3 * 1024)`를 사용하여 `c`를 **const** 키워드 때문에 수정될 수 없는 상수 값으로 초기화합니다.  
  
```  
int *b = &x;  
```  
  
 이 문은 다른 변수 `b`의 주소와 함께 `x` 포인터를 초기화합니다.  
  
```  
int *const a = &z;  
```  
  
 `a` 포인터는 `z`라는 변수의 주소와 함께 초기화됩니다. 그러나 이 포인터는 **const**로 지정되므로 `a` 변수는 초기화할 수만 있으며 수정할 수 없습니다. 항상 동일한 위치를 가리킵니다.  
  
```  
int GLOBAL ;  
  
int function( void )  
{  
    int LOCAL ;  
    static int *lp = &LOCAL;   /* Illegal initialization */  
    static int *gp = &GLOBAL;  /* Legal initialization   */  
    register int *rp = &LOCAL; /* Legal initialization   */  
}  
```  
  
 전역 변수 `GLOBAL`은 외부 수준에서 선언되므로 전역 수명을 가집니다. 지역 변수 `LOCAL`은 **auto** 저장소 클래스를 가지며 선언된 함수를 실행하는 동안에만 주소를 가집니다. 따라서 `LOCAL`의 주소와 함께 **static** 포인터 변수 `lp`를 초기화할 수 없습니다. `GLOBAL`의 주소가 항상 동일하므로 **static** 포인터 변수 `gp`는 해당 주소로 초기화될 수 있습니다. 마찬가지로 `*rp`는 지역 변수이며 비상수 이니셜라이저를 가질 수 있으므로 `rp`는 초기화될 수 있습니다. 블록을 입력할 때마다 `LOCAL`에 새 주소가 지정되며 이 주소는 `rp`에 할당됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [초기화](../c-language/initialization.md)