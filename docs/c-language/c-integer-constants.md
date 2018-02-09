---
title: "C 정수 상수 | Microsoft Docs"
ms.custom: 
ms.date: 02/01/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- integer constants
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6c23e90d235e1ad2a8cca577c5cfbf2be55b52b6
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2018
---
# <a name="c-integer-constants"></a>C 정수 상수

"정수 상수"는 정수 계열 값을 나타내는 10진수(기수 10), 8진수(기수 8) 또는 16진수(기수 16)입니다. 정수 상수는 변경할 수 없는 정수 값을 나타낼 때 사용합니다.

## <a name="syntax"></a>구문

*integer-constant*:  
&nbsp;&nbsp;*decimal-constant* *integer-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*octal-constant* *integer-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*hexadecimal-constant* *integer-suffix*<sub>opt</sub>  

*decimal-constant*:  
&nbsp;&nbsp;*nonzero-digit*  
&nbsp;&nbsp;*decimal-constant* *digit*  

*octal-constant*:  
&nbsp;&nbsp;**0**  
&nbsp;&nbsp;*octal-constant* *octal-digit*  

*hexadecimal-constant*:  
&nbsp;&nbsp;**0x**  *hexadecimal-digit*  
&nbsp;&nbsp;**0X**  *hexadecimal-digit*  
&nbsp;&nbsp;*hexadecimal-constant* *hexadecimal-digit*  

*nonzero-digit*: 다음 중 하나  
&nbsp;&nbsp;**1 2 3 4 5 6 7 8 9**  

*octal-digit*: 다음 중 하나  
&nbsp;&nbsp;**0 1 2 3 4 5 6 7**  

*hexadecimal-digit*: 다음 중 하나  
&nbsp;&nbsp;**0 1 2 3 4 5 6 7 8 9**  
&nbsp;&nbsp;**a b c d e f**  
&nbsp;&nbsp;**A B C D E F**  
  
*integer-suffix*:  
&nbsp;&nbsp;*unsigned-suffix* *long-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*long-suffix* *unsigned-suffix*<sub>opt</sub>  
&nbsp;&nbsp;*unsigned-suffix* *64-bit-integer-suffix*<sub>opt</sub>

*unsigned-suffix*: 다음 중 하나  
&nbsp;&nbsp;**u U**  

*long-suffix*: 다음 중 하나  
&nbsp;&nbsp;**l L**  
  
*64-bit-integer-suffix*: &nbsp;&nbsp;**i64 I64** 중 하나  

정수 상수는 빼기 기호(**-**)가 앞에 없는 경우 양수입니다. 빼기 기호는 단항 산술 부정 연산자로 해석됩니다. 이 연산자에 대한 자세한 내용은 [단항 산술 연산자](../c-language/unary-arithmetic-operators.md)를 참조하세요.

정수 상수가 **0x** 또는 **0X**로 시작되는 경우 16진수이고, 숫자 **0**으로 시작되는 경우에는 8진수입니다. 두 경우에 해당하지 않으면 10진수로 간주됩니다.

다음 코드 줄은 동일합니다.

```C
0x1C   /* = Hexadecimal representation for decimal 28 */
034    /* = Octal representation for decimal 28 */
```

공백 문자는 정수 상수의 숫자를 구분할 수 없습니다. 다음 예제에서는 올바른 10진수, 8진수 및 16진수 상수를 보여 줍니다.

```C
/* Decimal Constants */
10
132
32179

/* Octal Constants */
012
0204
076663

/* Hexadecimal Constants */
0xa or 0xA
0x84
0x7dB3 or 0X7DB3
```

## <a name="see-also"></a>참고 항목

[C 상수](../c-language/c-constants.md)  
