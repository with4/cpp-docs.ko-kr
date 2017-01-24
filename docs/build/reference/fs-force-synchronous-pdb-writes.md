---
title: "/F(동기 PDB 쓰기 적용) | Microsoft Docs"
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
  - "/FS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "-FS 컴파일러 옵션[C++]"
  - "/FS 컴파일러 옵션[C++]"
ms.assetid: b2caaffe-f6e1-4963-b068-648f06b105e0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /F(동기 PDB 쓰기 적용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) 또는 [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)로 생성되며, MSPDBSRV.EXE를 통해 serialize될 프로그램 데이터베이스\(PDB\) 파일에 강제로 씁니다.  
  
## 구문  
  
```  
/FS  
```  
  
## 설명  
 기본적으로  **\/Zi**  또는  **\/ZI**  를 지정 하면, 컴파일러는 PDB 파일의 형식 정보 및 기호화된 디버깅 정보 쓰기를 잠급니다.  유형 수가 큰 경우, 형식 정보를 생성하도록 컴파일러에 걸리는 시간을 크게 줄일 수 있습니다.  다른 프로세스가 일시적으로 PDB 파일을 잠그는 경우 — 예를 들어, 바이러스 백신 프로그램—, 컴파일러는 쓰기를 실패할 수 있으며 치명적인 오류가 발생할 수 있습니다.  Cl.exe의 여러 복사본이 같은 PDB 파일에 액세스할 경우에 이 문제가 발생할 수 있습니다 —예를 들어, 솔루션이 동일한 중간 디렉터리 또는 출력 디렉토리을 사용한 독립적인 프로젝트를 갖거나, 병렬 빌드가 사용될 경우.   **\/FS**  컴파일러 옵션은 컴파일러가 PDB 파일을 잠그는 것을 막을 수 있으며, MSPDBSRV.EXE를 통해 액세스를 직렬화하여 쓰기를 사용할 수 있습니다.  빌드를 훨씬 더 줄 수 있고 cl.exe의 여러 인스턴스가 동시에 PDB 파일에 액세스할 때 발생할 수 있는 모든 오류를 방지하지 않습니다.  중간 독립 프로젝트와 출력 위치를 분리해서 독립된 프로젝트를 쓰거나, 해당 프로젝트 중 하나가 다른 직렬화된 프로젝트 빌드에 종속되도록 솔루션을 변경 하는 것이 좋습니다.  
  
 [\/MP](../../build/reference/mp-build-with-multiple-processes.md) 옵션은 기본적으로  **\/FS**  을 사용합니다.  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [프로젝트 속성 사용](../../ide/working-with-project-properties.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 선택합니다.  
  
3.  **명령줄** 속성 페이지를 선택합니다.  
  
4.  **추가 옵션** 속성을 `/FS`에 포함하도록 수정한 후 **확인**을 선택합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)