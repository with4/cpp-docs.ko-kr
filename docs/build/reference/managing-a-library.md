---
title: "라이브러리 관리 | Microsoft Docs"
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
  - "VC.Project.VCLibrarianTool.IgnoreAllDefaultLibraries"
  - "VC.Project.VCLibrarianTool.AdditionalDependencies"
  - "VC.Project.VCLibrarianTool.RemoveObjects"
  - "VC.Project.VCLibrarianTool.LibraryPaths"
  - "VC.Project.VCLibrarianTool.OutputFile"
  - "VC.Project.VCLibrarianTool.IgnoreDefaultLibraryNames"
  - "VC.Project.VCLibrarianTool.AdditionalLibraryDirectories"
  - "VC.Project.VCLibrarianTool.ListContentsFile"
  - "VC.Project.VCLibrarianTool.ListContents"
  - "VC.Project.VCLibrarianTool.SubSystemVersion"
  - "VC.Project.VCLibrarianTool.IgnoreDefaultLibraryName"
  - "VC.Project.VCLibrarianTool.SubSystem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/CONVERT 라이브러리 관리자 옵션"
  - "/LIBPATH 라이브러리 관리자 옵션"
  - "/LINK50COMPAT 라이브러리 관리자 옵션"
  - "/LIST 라이브러리 관리자 옵션"
  - "/OUT 라이브러리 관리자 옵션"
  - "/REMOVE 라이브러리 관리자 옵션"
  - "/SUBSYSTEM 라이브러리 관리자 옵션"
  - "CONVERT 라이브러리 관리자 옵션"
  - "-CONVERT 라이브러리 관리자 옵션"
  - "LIB[C++], COFF 라이브러리 관리"
  - "LIBPATH 라이브러리 관리자 옵션"
  - "-LIBPATH 라이브러리 관리자 옵션"
  - "LINK50COMPAT 라이브러리 관리자 옵션"
  - "-LINK50COMPAT 라이브러리 관리자 옵션"
  - "LIST 라이브러리 관리자 옵션"
  - "-LIST 라이브러리 관리자 옵션"
  - "개체 파일"
  - "개체 파일, 빌드 및 수정"
  - "OUT 라이브러리 관리자 옵션"
  - "-OUT 라이브러리 관리자 옵션"
  - "REMOVE 라이브러리 관리자 옵션"
  - "-REMOVE 라이브러리 관리자 옵션"
  - "SUBSYSTEM 라이브러리 관리자 옵션"
  - "-SUBSYSTEM 라이브러리 관리자 옵션"
ms.assetid: f56a8b85-fbdc-4c09-8d8e-00f0ffe1da53
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 라이브러리 관리
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LIB의 기본 모드는 COFF 개체의 라이브러리를 빌드하거나 수정하는 것입니다.  \/EXTRACT\(개체를 파일로 복사할 때\) 또는 \/DEF\(가져오기 라이브러리를 빌드할 때\)를 지정하지 않은 경우 LIB는 이 모드에서 실행됩니다.  
  
 여러 개체 및\/또는 라이브러리에서 라이브러리를 빌드하려면 다음 구문을 사용합니다.  
  
