---
title: -c (링크 없이 컴파일) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /c
dev_langs:
- C++
helpviewer_keywords:
- suppress link
- cl.exe compiler, compiling without linking
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 86bd1ddcb6d44cfa433d4119f90eb02695089aa4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="c-compile-without-linking"></a>/c(링크 없이 컴파일)
링크에 대 한 자동 호출을 방지합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/c  
```  
  
## <a name="remarks"></a>설명  
 로 컴파일할 **/c** 만.obj 파일을 만듭니다. 적절 한 파일과 빌드의 링크 단계를 수행 하는 옵션을 사용 하 여 링크를 명시적으로 호출 해야 합니다.  
  
 사용 하 여 개발 환경에서 만든 내부 프로젝트는 **/c** 기본적으로 옵션입니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
-   이 옵션은 개발 환경 내에서 사용할 수 없습니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 명령줄 FIRST.obj 및 SECOND.obj 개체 파일을 만듭니다. THIRD.obj는 무시 됩니다.  
  
```  
CL /c FIRST.C SECOND.C THIRD.OBJ  
```  
  
 실행 파일을 만들려면 링크를 호출 해야 합니다.  
  
```  
LINK firsti.obj second.obj third.obj /OUT:filename.exe  
```  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)