---
title: "/Q 옵션(하위 수준 작업) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/q"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Q 컴파일러 옵션[C++]"
  - "-Q 컴파일러 옵션[C++]"
  - "/Q 컴파일러 옵션[C++]"
ms.assetid: 9fa738b9-630a-4bde-bc87-bdfa30552be4
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# /Q 옵션(하위 수준 작업)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Q** 컴파일러 옵션을 사용하면 다음과 같은 하위 수준의 컴파일러 작업을 수행할 수 있습니다.  
  
-   [\/Qfast\_transcendentals\(빠른 초월수 강제 적용\)](../../build/reference/qfast-transcendentals-force-fast-transcendentals.md): 빠른 초월수를 생성합니다.  
  
-   [\/QIfist\(\_ftol 사용 안 함\)](../../build/reference/qifist-suppress-ftol.md): 부동 소수점 형식에서 정수 형식으로 변환해야 할 때 `_ftol`이 사용되지 않도록 합니다. x86 전용입니다.  
  
-   [\/Qimprecise\_fwaits\(Try 블록 내의 fwait 제거\)](../../build/reference/qimprecise-fwaits-remove-fwaits-inside-try-blocks.md): `try` 블록 내에 있는 `fwait` 명령을 제거합니다.  
  
-   [\/Qpar\(자동 평행화 도우미\)](../../build/reference/qpar-auto-parallelizer.md): [\#pragma loop\(\)](../../preprocessor/loop.md) 지시문으로 표시되는 루프의 자동 병렬화를 사용하도록 설정합니다.  
  
-   [\/Qpar\-report\(자동 병렬화 도우미 보고 수준\)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md): 자동 병렬화에 대한 보고 수준을 사용하도록 설정합니다.  
  
-   [\/Qsafe\_fp\_loads](../../build/reference/qsafe-fp-loads.md): 부동 소수점 레지스터 로드 및 MMX 레지스터와 메모리 사이의 이동에 대 한 최적화를 표시 하지 않습니다.  
  
-   [\/Qvec\-report\(자동 벡터화 도우미 보고 수준\)](../../build/reference/qvec-report-auto-vectorizer-reporting-level.md): 자동 벡터화에 대한 보고 수준을 사용하도록 설정합니다.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)