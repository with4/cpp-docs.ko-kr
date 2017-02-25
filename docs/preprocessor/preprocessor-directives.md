---
title: "전처리기 지시문 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "지시문, 전처리기"
  - "전처리기, 지시문"
ms.assetid: e0fc4564-b6cf-4a36-bf51-6ccd7abd0a94
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 전처리기 지시문
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`#define` 및 **\#ifdef**와 같은 전처리기 지시문은 여러 실행 환경에서 소스 프로그램을 변경하기 쉽고 컴파일하기 용이하게 만들기 위해 일반적으로 사용됩니다.  소스 파일의 지시문은 특정 작업을 수행하도록 전처리기에 지시합니다.  예를 들어 전처리기는 텍스트에서 토큰을 바꾸거나, 다른 파일의 내용을 소스 파일에 삽입하거나, 텍스트 섹션을 제거하여 파일 일부의 컴파일을 억제할 수 있습니다.  전처리기 코드 줄은 매크로 확장 전에 인식되고 수행됩니다.  따라서 매크로가 전처리기 명령처럼 보이는 항목으로 확장되는 경우 해당 명령은 전처리기에서 인식되지 않습니다.  
  
 전처리기 문은 이스케이프 시퀀스가 지원되지 않는 것을 제외하고 소스 파일 문과 동일한 문자 집합을 사용합니다.  전처리기 문에서 사용되는 문자 집합은 [실행 문자 집합](http://msdn.microsoft.com/ko-kr/a7901c61-524d-47c6-beb6-d9dacc2e72ed)과 동일합니다.  전처리기는 음수 문자 값도 인식합니다.  
  
 전처리기는 다음 지시문을 인식합니다.  
  
|||||  
|-|-|-|-|  
|[\#define](../preprocessor/hash-define-directive-c-cpp.md)|[\#error](../preprocessor/hash-error-directive-c-cpp.md)|[\#import](../preprocessor/hash-import-directive-cpp.md)|[\#undef](../preprocessor/hash-undef-directive-c-cpp.md)|  
|[\#elif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[\#if](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[\#include](../preprocessor/hash-include-directive-c-cpp.md)|[\#using](../preprocessor/hash-using-directive-cpp.md)|  
|[\#else](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|[\#ifdef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[\#line](../preprocessor/hash-line-directive-c-cpp.md)|[\#endif](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)|  
|[\#ifndef](../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md)|[\#pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)|||  
  
 숫자 기호\(**\#**\)는 지시문이 포함된 줄에서 공백이 아닌 첫 번째 문자여야 합니다. 공백 문자는 숫자 기호와 지시문의 첫 문자 사이에 나타날 수 있습니다.  일부 지시문에는 인수 또는 값이 포함됩니다.  지시문 다음에 오는 모든 텍스트\(지시문의 일부인 인수 또는 값 제외\)는 한 줄 주석 구분 기호\(**\/\/**\)가 앞에 붙거나 주석 구분 기호\(**\/\* \*\/**\)로 묶여야 합니다.  전처리기 지시문이 포함된 여러 줄은 줄의 끝 표식 바로 앞에 백슬래시\(**\\**\)를 붙여 계속될 수 있습니다.  
  
 전처리기 지시문은 소스 파일의 어느 곳에나 나타날 수 있지만 소스 파일의 나머지 부분에만 적용됩니다.  
  
## 참고 항목  
 [전처리 연산자](../preprocessor/preprocessor-operators.md)   
 [미리 정의된 매크로](../preprocessor/predefined-macros.md)   
 [C\/C\+\+ 전처리기 참조](../preprocessor/c-cpp-preprocessor-reference.md)