---
title: "인라인 파일 지정 | Microsoft Docs"
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
  - "파일[C++], 인라인"
  - "인라인 파일[C++], NMAKE 지정"
  - "NMAKE 프로그램, 인라인 파일"
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 인라인 파일 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

filename이 표시될 명령에 두 개의 꺾쇠괄호\(\<\<\)를 지정합니다.\<\<*filename*  꺾쇠괄호는 매크로 확장이 될 수 없습니다.  
  
## 구문  
  
```  
<<[filename]  
```  
  
## 설명  
 명령이 실행되면 꺾쇠괄호가 *filename*으로 바뀌거나\(filename이 지정된 경우\) NMAKE에서 생성된 고유한 이름으로 바뀝니다.  *filename*이 지정된 경우 꺾쇠괄호 뒤에 공백이나 탭 없이 와야 합니다.  경로를 사용할 수 있습니다.  확장명이 필요하거나 가정되지 않습니다.  filename을 지정하면 같은 이름의 기존 파일은 덮어쓰고 현재 디렉터리나 지정된 디렉터리에 파일을 만들거나 TMP 디렉터리\(TMP 환경 변수가 정의되지 않은 경우에는 현재 디렉터리\)에 파일을 만듭니다.  이전 filename이 다시 사용되는 경우 NMAKE가 이전 파일을 대신합니다.  
  
## 참고 항목  
 [메이크파일의 인라인 파일](../build/inline-files-in-a-makefile.md)