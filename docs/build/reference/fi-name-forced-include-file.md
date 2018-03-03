---
title: "-FI (강제 포함 파일 이름) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCNMakeTool.ForcedIncludes
- VC.Project.VCCLCompilerTool.ForcedIncludeFiles
- VC.Project.VCCLWCECompilerTool.ForcedIncludeFiles
- /fi
dev_langs:
- C++
helpviewer_keywords:
- FI compiler option [C++]
- -FI compiler option [C++]
- /FI compiler option [C++]
- preprocess header file compiler option [C++]
ms.assetid: 07e79577-8152-4df9-a64c-aae08c603397
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b2003ab35bf76a8ac3e70288576af821a6c8e6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fi-name-forced-include-file"></a>/FI(강제 포함 파일 이름 지정)
전처리기가 지정 된 헤더 파일을 처리 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/FI[ ]pathname  
```  
  
## <a name="remarks"></a>설명  
 이 옵션은에 큰따옴표를 사용 하 여 파일을 지정 하는 것과 같습니다는 `#include` 명령줄 CL 환경 변수 또는 명령 파일에 지정 된 모든 소스 파일의 첫 번째 줄에 지시문입니다. 여러 개 사용 하면 **/FI** 파일 옵션은 CL에서 처리 되는 순서에 포함 됩니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **고급** 속성 페이지.  
  
4.  수정 된 **강제 포함** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [출력 파일 (/ F) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)