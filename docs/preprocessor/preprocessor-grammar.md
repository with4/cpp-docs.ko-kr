---
title: "전처리기 문법 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- preprocessor
- grammar, preprocessor
- preprocessor, grammar
ms.assetid: 6cd33fad-0b08-4592-9be8-7359c43e24e9
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 797d4bf4274a92ca4f265d01579698c0f9c6a4a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="preprocessor-grammar"></a>전처리기 문법
**#define***식별자* *토큰 문자열*선택    
  
 *#***정의***식별자*[**(** *식별자*opt**,** *...*  **,** *식별자*opt **)**] *토큰 문자열*선택    
  
 **정의 (***식별자* **)**   
  
 **정의 된***식별자*   
  
 `#include`**"***경로 사양***"**  
  
 `#include` **\<**  *경로 사양***>**  
  
 **#line***자리 시퀀스***"** *filename* **"**선택      
  
 *#***undef***식별자*   
  
 **#error***토큰 문자열*   
  
 **#pragma***토큰 문자열*   
  
 *조건부* :  
 *if 부분 elif 부품*opt*else 부분*opt*endif 줄*  
  
 *if 부분* :  
 *if linetext*  
  
 *if 줄* :  
 **#if***상수 식*   
  
 **#ifdef***식별자*   
  
 **#ifndef***식별자*   
  
 *elif 부품* :  
 *elif 줄 텍스트*  
  
 *elif 부품 elif 줄 텍스트*  
  
 *elif 줄* :  
 **#elif***상수 식*   
  
 *else 부분* :  
 *else linetext*  
  
 *다른 줄* :  
 `#else`  
  
 *endif 줄* :  
 `#endif`  
  
 *자리 시퀀스* :  
 *digit*  
  
 *digit-sequence digit*  
  
 *자리* : 중 하나  
 **0 1 2 3 4 5 6 7 8 9**  
  
 *토큰 문자열* :  
 토큰 문자열  
  
 *토큰* :  
 *keyword*  
  
 *identifier*  
  
 *constant*  
  
 *operator*  
  
 `punctuator`  
  
 *filename* :  
 올바른 운영 체제 파일 이름  
  
 *경로-사양* :  
 Legal file path  
  
 *텍스트* :  
 임의의 텍스트 시퀀스  
  
> [!NOTE]
>  다음 비 단말에서 확장 되는 [어휘 규칙](../cpp/lexical-conventions.md) 의 섹션은 *c + + 언어 참조*: `constant`, `constant` - *식* , *식별자*, *키워드*, `operator`, 및 `punctuator`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [문법 요약(C/C++)](../preprocessor/grammar-summary-c-cpp.md)