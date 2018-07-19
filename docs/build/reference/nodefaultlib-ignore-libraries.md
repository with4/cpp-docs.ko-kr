---
title: -NODEFAULTLIB (라이브러리 무시) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLinkerTool.OVERWRITEDefaultLibraryNames
- /nodefaultlib
dev_langs:
- C++
helpviewer_keywords:
- default libraries, removing
- -NODEFAULTLIB linker option
- libraries, ignore
- NODEFAULTLIB linker option
- /NODEFAULTLIB linker option
- ignore libraries linker option
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51caac10218d5f4d1787b2256875001ac32dc2b9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375716"
---
# <a name="nodefaultlib-ignore-libraries"></a>/NODEFAULTLIB(라이브러리 무시)
```  
/NODEFAULTLIB[:library]   
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *라이브러리*  
 링커가 외부 참조를 확인할 때 무시 해야 하는 라이브러리입니다.  
  
## <a name="remarks"></a>설명  
 /NODEFAULTLIB 옵션을 사용 하면 링커에서 외부 참조를 확인할 때 검색 하는 라이브러리 목록에서 하나 이상의 기본 라이브러리를 제거 합니다.  
  
 기본 라이브러리에 대 한 참조를 포함 하지 않는.obj 파일을 만들려면 사용 [/Zl (기본 라이브러리 이름 생략)](../../build/reference/zl-omit-default-library-name.md)합니다.  
  
 기본적으로 /NODEFAULTLIB 외부 참조를 확인할 때 검색 하는 라이브러리 목록에서 모든 기본 라이브러리를 제거 합니다. 선택적 *라이브러리* 매개 변수는 외부 참조를 확인할 때 검색 하는 라이브러리 목록에서 지정된 된 라이브러리를 제거할 수 있습니다. 제외 하려는 각 라이브러리에 대해 하나의 /NODEFAULTLIB 옵션을 지정 합니다.  
  
 링커는 명시적으로 지정한 다음에 지정 된 기본 라이브러리 /DEFAULTLIB 옵션을 사용 하는 라이브러리에서 찾은 다음.obj 파일에 지정 된 기본 라이브러리에서 먼저 검색 하 여 외부 정의에 대 한 참조를 확인 합니다.  
  
 /NODEFAULTLIB:*라이브러리* 재정의 [/DEFAULTLIB:](../../build/reference/defaultlib-specify-default-library.md)*라이브러리* 때 동일한 *라이브러리* 둘 다에 이름을 지정 합니다.  
  
 /NODEFAULTLIB을 사용 하는 경우 예를 들어 C 런타임 라이브러리 없이 프로그램을 빌드할 수 있습니다를 사용 하도록 [/ENTRY](../../build/reference/entry-entry-point-symbol.md) 프로그램의 진입점 (함수)를 지정할 수 있습니다. 자세한 내용은 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)을 참조하세요.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **입력**속성 페이지.  
  
4.  선택 된 **모든 기본 라이브러리 무시** 속성에서 무시 하려는 라이브러리의 목록을 지정 하거나는 **특정 라이브러리 무시** 속성입니다. **명령줄** 속성 페이지에는 이러한 속성에 변경 내용의 결과 표시 됩니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)