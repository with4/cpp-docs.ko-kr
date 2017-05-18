---
title: "단항 산술 연산자 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- operators [C], unary
- tilde (~) one's complement operator
- bitwise-complement operator
- arithmetic operators [C++], unary
- + operator, unary operators
- unary operators
- exclamation points
- ~ operator, one's complement operator
- logical negation
- '! operator, unary arithmetic operators'
ms.assetid: 78c91415-d469-499e-9dfe-4435350fd333
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 875fd5c87583f93a647cf51907d897603f923e7e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="unary-arithmetic-operators"></a>단항 산술 연산자
C 단항 더하기, 산술 부정, 보수 및 논리 부정 연산자는 다음 목록에서 설명합니다.  
  
|연산자|설명|  
|--------------|-----------------|  
|**+**|괄호 안의 식 앞에 오는 단항 더하기 연산자는 괄호 안의 연산자를 그룹화합니다. 이러한 연산자는 두 개 이상의 결합형 또는 가환적 이항 연산자와 관련된 식과 함께 사용됩니다. 피연산자는 산술 형식이어야 합니다. 결과는 피연산자의 값입니다. 정수 계열 피연산자는 정수 계열 확장을 거칩니다. 결과 형식은 확장된 피연산자 형식과 동일합니다.|  
|**-**|산술 부정 연산자에서는 피연산자의 부정(2의 보수)을 만듭니다. 피연산자는 정수 계열 또는 부동 소수점 값이어야 합니다. 이 연산자는 일반적인 산술 변환을 수행합니다.|  
|`~`|비트 보수(또는 비트 NOT) 연산자는 피연산자의 비트 보수를 만듭니다. 피연산자는 정수 계열 형식이어야 합니다. 이 연산자는 일반적인 산술 변환을 수행하며 결과는 변환 후 피연산자의 형식입니다.|  
|**!**|논리 부정(논리 NOT) 연산자는 해당 피연산자가 true(0이 아닌 값)이면 값 0을 생성하고, false(0)이면 값 1을 생성합니다. 결과는 `int` 형식입니다. 피연산자는 정수 계열, 부동 소수점 또는 포인터 값이어야 합니다.|  
  
 포인터에 대한 단항 산술 연산은 수행할 수 없습니다.  
  
## <a name="examples"></a>예제  
 다음 예제에서는 단항 산술 연산자를 보여 줍니다.  
  
```  
short x = 987;  
    x = -x;  
```  
  
 위의 예제에서 `x`의 새 값은 987의 음수 또는 –987입니다.  
  
```  
unsigned short y = 0xAAAA;  
    y = ~y;  
```  
  
 이 예제에서 `y`에 할당된 새 값은 부호 없는 값인 0xAAAA의 1의 보수이거나 0x5555입니다.  
  
```  
if( !(x < y) )  
```  
  
 `x`가 `y`보다 크거나 같으면 식의 결과는 1(true)입니다. `x`가 `y`보다 작으면 결과는 0(false)입니다.  
  
## <a name="see-also"></a>참고 항목  
 [단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)
