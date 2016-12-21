---
title: "방법: C/C++ 응용 프로그램에 매니페스트 포함 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "메니페스트 포함"
  - "메이크파일, 매니페스트를 포함하기 위해 업데이트"
  - "매니페스트[C++]"
ms.assetid: ec0bac69-2fdc-466c-ab0d-710a22974e5d
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 방법: C/C++ 응용 프로그램에 매니페스트 포함
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\/C\+\+ 응용 프로그램 또는 라이브러리의 매니페스트를 최종 이진 파일 내에 포함시키는 것이 좋습니다. 이렇게 하면 대부분의 시나리오에서 올바른 런타임 동작이 보장됩니다.   [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에서는 기본적으로 소스 파일에서 프로젝트를 빌드할 때 매니페스트를 포함시킵니다. 자세한 내용은 [Visual Studio에서 매니페스트 생성](../build/manifest-generation-in-visual-studio.md)을 참조하십시오.  그러나 nmake를 사용하여 응용 프로그램을 빌드하는 경우 기존의 메이크파일을 변경해야 합니다.  이 단원에서는 최종 이진 파일 안에 매니페스트를 자동으로 포함하도록 기존의 메이크파일을 변경하는 방법을 보여 줍니다.  
  
## 두 가지 방법  
 두 가지 방법으로 매니페스트를 응용 프로그램 또는 라이브러리 내에 포함시킬 수 있습니다.  
  
-   증분 빌드를 수행하지 않는 경우 빌드 후 단계로 다음과 비슷한 명령줄을 사용하여 매니페스트를 직접 포함시킬 수 있습니다.  
  
     **mt.exe –manifest MyApp.exe.manifest \-outputresource:MyApp.exe;1**  
  
     또는  
  
     **mt.exe –manifest MyLibrary.dll.manifest \-outputresource:MyLibrary.dll;2**  
  
     \(EXE의 경우 1, DLL의 경우 2\)  
  
-   증분 빌드를 수행하는 경우 위와 같이 리소스를 직접 편집하면 증분 빌드를 사용할 수 없게 되어 전체 다시 빌드가 수행되므로 다른 방법을 사용해야 합니다.  
  
    -   이진 파일을 링크하여 MyApp.exe.manifest 파일을 생성합니다.  
  
    -   매니페스트를 리소스 파일로 변환합니다.  
  
    -   다시 증분 링크하여 매니페스트 리소스를 이진 파일에 포함시킵니다.  
  
 다음 예제에서는 메이크파일을 변경하여 두 가지 기술을 통합하는 방법을 보여 줍니다.  
  
## 메이크파일\(이전\)  
 먼저 한 파일로 빌드되는 간단한 응용 프로그램인 MyApp.exe의 nmake 스크립트를 살펴 봅니다.  
  
```  
# build MyApp.exe  
!if "$(DEBUG)" == "1"  
CPPFLAGS=$(CPPFLAGS) /MDd  
LFLAGS=$(LFLAGS) /INCREMENTAL  
!else  
CPPFLAGS=$(CPPFLAGS) /MD  
!endif  
  
MyApp.exe : MyApp.obj  
    link $** /out:$@ $(LFLAGS)  
  
MyApp.obj : MyApp.cpp  
  
clean :   
    del MyApp.obj MyApp.exe  
```  
  
 Visual C\+\+로 변경하지 않고 실행할 경우 이 스크립트는 MyApp.exe를 만듭니다.  또한 외부 매니페스트 파일인 MyApp.exe.manifest가 작성되며, 이 매니페스트는 운영 체제가 런타임에 종속 어셈블리를 로드하는 데 사용됩니다.  
  
 MyLibrary.dll의 nmake 스크립트도 매우 비슷합니다.  
  
```  
# build MyLibrary.dll  
!if "$(DEBUG)" == "1"  
CPPFLAGS=$(CPPFLAGS) /MDd  
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL  
  
!else  
CPPFLAGS=$(CPPFLAGS) /MD  
LFLAGS=$(LFLAGS) /DLL  
  
!endif  
  
MyLibrary.dll : MyLibrary.obj  
    link $** /out:$@ $(LFLAGS)  
  
MyLibrary.obj : MyLibrary.cpp  
  
clean :   
    del MyLibrary.obj MyLibrary.dll  
```  
  
## 메이크파일\(이후\)  
 매니페스트를 포함하여 빌드하려면 원래 메이크파일에서 네 가지 사항을 변경해야 합니다.  MyApp.exe 메이크파일의 경우는 다음과 같습니다.  
  
```  
# build MyApp.exe  
!include makefile.inc  
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)  
  
!if "$(DEBUG)" == "1"  
CPPFLAGS=$(CPPFLAGS) /MDd  
LFLAGS=$(LFLAGS) /INCREMENTAL  
!else  
CPPFLAGS=$(CPPFLAGS) /MD  
!endif  
  
MyApp.exe : MyApp.obj  
    link $** /out:$@ $(LFLAGS)  
    $(_VC_MANIFEST_EMBED_EXE)  
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2  
  
MyApp.obj : MyApp.cpp  
  
clean :   
    del MyApp.obj MyApp.exe  
    $(_VC_MANIFEST_CLEAN)  
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3  
  
!include makefile.targ.inc  
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)  
```  
  
 MyLibrary.dll 메이크파일의 경우는 다음과 같습니다.  
  
```  
# build MyLibrary.dll  
!include makefile.inc  
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)  
  
!if "$(DEBUG)" == "1"  
CPPFLAGS=$(CPPFLAGS) /MDd  
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL  
  
!else  
CPPFLAGS=$(CPPFLAGS) /MD  
LFLAGS=$(LFLAGS) /DLL  
  
!endif  
  
MyLibrary.dll : MyLibrary.obj  
    link $** /out:$@ $(LFLAGS)  
    $(_VC_MANIFEST_EMBED_DLL)  
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2.  
  
MyLibrary.obj : MyLibrary.cpp  
  
clean :   
    del MyLibrary.obj MyLibrary.dll  
    $(_VC_MANIFEST_CLEAN)  
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3.  
  
!include makefile.targ.inc  
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)  
```  
  
 이제 실제 작업을 수행하는 makefile.inc와 makefile.targ.inc라는 두 개의 메이크파일이 포함됩니다.  
  
 makefile.inc를 만들고 다음 코드를 복사해 넣습니다.  
  
```  
# makefile.inc -- Include this file into existing makefile at the very top.  
  
# _VC_MANIFEST_INC specifies whether build is incremental (1 - incremental).  
# _VC_MANIFEST_BASENAME specifies name of a temporary resource file.  
  
!if "$(DEBUG)" == "1"  
CPPFLAGS=$(CPPFLAGS) /MDd  
LFLAGS=$(LFLAGS) /INCREMENTAL  
_VC_MANIFEST_INC=1  
_VC_MANIFEST_BASENAME=__VC90.Debug  
  
!else  
CPPFLAGS=$(CPPFLAGS) /MD  
_VC_MANIFEST_INC=0  
_VC_MANIFEST_BASENAME=__VC90  
  
!endif  
  
####################################################  
# Specifying name of temporary resource file used only in incremental builds:  
  
!if "$(_VC_MANIFEST_INC)" == "1"  
_VC_MANIFEST_AUTO_RES=$(_VC_MANIFEST_BASENAME).auto.res  
!else  
_VC_MANIFEST_AUTO_RES=  
!endif  
  
####################################################  
# _VC_MANIFEST_EMBED_EXE - command to embed manifest in EXE:  
  
!if "$(_VC_MANIFEST_INC)" == "1"  
  
#MT_SPECIAL_RETURN=1090650113  
#MT_SPECIAL_SWITCH=-notify_resource_update  
MT_SPECIAL_RETURN=0  
MT_SPECIAL_SWITCH=  
_VC_MANIFEST_EMBED_EXE= \  
if exist $@.manifest mt.exe -manifest $@.manifest -out:$(_VC_MANIFEST_BASENAME).auto.manifest $(MT_SPECIAL_SWITCH) & \  
if "%ERRORLEVEL%" == "$(MT_SPECIAL_RETURN)" \  
rc /r $(_VC_MANIFEST_BASENAME).auto.rc & \  
link $** /out:$@ $(LFLAGS)  
  
!else  
  
_VC_MANIFEST_EMBED_EXE= \  
if exist $@.manifest mt.exe -manifest $@.manifest -outputresource:$@;1  
  
!endif  
  
####################################################  
# _VC_MANIFEST_CLEAN - command to clean resources files generated temporarily:  
  
!if "$(_VC_MANIFEST_INC)" == "1"  
  
_VC_MANIFEST_CLEAN=-del $(_VC_MANIFEST_BASENAME).auto.res \  
    $(_VC_MANIFEST_BASENAME).auto.rc \  
    $(_VC_MANIFEST_BASENAME).auto.manifest  
  
!else  
  
_VC_MANIFEST_CLEAN=  
  
!endif  
  
# End of makefile.inc   
####################################################  
```  
  
 이제 makefile.targ.inc를 만들고 다음 코드를 복사해 넣습니다.  
  
```  
# makefile.targ.inc - include this at the very bottom of the existing makefile  
  
####################################################  
# Commands to generate initial empty manifest file and the RC file  
# that references it, and for generating the .res file:  
  
$(_VC_MANIFEST_BASENAME).auto.res : $(_VC_MANIFEST_BASENAME).auto.rc  
  
$(_VC_MANIFEST_BASENAME).auto.rc : $(_VC_MANIFEST_BASENAME).auto.manifest  
    type <<$@  
#include <winuser.h>  
1RT_MANIFEST"$(_VC_MANIFEST_BASENAME).auto.manifest"  
<< KEEP  
  
$(_VC_MANIFEST_BASENAME).auto.manifest :  
    type <<$@  
<?xml version='1.0' encoding='UTF-8' standalone='yes'?>  
<assembly xmlns='urn:schemas-microsoft-com:asm.v1' manifestVersion='1.0'>  
</assembly>  
<< KEEP  
  
# end of makefile.targ.inc  
```  
  
## 참고 항목  
 [C\/C\+\+ 프로그램의 매니페스트 생성 이해](../build/understanding-manifest-generation-for-c-cpp-programs.md)