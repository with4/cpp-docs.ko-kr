---
title: "심각한 오류 C1383 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1383"
ms.assetid: ca224d14-d687-4fd6-80c2-8b82f28924ea
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 심각한 오류 C1383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러 옵션 \/GL은 설치된 공용 언어 런타임 버전과 호환되지 않습니다.  
  
 최신 컴파일러에서 이전 버전의 공용 언어 런타임을 사용하며 **\/clr** 및 **\/GL.**으로 컴파일하는 경우 C1383이 발생합니다.  
  
 해결하려면 **\/clr**과 함께 **\/GL**을 사용하지 않거나, 컴파일러와 함께 제공된 공용 언어 런타임 버전을 설치합니다.  
  
 자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md) 및 [\/GL\(전체 프로그램 최적화\)](../../build/reference/gl-whole-program-optimization.md)를 참조하세요.