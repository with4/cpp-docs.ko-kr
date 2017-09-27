---
title: "단항 더하기 및 부정 연산자: + 및-| Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- +
- '-'
dev_langs:
- C++
helpviewer_keywords:
- unary operators, plus
- '- operator'
- negation operator
- + operator, unary operators
- + operator
ms.assetid: 2c58c4f4-0d92-4ae3-9d0c-1a6157875cc1
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9c664cd382685693da7ab12ba85891bc2ab0d7e8
ms.contentlocale: ko-kr
ms.lasthandoff: 09/25/2017

---
# <a name="unary-plus-and-negation-operators--and--"></a>단항 더하기 및 부정 연산자: + 및 -
## <a name="syntax"></a>구문  
  
```  
  
+ cast-expression  
```  
  
```  
  
- cast-expression  
```  
  
## <a name="-operator"></a>+ 연산자  
 단항 더하기 연산자의 결과 (**+**)는 피연산자의 값입니다. 단항 더하기 연산자의 피연산자는 산술 형식이어야 합니다.  
  
 정수 계열 확장은 정수 계열 피연산자를 대상으로 수행됩니다. 결과 형식은 피연산자가 승격될 형식입니다. 따라서, `+ch`가 `ch` 형식인 `char` 식은 `int` 형식이 되며 그 값은 변경되지 않습니다. 참조 [표준 변환](standard-conversions.md) 확장 수행 방법에 대 한 자세한 내용은 합니다.  
  
## <a name="--operator"></a>- 연산자  
 단항 부정 연산자 (**-**)는 피연산자의 부정을 생성 합니다. 단항 부정 연산자의 피연산자는 산술 형식이어야 합니다.  
  
 정수 계열 확장은 정수 계열 피연산자에서 수행되며, 결과 형식은 피연산자가 확장되는 형식입니다. 참조 [표준 변환](standard-conversions.md) 확장 수행 방법에 대 한 자세한 내용은 합니다.  
  
## <a name="microsoft-specific"></a>Microsoft 전용  
 부호 없는 수량의 단항 부정은 2^n에서 피연산자의 값을 빼서 수행됩니다. 여기서 n은 지정된 부호 없는 형식의 개체에 있는 비트 수입니다. Microsoft C++는 2의 보수 산술 연산을 활용하는 프로세서에서 실행됩니다. 다른 프로세서에서는 부정에 대한 알고리즘이 다를 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)   
 [C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
