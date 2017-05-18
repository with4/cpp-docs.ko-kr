---
title: "C 대입 연산자 | Microsoft Docs"
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
- remainder assignment operator (%=)
- '&= operator'
- bitwise-AND assignment operator
- operators [C], assignment
- operators [C], shift
- ^= operator, assignment operators
- += operator
- '>>= operator'
- '|= operator'
- division assignment operator
- subtraction operator
- right shift operators
- subtraction operator, C assignment operators
- = operator, assignment operators
- '*= operator'
- '>> operator'
- '%= operator'
- assignment operators, C
- = operator
- assignment operators
- assignment conversions
- -= operator
- multiplication assignment operator (*=)
- shift operators, right
- /= operator
- operator >>=, C assignment operators
- <<= operator
ms.assetid: 11688dcb-c941-44e7-a636-3fc98e7dac40
caps.latest.revision: 8
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
ms.openlocfilehash: 0e65a64dffc4a9c03f2075bcd9eee87b18ad2e77
ms.contentlocale: ko-kr
ms.lasthandoff: 04/01/2017

---
# <a name="c-assignment-operators"></a>C 할당 연산자
할당 연산자는 오른쪽 피연산자의 값을 왼쪽 피연산자에서 이름을 지정한 저장소 위치에 할당합니다. 따라서 할당 연산의 왼쪽 피연산자는 수정할 수 있는 l-value이어야 합니다. 할당 후 할당 식은 왼쪽 피연산자의 값을 갖지만 l-value는 아닙니다.  
  
 **구문**  
  
 *assignment-expression*:  
 *conditional-expression*  
  
 *unary-expression assignment-operator assignment-expression*  
  
 *assignment-operator*: 다음 중 하나  
 **= \*=** `/=` `%=` `+=` **-= <\<= >>= &=** `^=` `|=`  
  
 C의 할당 연산자는 단일 연산에서 값을 변형 및 할당할 수 있습니다. C에서는 다음과 같은 할당 연산자를 제공합니다.  
  
|연산자|연산 수행|  
|--------------|-------------------------|  
|**=**|단순 할당|  
|**\*=**|곱하기 할당|  
|`/=`|나누기 할당|  
|`%=`|나머지 할당|  
|`+=`|더하기 할당|  
|**-=**|빼기 할당|  
|**<\<=**|왼쪽 시프트 할당|  
|**>>=**|오른쪽 시프트 할당|  
|**&=**|비트 AND 할당|  
|`^=`|비트 제외 OR 할당|  
|`&#124;=`|비트 포함 OR 할당|  
  
 할당에서 오른쪽 값의 형식은 왼쪽 값의 형식으로 변환되고 해당 값은 할당이 발생한 후 왼쪽 피연산자에 저장됩니다. 왼쪽 피연산자는 배열, 함수 또는 상수이어서는 안 됩니다. 두 형식에 의존하는 특정 변환 경로에 대한 자세한 내용은 [형식 변환](../c-language/type-conversions-c.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [할당 연산자](../cpp/assignment-operators.md)
