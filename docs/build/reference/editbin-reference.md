---
title: "EDITBIN 참조 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "editbin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "이진 데이터, 편집"
  - "COFF 파일, 편집"
  - "EDITBIN 프로그램"
  - "개체 파일, 수정"
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# EDITBIN 참조
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft COFF Binary File Editor\(EDITBIN.EXE\)는 COFF\(공용 개체 파일 형식\) 이진 파일을 수정합니다.  EDITBIN을 사용하여 개체 파일, 실행 파일 및 DLL\(동적 연결 라이브러리\)을 수정할 수 있습니다.  
  
> [!NOTE]
>  이 도구는 [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] 명령 프롬프트에서만 시작할 수 있습니다.  시스템 명령 프롬프트 또는 파일 탐색기에서는 시작할 수 없습니다.  
  
 [\/GL](../../build/reference/gl-whole-program-optimization.md) 컴파일러 옵션으로 만든 파일에는 EDITBIN을 사용할 수 없습니다.  \/GL 옵션으로 만든 이진 파일을 수정하려면 컴파일과 링크를 다시 해야 합니다.  
  
-   [EDITBIN 명령줄](../../build/reference/editbin-command-line.md)  
  
-   [EDITBIN 옵션](../../build/reference/editbin-options.md)  
  
## 참고 항목  
 [C\/C\+\+ 빌드 도구](../../build/reference/c-cpp-build-tools.md)