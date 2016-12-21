---
title: "PCH용 샘플 메이크파일 | Microsoft Docs"
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
  - "pch"
dev_langs: 
  - "C++"
ms.assetid: daf68983-77dc-45db-8701-aa89ad18910d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# PCH용 샘플 메이크파일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 메이크파일은 프로젝트에 간단히 적응되도록 매크로와 \!IF, \!ELSE, \!ENDIF 제어 흐름 명령 구조를 사용합니다.  
  
```  
# Makefile : Illustrates the effective use of precompiled  
#            headers in a project  
# Usage:     NMAKE option  
# option:    DEBUG=[0|1]  
#            (DEBUG not defined is equivalent to DEBUG=0)  
#  
OBJS = myapp.obj applib.obj  
# List all stable header files in the STABLEHDRS macro.  
STABLEHDRS = stable.h another.h  
# List the final header file to be precompiled here:  
BOUNDRY = stable.h  
# List header files under development here:  
UNSTABLEHDRS = unstable.h  
# List all compiler options common to both debug and final  
# versions of your code here:  
CLFLAGS = /c /W3  
# List all linker options common to both debug and final  
# versions of your code here:  
LINKFLAGS = /NOD /ONERROR:NOEXE  
!IF "$(DEBUG)" == "1"  
CLFLAGS   = /D_DEBUG $(CLFLAGS) /Od /Zi /f  
LINKFLAGS = $(LINKFLAGS) /COD  
LIBS      = slibce  
!ELSE  
CLFLAGS   = $(CLFLAGS) /Oselg /Gs  
LINKFLAGS = $(LINKFLAGS)  
LIBS      = slibce  
!ENDIF  
myapp.exe: $(OBJS)  
    link $(LINKFLAGS) @<<  
$(OBJS), myapp, NUL, $(LIBS), NUL;  
<<  
# Compile myapp  
myapp.obj  : myapp.cpp $(UNSTABLEHDRS)  stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    myapp.cpp  
# Compile applib  
applib.obj : applib.cpp $(UNSTABLEHDRS) stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    applib.cpp  
# Compile headers  
stable.pch : $(STABLEHDRS)  
    $(CPP) $(CLFLAGS) /Yc$(BOUNDRY)    applib.cpp myapp.cpp  
```  
  
 [빌드 프로세스의 PCH 파일](../../build/reference/pch-files-in-the-build-process.md)의 그림 "미리 컴파일된 헤더 파일을 사용하는 메이크파일의 구조"에 표시된 STABLEHDRS, BOUNDRY 및 UNSTABLEHDRS 매크로 외에, 이 메이크파일은 CLFLAGS 매크로와 LINKFLAGS 매크로를 제공합니다.  이러한 매크로는 응용 프로그램 실행 파일의 디버그 버전을 빌드하든 최종 버전을 빌드하든 상관 없이 적용되는 컴파일러 및 링커 옵션을 나열하는 데 사용해야 합니다.  또한 프로젝트에 필요한 라이브러리를 나열하는 LIBS 매크로도 있습니다.  
  
 메이크파일은 \!IF, \!ELSE, \!ENDIF를 사용하여 사용자가 NMAKE 명령줄에서 DEBUG 기호를 정의하는지 여부를 감지하기도 합니다.  
  
```  
NMAKE DEBUG=[1|0]  
```  
  
 이 기능을 사용하면 개발 단계와 프로그램의 최종 버전에 대해\(최종 버전의 경우에는 DEBUG\=0을 사용\) 동일한 메이크파일을 사용할 수 있게 됩니다.  다음의 명령줄이 이에 해당합니다.  
  
```  
NMAKE   
NMAKE DEBUG=0  
```  
  
 메이크파일에 대한 자세한 내용은 [NMAKE 참조](../../build/nmake-reference.md)를 참조하십시오.  또한 [컴파일러 옵션](../../build/reference/compiler-options.md) 및 [링커 옵션](../../build/reference/linker-options.md)도 참조하십시오.  
  
## 참고 항목  
 [프로젝트에 미리 컴파일된 헤더 사용](../../build/reference/using-precompiled-headers-in-a-project.md)