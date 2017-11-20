---
title: "C 정수 상수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: integer constants
ms.assetid: fcf6b83c-2038-49ec-91ca-3d5ca1f83037
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 20025ae47491084436864481357125e741ccc486
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="c-integer-constants"></a>C 정수 상수
"정수 상수"는 정수 계열 값을 나타내는 10진수(기수 10), 8진수(기수 8) 또는 16진수(기수 16)입니다. 정수 상수는 변경할 수 없는 정수 값을 나타낼 때 사용합니다.  
  
## <a name="syntax"></a>구문  
 *integer-constant*:  
 *decimal-constant integer-suffix* opt  
  
 *octal-constant integer-suffix* opt  
  
 *hexadecimal-constant integer-suffix* opt  
  
 *decimal-constant*:  
 *nonzero-digit*  
  
 *decimal-constant digit*  
  
 *octal-constant*:  
 **0**  
  
 *octal-constant octal-digit*  
  
 *hexadecimal-constant*:  
 **0x**  *hexadecimal-digit*  
  
 **0X**  *hexadecimal-digit*  
  
 *hexadecimal-constant hexadecimal-digit*  
  
 *nonzero-digit*: 다음 중 하나  
 **1 2 3 4 5 6 7 8 9**  
  
 *octal-digit*: 다음 중 하나  
 **0 1 2 3 4 5 6 7**  
  
 *hexadecimal-digit*: 다음 중 하나  
 **0 1 2 3 4 5 6 7 8 9**  
  
 **a b c d e f**  
  
 **A B C D E F**  
  
 *integer-suffix*:  
 *unsigned-suffix long-suffix* opt  
  
 *long-suffix unsigned-suffix* opt  
  
 *unsigned-suffix*: 다음 중 하나  
 **u U**  
  
 *long-suffix*: 다음 중 하나  
 **l L**  
  
 *64-bit integer-suffix*:  
 **i64**  
  
 정수 상수는 빼기 기호(**-**)가 앞에 없는 경우 양수입니다. 빼기 기호는 단항 산술 부정 연산자로 해석됩니다. 이 연산자에 대한 자세한 내용은 [단항 산술 연산자](../c-language/unary-arithmetic-operators.md)를 참조하세요.  
  
 정수 상수가 **0x** 또는 **0X**로 시작되는 경우 16진수이고, 숫자 **0**으로 시작되는 경우에는 8진수입니다. 두 경우에 해당하지 않으면 10진수로 간주됩니다.  
  
 다음 코드 줄은 동일합니다.  
  
```  
0x1C   /* = Hexadecimal representation for decimal 28 */  
034    /* = Octal representation for decimal 28 */  
```  
  
 공백 문자는 정수 상수의 숫자를 구분할 수 없습니다. 다음 예제에서는 올바른 10진수, 8진수 및 16진수 상수를 보여 줍니다.  
  
```  
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