---
title: "인라인 파일 텍스트 만들기 | Microsoft Docs"
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
helpviewer_keywords: 
  - "인라인 파일, 텍스트 만들기"
  - "NMAKE 프로그램, 인라인 파일"
  - "텍스트, 인라인 파일"
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 인라인 파일 텍스트 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

인라인 파일은 임시 파일 또는 영구 파일입니다.  
  
## 구문  
  
```  
  
      inlinetext  
.  
.  
.  
<<[KEEP | NOKEEP]  
```  
  
## 설명  
 명령 이후 첫 번째 줄에 *inlinetext*를 지정합니다.  각 줄의 시작에 꺾쇠괄호\(\<\<\)로 구문이 끝남을 표시합니다.  구분 괄호 앞에 있는 모든 *inlinetext*는 파일에 포함됩니다.  *inlinetext*에 매크로 확장과 대체는 포함될 수 있지만 지시문과 메이크파일 주석은 포함될 수 없습니다.  공백, 탭 및 줄 바꿈 문자는 문자 그대로 처리됩니다.  
  
 임시 파일은 세션 중에 존재하고 다른 명령으로 다시 사용할 수 있습니다.  NMAKE 세션이 끝난 후 파일을 유지하려면 꺾쇠괄호를 닫은 후 **KEEP**을 지정합니다. 이름이 없는 파일은 생성된 파일 이름으로 디스크에 보존됩니다.  임시 파일에는 **NOKEEP**을 지정하거나 아무것도 지정하지 않습니다.  **KEEP**과 **NOKEEP**은 대\/소문자를 구분하지 않습니다.  
  
## 참고 항목  
 [메이크파일의 인라인 파일](../build/inline-files-in-a-makefile.md)