---
title: "/FA, /Fa(목록 파일) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.AssemblerListingLocation"
  - "VC.Project.VCCLCompilerTool.ConfigureASMListing"
  - "VC.Project.VCCLWCECompilerTool.AssemblerOutput"
  - "VC.Project.VCCLCompilerTool.AssemblerListingLocation"
  - "/fa"
  - "VC.Project.VCCLCompilerTool.AssemblerOutput"
  - "VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FA 컴파일러 옵션[C++]"
  - "어셈블리만 사용하는 목록"
  - "FA 컴파일러 옵션[C++]"
  - "-FA 컴파일러 옵션[C++]"
  - "파일 형식 목록 표시"
ms.assetid: c7507d0e-c69d-44f9-b8e2-d2c398697402
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /FA, /Fa(목록 파일)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

어셈블리 코드가 포함된 목록 파일을 만듭니다.  
  
## 구문  
  
```  
/FA[c|s|u]  
/Fapathname  
```  
  
## 설명  
 인수는 소스 코드와 기계어 코드 생성 및 목록 파일의 확장명을 제어합니다.  
  
 다음 표에서는 **\/FA**의 다양한 값에 대해 설명합니다.  **\/FA**의 값을 두 개 이상 지정할 수 있습니다.  예를 들어, **\/FAsu**를 지정할 수 있습니다.  
  
|옵션|목록 내용 및  파일 확장명|  
|--------|---------------------|  
|**\/FA**|어셈블리 코드; .asm|  
|**\/FAc**|기계어 및 어셈블리 코드; .cod|  
|**\/FAs**|소스 및 어셈블리 코드; .asm<br /><br /> **\/FAcs**를 지정한 경우 파일 확장명은 .cod입니다.|  
|**\/FAu**|바이트 순서 마커를 사용하여 UTF\-8 형식으로 출력 파일이 작성되도록 합니다.  파일의 기본 인코딩은 ANSI이지만 목록 파일을 시스템에 상관없이 올바르게 표시하려는 경우 또는 컴파일러에 대한 입력으로 유니코드 소스 코드 파일을 사용하려는 경우에는 **\/FAu**를 사용합니다.<br /><br /> **\/FAsu**를 지정하고 소스 코드 파일에서 UTF\-8 이외의 유니코드 인코딩을 사용하는 경우 .asm 파일의 코드 줄이 올바르게 표시되지 않을 수 있습니다.|  
  
 기본적으로 목록 파일은 소스 파일과 동일한 기본 이름을 사용합니다.  **\/Fa** 옵션을 사용하여 목록 파일과 목록 파일이 만들어지는 디렉터리의 이름을 변경할 수 있습니다.  
  
|\/Fa 사용법|결과|  
|--------------|--------|  
|**\/Fa**|컴파일할 때 소스 코드 파일마다 *source\_file*.asm이 하나씩 만들어집니다.|  
|**\/Fa** *filename*|*filename*.asm은 현재 디렉터리에 저장됩니다.  소스 코드 파일 하나를 컴파일할 때만 이 옵션을 사용할 수 있습니다.|  
|**\/Fa** *filename.extension*|*filename.extension*.asm은 현재 디렉터리에 저장됩니다.  소스 코드 파일 하나를 컴파일할 때만 이 옵션을 사용할 수 있습니다.|  
|**\/Fa** *directory*\\|컴파일할 때 소스 코드 파일마다 *source\_file*.asm이 하나씩 만들어지고 지정된 *directory*에 저장됩니다.  이 옵션 뒤에는 백슬래시가 있어야 합니다.  현재 디스크에 있는 경로만 지정할 수 있습니다.|  
|**\/Fa** *directory*\\*filename*|*filename*.asm이 지정된 `directory`에 저장됩니다.  소스 코드 파일 하나를 컴파일할 때만 이 옵션을 사용할 수 있습니다.|  
|**\/Fa** *directory*\\*filename.extension*|`directory` 구문은 \(*filename.extension*\)에 지정되어 있습니다.  소스 코드 파일 하나를 컴파일할 때만 이 옵션을 사용할 수 있습니다.|  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **출력 파일** 속성 페이지를 클릭합니다.  
  
4.  **ASM 목록 위치**\(**\/Fa**\) 또는 **어셈블러 출력**\(**\/FA**\) 속성을 수정합니다. **\/FAu**는 **추가 옵션** 상자의 **명령줄** 속성 페이지에서 지정해야 합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerListingLocation%2A> 또는 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerOutput%2A>을 참조하십시오.  **\/FAu**를 지정하는 방법은 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 예제  
 다음 명령줄을 실행하면 소스와 기계어 코드가 결합된 HELLO.cod 목록이 만들어집니다.  
  
```  
CL /FAcs HELLO.CPP  
```  
  
## 참고 항목  
 [출력 파일\(\/F\) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)