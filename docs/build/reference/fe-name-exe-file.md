---
title: "/Fe(EXE 파일 이름 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/fe"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fe 컴파일러 옵션[C++]"
  - "실행 파일, 이름 바꾸기"
  - "Fe 컴파일러 옵션[C++]"
  - "-Fe 컴파일러 옵션[C++]"
  - "파일 이름 바꾸기 컴파일러 옵션[C++]"
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /Fe(EXE 파일 이름 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

컴파일러에서 만든 .exe 파일이나 DLL 파일의 이름과 디렉터리를 지정합니다.  
  
## 구문  
  
```  
/Fepathname  
```  
  
## 설명  
 이 옵션을 지정하지 않으면 컴파일러가 명령줄에 지정된 첫 번째 소스나 개체 파일의 기본 이름과 .exe 또는 .dll 확장명을 사용하여 파일에 기본 이름을 지정합니다.  
  
 링크하지 않고 컴파일하는 [\/c\(링크 없이 컴파일\)](../../build/reference/c-compile-without-linking.md) 옵션을 지정하면 **\/Fe** 옵션이 적용되지 않습니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **링커** 폴더를 클릭합니다.  
  
3.  **일반** 속성 페이지를 클릭합니다.  
  
4.  **출력 파일** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>를 참조하십시오.  
  
## 예제  
 다음 명령줄을 실행하면 현재 디렉터리에 있는 모든 C 소스 파일을 컴파일하고 링크합니다.  그러면 PROCESS.exe라는 실행 파일이 C:\\BIN 디렉터리에 만들어집니다.  
  
```  
CL /FeC:\BIN\PROCESS *.C  
```  
  
## 예제  
 다음 명령줄을 실행하면 첫 번째 소스나 개체 파일과 기본 이름이 동일한 실행 파일이 `C:\BIN` 디렉터리에 만들어집니다.  
  
```  
CL /FeC:\BIN\ *.C  
```  
  
## 참고 항목  
 [출력 파일\(\/F\) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)