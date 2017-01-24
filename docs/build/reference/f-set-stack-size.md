---
title: "/F(스택 크기 설정) | Microsoft Docs"
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
  - "/f"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/F 컴파일러 옵션[C++]"
  - "F 컴파일러 옵션[C++]"
  - "-F 컴파일러 옵션[C++]"
  - "스택 크기 설정 컴파일러 옵션"
  - "스택, 크기 설정"
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /F(스택 크기 설정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로그램 스택 크기를 바이트 단위로 설정합니다.  
  
## 구문  
  
```  
/F number  
```  
  
## 인수  
 `number`  
 스택 크기를 바이트 단위로 표시합니다.  
  
## 설명  
 이 옵션을 사용하지 않을 경우에는 기본 스택 크기가 1MB입니다.  `number` 인수에는 10진수나 C언어 표기법을 사용할 수 있습니다.  인수는 1부터 링커에서 허용하는 최대 스택 크기까지 지정할 수 있습니다.  그러면 링커에서는 지정된 값을 가장 가까운 4바이트 단위 값으로 반올림합니다.  **\/F**와 `number` 사이의 공백은 선택 사항입니다.  
  
 프로그램에 스택 오버플로 메시지가 나타나면 스택 크기를 증가시켜야 합니다.  
  
 스택 크기를 다음과 같은 방법으로 설정할 수도 있습니다.  
  
-   **\/STACK** 링커 옵션을 사용합니다.  자세한 내용은 [\/STACK](../../build/reference/stack.md)을 참조하십시오.  
  
-   .exe 파일에 EDITBIN을 사용합니다.  자세한 내용은 [EDITBIN 참조](../../build/reference/editbin-reference.md)을 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)