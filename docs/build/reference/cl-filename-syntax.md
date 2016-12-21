---
title: "CL 파일 이름 구문 | Microsoft Docs"
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
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe 컴파일러, 파일 이름 구문"
  - "확장, 컴파일러에 지정"
  - "파일 이름[C++]"
  - "파일 이름[C++], CL 컴파일러"
  - "경로, CL 컴파일러 파일 이름 구문"
  - "구문, 컴파일러 파일 이름"
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# CL 파일 이름 구문
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CL은 FAT, HPFS 또는 NTFS 명명 규칙을 따르는 이름이 지정된 파일을 허용합니다.  파일 이름은 전체 또는 부분 경로를 포함할 수 있습니다.  전체 경로에는 드라이브 이름과 디렉터리 이름 하나 이상이 포함됩니다.  CL은 백슬래시\(\\\) 또는 슬래시\(\/\)로 구분된 파일 이름을 허용합니다.  공백이 있는 파일 이름은 큰따옴표 문자로 묶어야 합니다.  부분 경로에서는 드라이브 이름이 생략됩니다. 이 경우 CL은 드라이브를 현재 드라이브로 가정합니다.  경로를 지정하지 않으면 CL은 파일이 현재 디렉터리에 있다고 가정합니다.  
  
 파일 이름 확장명에 따라 파일 처리 방법이 결정됩니다.  확장명이 .c, .cxx 또는 .cpp인 C 파일 및 C\+\+ 파일은 컴파일됩니다.  .obj 파일, 라이브러리\(.lib\) 및 모듈 정의\(.def\) 파일은 처리되지 않고 링커로 전달됩니다.  
  
## 참고 항목  
 [컴파일러 명령줄 구문](../../build/reference/compiler-command-line-syntax.md)