---
title: "컴파일러 및 링커에서의 유니코드 지원 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.UseUnicodeResponseFiles"
  - "VC.Project.VCLibrarianTool.UseUnicodeResponseFiles"
  - "VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles"
  - "VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Unicode, Visual C++"
ms.assetid: acc1d322-56b9-4696-a30e-2af891a4e288
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 및 링커에서의 유니코드 지원
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 Visual C\+\+ 빌드 도구에서의 유니코드 지원에 대해 설명합니다.  
  
 파일 이름  
 이제 컴파일러 지시문\(예: \#include\) 또는 명령줄에 지정된 파일 이름에 유니코드 문자를 사용할 수 있습니다.  
  
 소스 코드 파일  
 이제 식별자, 매크로, 문자열\/문자 리터럴 및 주석에서 유니코드 문자가 지원됩니다.  유니버설 문자 이름도 사용할 수 있습니다.  
  
 다음 인코딩에서 소스 코드 파일에 유니코드를 입력할 수 있습니다.  
  
-   UTF\-16 little endian\(BOM에 관계 없음\)  
  
-   UTF\-16 big endian\(BOM에 관계 없음\)  
  
-   UTF\-8\(BOM 있음\)  
  
 Output  
 컴파일하는 동안 컴파일러에서는 콘솔에 UTF\-16으로 진단 정보를 출력합니다.  콘솔에 표시될 수 있는 문자는 콘솔 창 속성에 따라 달라집니다.  파일로 리디렉션되는 컴파일러 출력은 현재 ANSI 콘솔 코드 페이지입니다.  
  
 링커 지시 파일 및 .DEF 파일  
 지시 파일과 DEF 파일은 바이트 순서 표시가 있는 UTF\-16 또는 ANSI 형식일 수 있습니다.  이전에는 ANSI만 지원되었습니다.  
  
 .asm 및 .cod 덤프  
 .asm 및 .cod 덤프는 MASM과의 호환을 위해 기본적으로 ANSI 형식입니다.  UTF\-8로 출력하려면 \/FAu를 사용합니다.  \/FAs를 지정하면 혼합 소스가 직접 인쇄되어 지저분해 보일 수 있습니다\(예: 소스 코드가 UTF\-8이고 \/FAsu를 지정하지 않은 경우\).  
  
 적절한 도구를 선택하고 기본적으로 활성화되어 있는 **유니코드 지시 파일 사용** 속성을 선택하여 개발 환경에서 유니코드 파일 이름을 사용할 수 있습니다\([방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md) 참조\).  이 기본값은 개발 환경을 수정하여 유니코드를 지원하지 않는 컴파일러를 사용하고자 할 때 변경할 수 있습니다.  
  
## 참고 항목  
 [명령줄 빌드](../../build/building-on-the-command-line.md)