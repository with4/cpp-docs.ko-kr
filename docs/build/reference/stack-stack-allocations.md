---
title: "/STACK(스택 할당) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.StackReserveSize"
  - "VC.Project.VCLinkerTool.StackCommitSize"
  - "/stack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STACK 링커 옵션"
  - "-STACK 링커 옵션"
  - "메모리 할당, 스택"
  - "/STACK 링커 옵션"
  - "스택, 크기 설정"
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /STACK(스택 할당)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/STACK:reserve[,commit]  
```  
  
## 설명  
 \/STACK 옵션은 스택 크기를 바이트 단위로 설정합니다.  이 옵션은 .exe 파일을 빌드할 때만 사용합니다.  
  
 `reserve` 값은 가상 메모리에서 전체 스택 할당을 지정합니다.  ARM, x86 및 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 컴퓨터의 경우 기본 스택 크기는 1MB입니다.  
  
 `commit` 인수는 운영 체제에서 해석됩니다.  Windows RT의 경우 이 인수는 한 번에 할당할 실제 메모리 양을 지정합니다.  커밋된 가상 메모리는 페이징 파일에 공간을 예약합니다.   `commit` 값이 크면 응용 프로그램에 더 많은 스택 공간이 필요할 때 시간을 절약할 수 있지만 메모리 요구량과 시작 시간은 늘어날 수 있습니다.  ARM, x86 및 [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] 컴퓨터의 경우 기본 commit 값은 4KB입니다.  
  
 `reserve` 와 `commit` 값을 10진법 또는 C언어 표기법으로 지정합니다.  
  
 스택 크기를 설정하는 다른 방법은 모듈 정의 파일\(.def\)에서 [STACKSIZE](../../build/reference/stacksize.md) 문을 사용하는 것입니다.  이 둘이 모두 지정된 경우에는 **STACKSIZE**가 스택 할당\(\/STACK\) 옵션에 우선하여 적용됩니다.  .exe 파일을 빌드한 후 [EDITBIN](../../build/reference/editbin-reference.md) 도구를 사용하여 스택 크기를 변경할 수 있습니다.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **링커** 폴더를 선택합니다.  
  
3.  **시스템** 속성 페이지를 선택합니다.  
  
4.  다음 속성 중 하나를 수정합니다.  
  
    -   **스택 커밋 크기**  
  
    -   **스택 예약 크기**  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A> 속성을 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)