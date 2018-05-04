---
title: -I (추가 포함 디렉터리) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories
- VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories
- /I
- VC.Project.VCNMakeTool.IncludeSearchPath
dev_langs:
- C++
helpviewer_keywords:
- /I compiler option [C++]
- Additional Include Directories compiler option
- I compiler option [C++]
- -I compiler option [C++]
- set include directories
- include directories, compiler option [C++]
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 435714d72eeabe74f0cd85509d74dff5d541b019
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="i-additional-include-directories"></a>/I(추가 포함 디렉터리)
Include 파일을 검색할 디렉터리 목록에 디렉터리를 추가 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/I[ ]directory  
```  
  
## <a name="arguments"></a>인수  
 `directory`  
 디렉터리 목록에 추가할 디렉터리는 포함 파일에 대 한 검색 합니다.  
  
## <a name="remarks"></a>설명  
 둘 이상의 디렉터리를 추가 하려면이 옵션을 두 번 이상 사용 합니다. 디렉터리를 지정된 된 포함 파일을 찾을 때까지 검색 합니다.  
  
 표준 포함 경로 무시 함께이 옵션을 사용할 수 있습니다 ([/X (표준 포함 경로 무시)](../../build/reference/x-ignore-standard-include-paths.md)) 옵션입니다.  
  
 컴파일러는 다음 순서 대로 디렉터리를 검색 합니다.  
  
1.  소스 파일을 포함 하는 디렉터리입니다.  
  
2.  지정 된 디렉터리는 **/I** CL 대로 검색 순서로 옵션입니다.  
  
3.  에 지정 된 디렉터리는 **INCLUDE** 환경 변수입니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **일반** 속성 페이지.  
  
4.  수정 된 **추가 포함 디렉터리** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 명령은 다음과 같은 순서로 MAIN.c 요청한 포함 파일에 대 한 찾습니다: \INCLUDE 디렉터리에서 다음 다음 \MY\INCLUDE 디렉터리에서 MAIN.c를 포함 하 고 마지막으로 디렉터리에서에 할당 된 포함 된 디렉터리에서 첫 번째 환경 변수입니다.  
  
```  
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C  
```  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)