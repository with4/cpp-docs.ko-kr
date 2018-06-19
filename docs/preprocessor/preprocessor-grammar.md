---
title: 전처리기 문법 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d14a3e00e18a2d3ac69dd472ac4056a379ada224
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843368"
---
# <a name="preprocessor-grammar"></a>전처리기 문법
**#define**  *identifier* *token-string*opt  
  
 *#* **정의***식별자*[**(** *식별자*opt **,** *...*  **,** *식별자*opt **)**] *토큰 문자열*선택  
  
 **defined(**  *identifier* **)**  
  
 **defined**  *identifier*  
  
 `#include` **"***path-spec***"**  
  
 `#include` **\<***path-spec***>**  
  
 **#line**  *digit-sequence*  **"** *filename* **"** opt  
  
 *#* **undef**  *identifier*  
  
 **#error**  *token-string*  
  
 **#pragma**  *token-string*  
  
 *조건부* :  
 *if 부분 elif 부품*opt*else 부분*opt*endif 줄*  
  
 *if-part* :  
 *if-linetext*  
  
 *if-line* :  
 **#if**  *constant-expression*  
  
 **#ifdef**  *identifier*  
  
 **#ifndef**  *identifier*  
  
 *elif-parts* :  
 *elif 줄 텍스트*  
  
 *elif 부품 elif 줄 텍스트*  
  
 *elif-line* :  
 **#elif**  *constant-expression*  
  
 *else-part* :  
 *else-linetext*  
  
 *else-line* :  
 `#else`  
  
 *endif-line* :  
 `#endif`  
  
 *digit-sequence* :  
 *digit*  
  
 *digit-sequence digit*  
  
 *자리* : 중 하나  
 **0 1 2 3 4 5 6 7 8 9**  
  
 *token-string* :  
 토큰 문자열  
  
 *token* :  
 *keyword*  
  
 *identifier*  
  
 *constant*  
  
 *operator*  
  
 `punctuator`  
  
 *filename* :  
 올바른 운영 체제 파일 이름  
  
 *path-spec* :  
 Legal file path  
  
 *텍스트* :  
 임의의 텍스트 시퀀스  
  
> [!NOTE]
>  다음 비 단말에서 확장 되는 [어휘 규칙](../cpp/lexical-conventions.md) 의 섹션은 *c + + 언어 참조*: `constant`, `constant` - *식* , *식별자*, *키워드*, `operator`, 및 `punctuator`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [문법 요약(C/C++)](../preprocessor/grammar-summary-c-cpp.md)