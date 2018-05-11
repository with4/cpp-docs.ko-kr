---
title: -/LIBPATH (추가 Libpath) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /libpath
- VC.Project.VCLinkerTool.AdditionalLibraryDirectories
dev_langs:
- C++
helpviewer_keywords:
- LIBPATH linker option
- /LIBPATH linker option
- Additional Libpath linker option
- environment library path override
- -LIBPATH linker option
- library path linker option
ms.assetid: 7240af0b-9a3d-4d53-8169-2a92cd6958ba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ccb94ad20735e81fc3d83f757cc0265cdc32169
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="libpath-additional-libpath"></a>/LIBPATH(추가 Libpath)
```  
/LIBPATH:dir  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `dir`  
 경로 지정 LIB 환경 옵션에 지정 된 경로 검색 하기 전에 링커가 검색 합니다.  
  
## <a name="remarks"></a>설명  
 환경 라이브러리 경로를 재정의할 /LIBPATH 옵션을 사용 합니다. 링커에서 먼저이 옵션을 지정 된 경로에서 검색 하 고 누른 다음 LIB 환경 변수에 지정 된 경로에서 검색 됩니다. 입력 하면 각 /LIBPATH 옵션에 대 한 디렉터리를 하나만 지정할 수 있습니다. 둘 이상의 디렉터리를 지정 하려는 경우에 여러 /LIBPATH 옵션을 지정 해야 합니다. 링커는 다음 순서에 지정 된 디렉터리를 검색 합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **일반** 속성 페이지.  
  
4.  수정 된 **추가 라이브러리 디렉터리** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalLibraryDirectories%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)