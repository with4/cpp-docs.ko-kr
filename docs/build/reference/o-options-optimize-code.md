---
title: "/O 옵션(코드 최적화) | Microsoft Docs"
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
  - "VC.Project.VCCLCompilerTool.Optimization"
  - "/o"
  - "VC.Project.VCCLWCECompilerTool.Optimization"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe 컴파일러, 성능"
  - "성능, cle.exe 컴파일러"
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /O 옵션(코드 최적화)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/O** 옵션은 속도가 가장 빠르고 크기는 가장 작은 코드를 만들 수 있도록 여러 가지 최적화를 제어합니다.  
  
-   [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md)은 크기가 최소가 되도록 코드를 최적화합니다.  
  
-   [\/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md)는 속도가 최대가 되도록 코드를 최적화합니다.  
  
-   [\/Ob](../../build/reference/ob-inline-function-expansion.md)는 인라인 함수 확장을 제어합니다.  
  
-   [\/Od](../../build/reference/od-disable-debug.md)는 최적화 기능을 사용할 수 없게 설정하므로 컴파일 속도가 빨라지고 디버깅이 간단해집니다.  
  
-   [\/Og](../../build/reference/og-global-optimizations.md)는 전역 최적화를 수행할 수 있도록 합니다.  
  
-   [\/Oi](../../build/reference/oi-generate-intrinsic-functions.md)는 적절한 함수 호출에 대해 내장 함수를 생성합니다.  
  
-   [\/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)는 컴파일러가 속도 최적화보다 크기 최적화를 우선적으로 처리하도록 합니다.  
  
-   [\/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)\(기본 설정\)는 컴파일러가 크기 최적화보다 속도 최적화를 우선적으로 처리하도록 합니다.  
  
-   [\/Ox](../../build/reference/ox-full-optimization.md)는 최대 최적화를 선택합니다.  
  
-   [\/Oy](../../build/reference/oy-frame-pointer-omission.md)는 호출 스택에 프레임 포인터를 만들지 않으므로 함수 호출이 빨라집니다.  
  
## 설명  
 여러 **\/O** 옵션을 단일 옵션 문에 결합할 수도 있습니다.  예를 들어, `/Odi`는 `/Od /Oi`와 같습니다.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)