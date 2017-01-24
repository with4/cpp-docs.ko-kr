---
title: "/Yd(개체 파일에 디버그 정보 삽입) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/yd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Yd 컴파일러 옵션[C++]"
  - "디버깅[C++], 디버그 정보 파일"
  - "Yd 컴파일러 옵션[C++]"
  - "-Yd 컴파일러 옵션[C++]"
ms.assetid: c5a699fe-65ce-461e-964c-7f5eb2a8320a
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Yd(개체 파일에 디버그 정보 삽입)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 옵션을 [\/Yc](../../build/reference/yc-create-precompiled-header-file.md) 및 [\/Z7](../../build/reference/z7-zi-zi-debug-information-format.md) 옵션과 함께 사용하면 미리 컴파일된 헤더 파일\(.pch\)에서 만든 모든 개체 파일에 전체 디버깅 정보가 삽입됩니다.  사용되지 않습니다.  
  
## 구문  
  
```  
/Yd  
```  
  
## 설명  
 **\/Yd**는 사용되지 않습니다. [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)]에서는 이제 **\/Zi**를 대신 사용하여 .pdb 파일 하나에 여러 개체를 쓸 수 있습니다.  자세한 내용은 [Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ko-kr/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)을 참조하십시오.  
  
 디버깅 정보가 포함된 라이브러리를 배포해야 하는 경우가 아니라면 [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) 옵션을 **\/Z7** 및 **\/Yd** 대신 사용하십시오.  
  
 모든 .obj 파일에 전체 디버깅 정보를 저장하는 작업은 디버깅 정보가 포함된 라이브러리를 분산해야 하는 경우에만 필요합니다.  이 작업은 컴파일 속도를 느리게 하고 많은 디스크 공간을 필요로 합니다.  **\/Yc** 및 **\/Z7**이 **\/Yd** 없이 사용되면, 컴파일러는 .pch 파일에서 만든 첫 번째 .obj 파일에 공용 디버깅 정보를 저장합니다.  그런 다음, 컴파일러는.pch 파일에서 다음으로 만든 .obj 파일에 이 정보를 삽입하지 않고 정보에 대한 상호 참조를 삽입합니다.  얼마나 많은 .obj 파일에서 .pch 파일을 사용하든 간에, 하나의 .obj 파일만 공용 디버깅 정보를 포함합니다.  
  
 이러한 기본 동작으로 인해 빌드 시간이 빨라지고 필요한 디스크 공간이 줄어들기는 하지만, 조금만 변경되어도 공용 디버깅 정보가 들어 있는 .obj 파일을 다시 빌드해야 하는 경우에는 사용하지 않는 것이 좋습니다.  이 경우 컴파일러는 원래의 .obj 파일에 대한 상호 참조가 포함된 모든 .obj 파일을 다시 빌드해야 합니다.  또한, 공용 .pch 파일이 다른 프로젝트에서 사용되는 경우, 단일 .obj 파일에 대한 상호 참조의 의존도는 서로 다릅니다.  
  
 미리 컴파일된 헤더에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [\/Y\(미리 컴파일된 헤더\)](../../build/reference/y-precompiled-headers.md)  
  
-   [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)  
  
### Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하십시오.  
  
2.  **C\/C\+\+** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### 프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>를 참조하십시오.  
  
## 예제  
 각각 **\#include** 문을 포함하고 있는 두 개의 기본 파일 F.cpp와 G.cpp가 있다고 가정해봅시다.  
  
```  
#include "windows.h"  
#include "etc.h"  
```  
  
 다음 명령은 미리 컴파일된 헤더 파일 ETC.pch와 개체 파일 F.obj를 만듭니다.  
  
```  
CL /YcETC.H /Z7 F.CPP  
```  
  
 개체 파일 F.obj에는 WINDOWS.h와 ETC.h 및 여기에 포함된 기타 다른 헤더 파일에 대한 형식과 기호 정보가 들어 있습니다.  이제 미리 컴파일된 헤더 ETC.pch를 사용하여 소스 파일 G.cpp를 컴파일할 수 있습니다.  
  
```  
CL /YuETC.H /Z7 G.CPP  
```  
  
 개체 파일 G.obj는 미리 컴파일된 헤더에 대한 디버깅 정보를 포함하지 않지만, F.obj 파일의 해당 정보를 참조합니다.  F.obj 파일과 연결해야 한다는 점을 주의하십시오.  
  
 미리 컴파일된 헤더가 **\/Z7** 옵션으로 컴파일되지 않은 경우 나중에 **\/Z7** 옵션으로 컴파일할 때 미리 컴파일된 헤더를 계속 사용할 수 있습니다.  그러나 디버깅 정보는 현재 개체 파일에 삽입되며, 미리 컴파일된 헤더에 정의된 함수와 형식의 지역 기호는 디버거에서 사용할 수 없습니다.  
  
## 참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)