```  
LIB [options...] files...  
```  
  
 이 명령은 하나 이상의 입력 파일\(*files*\)에서 라이브러리를 만듭니다.  *files*는 COFF 개체 파일이거나 32비트 OMF 개체 파일 또는 기존 COFF 라이브러리일 수 있습니다.  LIB는 지정된 파일의 모든 개체를 포함하는 하나의 라이브러리를 만듭니다.  입력 파일이 32비트 OMF 개체 파일인 경우 LIB는 라이브러리를 빌드하기 전에 해당 파일을 COFF로 변환합니다.  LIB에서는 16비트 버전의 LIB에서 만들어진 라이브러리의 32비트 OMF 개체를 받아들일 수 없습니다.  이런 경우에는 먼저 16비트 LIB를 사용하여 해당 개체를 추출해야만 추출된 개체 파일을 32비트 LIB에 대한 입력으로 사용할 수 있습니다.  
  
 기본적으로 LIB는 첫 번째 개체 또는 라이브러리 파일의 기본 이름과 .lib 확장명을 사용하여 출력 파일의 이름을 지정합니다.  이 출력 파일은 현재 디렉터리에 놓입니다.  이름이 같은 파일이 이미 있는 경우에는 해당 출력 파일이 기존 파일을 대체합니다.  기존 라이브러리를 보존하려면 \/OUT 옵션을 사용하여 해당 출력 파일의 이름을 지정하면 됩니다.  
  
 다음 옵션은 라이브러리를 빌드 및 수정하는 데 적용됩니다.  
  
 \/LIBPATH:`dir`  
 환경 라이브러리 경로를 재정의합니다.  자세한 내용은 LINK [\/LIBPATH](../../build/reference/libpath-additional-libpath.md) 옵션에 대한 설명 부분을 참조하십시오.  
  
 \/LIST  
 출력 라이브러리에 대한 정보를 표준 출력에 표시합니다.  출력을 파일로 리디렉션할 수 있습니다.  \/LIST를 사용하면 기존 라이브러리를 수정하지 않고 해당 내용을 확인할 수 있습니다.  
  
 \/NAME:*filename*  
 가져오기 라이브러리를 빌드할 때 사용할 DLL의 이름을 지정합니다.  
  
 \/NODEFAULTLIB  
 외부 참조 확인 시 검색한 라이브러리 목록에서 하나 이상의 기본 라이브러리를 제거합니다.  자세한 내용은 [\/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)를 참조하십시오.  
  
 \/OUT:*filename*  
 기본 출력 파일 이름을 재정의합니다.  기본적으로 출력 라이브러리는 현재 디렉터리에 만들어지며, 명령줄에 있는 첫 번째 라이브러리 또는 개체 파일의 기본 이름과 .lib 확장명을 사용합니다.  
  
 \/REMOVE:*object*  
 지정된 개체\(*object*\)를 출력 라이브러리에서 제거합니다.  라이브러리에서는 개체 파일이나 라이브러리의 모든 개체를 결합한 후 \/REMOVE로 지정된 모든 개체를 삭제하여 출력 라이브러리를 만듭니다.  
  
 \/SUBSYSTEM:{CONSOLE &#124; EFI\_APPLICATION &#124; EFI\_BOOT\_SERVICE\_DRIVER &#124; EFI\_ROM &#124; EFI\_RUNTIME\_DRIVER &#124; NATIVE &#124; POSIX &#124; WINDOWS &#124; WINDOWSCE}\[,\#\[.\#\#\]\]  
 출력 라이브러리에 링크하여 만든 프로그램의 실행 방법을 운영 체제에 알립니다.  자세한 내용은 LINK [\/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md) 옵션에 대한 설명 부분을 참조하십시오.  
  
 명령줄에 지정된 LIB 옵션은 대\/소문자가 구분되지 않습니다.  
  
 LIB를 사용하면 다음과 같은 라이브러리 관리 작업을 수행할 수 있습니다.  
  
-   라이브러리에 개체를 추가하려면 기존 라이브러리의 파일 이름 및 새로 추가할 개체의 파일 이름을 지정합니다.  
  
-   여러 개의 라이브러리를 결합하려면 해당 라이브러리 파일 이름을 지정합니다.  하나의 LIB 명령만으로 개체를 추가하고 라이브러리를 결합할 수 있습니다.  
  
-   라이브러리 멤버를 새로운 개체로 바꾸려면 바꿀 멤버 개체가 들어 있는 라이브러리와 새 개체의 파일 이름\(또는 새 개체가 들어 있는 라이브러리\)을 지정합니다.  둘 이상의 입력 파일에 같은 이름을 가진 개체가 이미 있는 경우 LIB는 LIB 명령에 지정된 마지막 개체를 출력 라이브러리에 포함시킵니다.  라이브러리 멤버를 바꿀 때에는 기존 개체가 들어 있는 라이브러리 다음에 새 개체 또는 라이브러리를 지정해야 합니다.  
  
-   라이브러리에서 멤버를 삭제하려면 \/REMOVE 옵션을 사용합니다.  LIB는 명령줄 순서에 상관 없이 모든 입력 개체를 결합한 다음 \/REMOVE 옵션의 사양을 처리합니다.  
  
> [!NOTE]
>  동일한 단계에서 멤버 삭제 및 파일에 멤버 추출을 모두 수행할 수는 없습니다.  먼저 \/EXTRACT를 사용하여 멤버 개체를 추출한 다음 \/REMOVE를 사용하여 LIB를 다시 실행해야 합니다.  이 동작은 다른 Microsoft 제품에서 제공되는 16비트 LIB\(OMF 라이브러리용\)의 동작과 다릅니다.  
  
## 참고 항목  
 [LIB 참조](../../build/reference/lib-reference.md)