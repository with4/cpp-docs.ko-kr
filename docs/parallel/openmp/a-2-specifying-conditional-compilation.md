---
title: "A.2   Specifying Conditional Compilation | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: de4a21b9-f987-4738-9f13-c4795f6f2dff
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.2   Specifying Conditional Compilation
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 예제는 OpenMP 매크로 사용 하 여 조건부 컴파일 사용 하는 설명 `_OPENMP` \([섹션 2.2](../../parallel/openmp/2-2-conditional-compilation.md) 8 페이지\).  OpenMP 컴파일으로는 `_OPENMP` 됩니다 매크로 정의 합니다.  
  
```  
# ifdef _OPENMP   
    printf_s("Compiled by an OpenMP-compliant implementation.\n");  
# endif  
```  
  
 정의 된 전처리기 연산자 하나 이상의 매크로 단일 지시문에서 테스트할 수 있습니다.  
  
```  
# if defined(_OPENMP) && defined(VERBOSE)  
    printf_s("Compiled by an OpenMP-compliant implementation.\n");  
# endif  
```