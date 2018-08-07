---
title: '단항 더하기 및 부정 연산자: + 및-| Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- +
- '-'
dev_langs:
- C++
helpviewer_keywords:
- unary operators [C++], plus
- '- operator'
- negation operator
- + operator [C++], unary operators
- + operator
ms.assetid: 2c58c4f4-0d92-4ae3-9d0c-1a6157875cc1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 06e7f6bd089866619d82798bb220580e8a11b04b
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460895"
---
# <a name="unary-plus-and-negation-operators--and--"></a>단항 더하기 및 부정 연산자: + 및 -
## <a name="syntax"></a>구문  
  
```  
+ cast-expression  
- cast-expression  
```  
  
## <a name="-operator"></a>+ 연산자  
 단항 더하기 연산자의 결과 (**+**)는 피연산자의 값입니다. 단항 더하기 연산자의 피연산자는 산술 형식이어야 합니다.  
  
 정수 계열 확장은 정수 계열 피연산자를 대상으로 수행됩니다. 결과 형식은 피연산자가 승격될 형식입니다. 따라서, 다음 식은 `+ch`여기서 `ch` 형식입니다 **char**, 형식이 **int**; 값이 수정 되지 않습니다. 참조 [표준 변환](standard-conversions.md) 승격 수행 되는 방법에 대 한 자세한 내용은 합니다.  
  
## <a name="--operator"></a>- 연산자  
 단항 부정 연산자 (**-**)는 피연산자의 부정을 생성 합니다. 단항 부정 연산자의 피연산자는 산술 형식이어야 합니다.  
  
 정수 계열 확장은 정수 계열 피연산자에서 수행되며, 결과 형식은 피연산자가 확장되는 형식입니다. 참조 [표준 변환](standard-conversions.md) 승격 수행 하는 방법에 대 한 자세한 내용은 합니다.  
  
## <a name="microsoft-specific"></a>Microsoft 전용  
 부호 없는 수량의 단항 부정은 2^n에서 피연산자의 값을 빼서 수행됩니다. 여기서 n은 지정된 부호 없는 형식의 개체에 있는 비트 수입니다.
  
## <a name="see-also"></a>참고자료  
 [단항 연산자가 있는 식](../cpp/expressions-with-unary-operators.md)   
 [C++ 기본 제공 연산자, 우선 순위 및 결합성](../cpp/cpp-built-in-operators-precedence-and-associativity.md)