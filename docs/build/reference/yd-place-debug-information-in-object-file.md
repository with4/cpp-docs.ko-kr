---
title: -Yd (개체 파일에 디버그 정보) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /yd
dev_langs:
- C++
helpviewer_keywords:
- /Yd compiler option [C++]
- -Yd compiler option [C++]
- debugging [C++], debug information files
- Yd compiler option [C++]
ms.assetid: c5a699fe-65ce-461e-964c-7f5eb2a8320a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39b03b0faf975caba8c5a287c88afcdf53f7a71f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378235"
---
# <a name="yd-place-debug-information-in-object-file"></a>/Yd(개체 파일에 디버그 정보 삽입)
함께 사용 하면 미리 컴파일된 헤더 (.pch) 파일에서 만든 전체 디버깅 정보 모든 개체 파일에 삽입 된 [/Yc](../../build/reference/yc-create-precompiled-header-file.md) 및 [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md) 옵션입니다. 더 이상 사용되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Yd  
```  
  
## <a name="remarks"></a>설명  
 **/Yd** 는 사용 되지 않습니다. [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 에서는 이제는 여러 개체를 단일.pdb 파일을 쓸 사용 **/Zi** 대신 합니다. 목록이 사용 되지 않는 컴파일러 옵션에 대 한 참조 **사용 되지 않음 및 컴파일러 옵션 제거** 에 [컴파일러 옵션 범주별 목록](../../build/reference/compiler-options-listed-by-category.md)합니다.  
  
 사용 하 여 디버깅 정보를 포함 하는 라이브러리를 배포 하는 제외의 [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) 옵션 대신 **/Z7** 및 **/Yd**합니다.  
  
 모든.obj 파일에 완전 한 디버깅 정보를 저장 하는 것은 디버깅 정보를 포함 하는 라이브러리를 배포 하는 데에 필요 합니다. 컴파일 느려지고 상당한 디스크 공간이 필요 합니다. 때 **/Yc** 및 **/Z7** 없이 사용 하는 **/Yd**, 컴파일러.pch 파일에서 만든 첫 번째.obj 파일에 일반 디버깅 정보를 저장 합니다. 컴파일러는.pch 파일;에서 앞으로 생성 하는.obj 파일에이 정보를 삽입 하지 않습니다. 정보에 대 한 상호 참조를 삽입합니다. .Pch 파일을 사용 하는.obj 파일의 수에 관계 없이 하나의.obj 파일 일반적인 디버깅 정보를 포함 합니다.  
  
 이 기본 동작으로 인해 빌드 시간이 빠르고 디스크 공간 요구 사항 감소, 있지만 것은 바람직하지 않습니다는 약간만 변경 일반적인 디버깅 정보를 포함 하는.obj 파일을 다시 작성 해야 하는 경우. 이 경우 컴파일러는 원래.obj 파일에 대 한 상호 참조를 포함 하는 모든.obj 파일을 다시 만들어야 합니다. 또한 일반적인.pch 파일을 다른 프로젝트에서 사용 하는 경우 단일.obj 파일에 대 한 상호 참조에 대 한 의존도가 어렵습니다.  
  
 미리 컴파일된 헤더에 대 한 자세한 내용은 다음을 참조 하세요.  
  
-   [/Y(미리 컴파일된 헤더)](../../build/reference/y-precompiled-headers.md)  
  
-   [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="examples"></a>예제  
 있다고 가정 하면 두 개의 기본 파일 F.cpp와 각 포함 하 고 있는 G.cpp **#include** 문:  
  
```  
#include "windows.h"  
#include "etc.h"  
```  
  
 다음 명령은 만듭니다 미리 컴파일된 헤더 파일 ETC.pch 및 F.obj 개체 파일:  
  
```  
CL /YcETC.H /Z7 F.CPP  
```  
  
 F.obj 개체 파일 형식 및 WINDOWS.h 및 ETC.h에 대 한 기호 정보 (및 다른 헤더 파일 포함)를 포함 합니다. 이제 미리 컴파일된 헤더 ETC.pch G.cpp 소스 파일을 컴파일하는 데 사용할 수 있습니다.  
  
```  
CL /YuETC.H /Z7 G.CPP  
```  
  
 개체 파일 G.obj 미리 컴파일된 헤더에 대 한 디버깅 정보가 포함 되지 않은 있지만 F.obj 파일의 해당 정보를 참조 합니다. F.obj 파일과 함께 연결 해야 하는 참고 합니다.  
  
 미리 컴파일된 헤더가으로 컴파일되지 않은 경우 **/Z7**, 나중에 사용할 수 있습니다 **/Z7**합니다. 그러나 현재 개체 파일에 디버깅 정보 포함 및 함수와 미리 컴파일된 헤더에 정의 된 형식에 대 한 로컬 기호는 디버거에서 사용할 수 없는 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)