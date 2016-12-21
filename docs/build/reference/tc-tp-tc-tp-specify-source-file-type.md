---
title: "/Tc, /Tp, /TC, /TP(소스 파일 형식 지정) | Microsoft Docs"
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
  - "VC.Project.VCCLWCECompilerTool.CompileAs"
  - "VC.Project.VCCLCompilerTool.CompileAs"
  - "/Tp"
  - "/tc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Tc 컴파일러 옵션[C++]"
  - "/Tp 컴파일러 옵션[C++]"
  - "소스 파일, 컴파일러에 지정"
  - "Tc 컴파일러 옵션[C++]"
  - "-Tc 컴파일러 옵션[C++]"
  - "Tp 컴파일러 옵션[C++]"
  - "-Tp 컴파일러 옵션[C++]"
ms.assetid: 7d9d0a65-338b-427c-8b48-fff30e2f9d2b
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Tc, /Tp, /TC, /TP(소스 파일 형식 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Tc** 옵션은 .c라는 확장명이 없어도 `filename`이 C 소스 파일이라는 것을 지정합니다.  **\/Tp** 옵션은 .cpp나 .cxx라는 확장명이 없어도 `filename`이 C\+\+ 소스 파일이라는 것을 지정합니다.  옵션과 `filename` 사이의 공백은 넣어도 되고 넣지 않아도 됩니다.  각각의 옵션은 하나의 파일을 지정하며, 추가 파일을 지정하려면 옵션을 반복해야 합니다.  
  
 **\/TC**와 **\/TP**는 **\/Tc**와 **\/Tp**의 전역 버전입니다.  이들은 해당 옵션과 관련된 명령줄의 위치와 상관 없이, 컴파일러가 명령줄의 모든 파일을 C 소스 파일\(**\/TC**\)이나 C\+\+ 소스 파일\(**\/TP**\)로서 처리하도록 지정합니다.  **\/Tc**나 **\/Tp**는 단일 파일에 대해 이들 전역 옵션을 재정의할 수 있습니다.  
  
## 구문  
  
```  
/Tcfilename  
/Tpfilename  
/TC  
/TP  
```  
  
## 인수  
 `filename`  
 C 또는 C\+\+ 소스 파일.  
  
## 설명  
 기본적으로 CL은 .c 확장명을 가진 파일을 C 소스 파일로 간주하고 .cpp나 .cxx 확장명을 가진 파일을 C\+\+ 소스 파일로 간주합니다.  
  
 **TC** 또는 **Tc** 옵션이 지정되었다면 사양을 [\/Zc:wchar\_t\(wchar\_t를 네이티브 형식으로 인식\)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) 옵션은 무시 됩니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **고급** 속성 페이지를 클릭합니다.  
  
4.  **컴파일 옵션** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>를 참조하십시오.  
  
## 예제  
 다음 CL 명령줄은 MAIN.c, TEST.prg 및 COLLATE.prg 모두를 C 소스 파일로 지정합니다.  CL은 PRINT.prg를 인식하지 않습니다.  
  
```  
CL MAIN.C /TcTEST.PRG /TcCOLLATE.PRG PRINT.PRG  
```  
  
 다음 CL 명령줄은 TEST1.c, TEST2.cxx, TEST3.huh 및 TEST4.o이 C\+\+ 파일로 컴파일되고 TEST5.z는 C 파일로 컴파일된다고 지정합니다.  
  
```  
CL TEST1.C TEST2.CXX TEST3.HUH TEST4.O /Tc TEST5.Z /TP  
```  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)