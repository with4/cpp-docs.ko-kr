---
title: "#ifdef 및 #ifndef 지시문 (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#ifndef"
  - "#ifdef"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#ifdef 지시문"
  - "#ifndef 지시문"
  - "ifdef 지시문(#ifdef)"
  - "ifndef 지시문(#ifndef)"
  - "전처리기, 지시문"
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #ifdef 및 #ifndef 지시문 (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\#ifdef** 및 **\#ifndef** 지시문은 **정의된** 식별자와 함께 사용할 경우 `#if` 지시문과 동일한 작업을 수행합니다.  
  
## 구문  
  
```  
#ifdef identifier  
#ifndef identifier  
  
// equivalent to  
#if defined identifier  
#if !defined identifier  
```  
  
## 설명  
 `#if`를 사용할 수 있는 위치에서 **\#ifdef** 및 **\#ifndef** 지시문을 사용할 수 있습니다.  **\#ifdef** 식별자 문은 식별자가 정의된 경우 `#if 1` 문과 동일하며, 식별자가 정의되지 않았거나 `#undef` 지시문으로 정의되지 않은 경우 `#if 0` 문과 동일합니다.  이러한 지시문은 C 또는 C\+\+ 소스 코드에서 선언된 식별자가 아니라 `#define`으로 정의된 식별자가 있는지 여부만 검사합니다.  
  
 이러한 지시문은 이전 버전 언어와의 호환성을 위해서만 제공됩니다.  **정의된\(****식별자\)** 상수 식과 `#if` 지시문을 함께 사용할 것을 권장합니다.  
  
 **\#ifndef** 지시문은 **\#ifdef**에서 확인하는 조건의 반대 조건을 확인합니다.  식별자가 정의되지 않았거나 해당 정의가 `#undef`를 통해 제거된 경우 조건은 true\(0이 아닌 값\)입니다.  그렇지 않으면 조건은 false\(0\)입니다.  
  
 **Microsoft 전용**  
  
 식별자는 \/D 옵션을 사용하여 명령줄에서 전달할 수 있습니다.  \/D로 최대 30개의 매크로를 지정할 수 있습니다.  
  
 정의는 명령줄에서 전달될 수 있으므로 정의가 존재하는지 여부를 확인하는 데 유용합니다.  예를 들면 다음과 같습니다.  
  
```  
// ifdef_ifndef.CPP  
// compile with: /Dtest /c  
#ifndef test  
#define final  
#endif  
```  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [전처리기 지시문](../preprocessor/preprocessor-directives.md)