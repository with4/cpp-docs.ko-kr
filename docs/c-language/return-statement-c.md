---
title: "return 문 (C) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "return 문의 ( ) 괄호"
ms.assetid: 18cd82cf-f899-4b28-83ad-4eff353ddcb4
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# return 문 (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`return` 문은 함수의 실행을 종료하고 호출한 함수로 제어를 반환합니다.  호출 바로 다음 지점의 호출 함수에서 실행을 다시 시작합니다.  `return` 문은 호출하는 함수에 값을 반환할 수도 있습니다.  자세한 내용은 [반환 형식](../c-language/return-type.md)을 참조하십시오.  
  
## 구문  
 점프 문:  
 **반환**  *식*  opt **;**  
  
 식이 있는 경우 식의 값이 호출한 함수로 반환됩니다.  *expression*을 생략하면 함수의 반환 값이 정의되지 않습니다.  식이 있는 경우 식은 함수에서 반환한 형식으로 변환한 이후 평가합니다.  함수가 `void` 반환 형식으로 선언된 경우 식이 포함된 `return` 문은 경고를 발생시키고 식은 평가되지 않습니다.  
  
 함수 정의에 `return` 문이 없는 경우 호출된 함수의 마지막 문이 실행된 후 컨트롤이 자동으로 호출 함수로 반환됩니다.  이 경우 호출된 함수의 반환 값은 정의되지 않습니다.  반환 값이 필요하지 않은 경우 `void` 반환 형식을 지정하여 함수를 선언합니다. 그렇지 않을 경우 반환 형식은 `int`입니다.  
  
 대부분의 프로그래머는 `return` 문의 *expression* 인수를 포함하는 데 괄호를 사용합니다.  하지만 C에는 괄호가 필요하지 않습니다.  
  
 이 예제에서는 `return` 문을 보여 줍니다.  
  
```  
#include <limits.h>  
#include <stdio.h>  
  
void draw( int i, long long ll );  
long long sq( int s );  
  
int main()  
{  
    long long y;  
    int x = INT_MAX;  
  
    y = sq( x );  
    draw( x, y );  
    return x;  
}  
  
long long sq( int s )  
{  
    // Note that parentheses around the return expression   
    // are allowed but not required here.  
    return( s * (long long)s );  
}  
  
void draw( int i, long long ll )  
{  
    printf( "i = %d, ll = %lld\n", i, ll );  
    return;  
}  
  
```  
  
 이 예제에서 `main` 함수는 `sq` 및 `draw`라는 두 개의 함수를 호출합니다.  `sq` 함수는 `main` 함수에 `y` 에 할당된 `x * x` 값을 반환합니다.  이 `sq` 의 반환 표현식을 둘러싼 괄호는 식의 일부분으로 평가되고, 명세서 식으로 요구되지 않습니다.  반환 표현식이 반환 타입으로 변환되기 전에 평가가 되기 때문에, `sq` 기대치 못한 결과를 이끌어낼 수 잇는 가능한 무결성 오버플로우를 예방하기 위한 캐스트와 함께 형식을 반환하는 표현식 형식을한 주목합니다.  이 `draw` 로 선언 된 함수는 `void` 함수입니다.  매개 변수의 값들을 표현하고 빈 반환 명세서는 함수를 종료하고, 값을 반환하지 않습니다.  `draw`의 반환 값을 할당하려고 하면 진단 메시지가 발행됩니다.  이 `main` 함수는 운영체제를 위한 `x` 의 값을 반환합니다.  
  
 대상의 예제는 다음과 같습니다.  
  
  **i \= 2147483647, ll \= 4611686014132420609**   
## 참고 항목  
 [문](../c-language/statements-c.md)