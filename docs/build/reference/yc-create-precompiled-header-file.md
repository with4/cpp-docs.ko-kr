---
title: "-Yc (미리 컴파일된 헤더 파일 만들기) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.UsePrecompiledHeader
- /yc
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderThrough
- VC.Project.VCCLWCECompilerTool.UsePrecompiledHeader
- VC.Project.VCCLCompilerTool.PrecompiledHeaderThrough
dev_langs:
- C++
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- .pch files, creating
- -Yc compiler option [C++]
- /Yc compiler option [C++]
- Yc compiler option [C++]
ms.assetid: 47c2e555-b4f5-46e6-906e-ab5cf21f0678
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 865b5e0fa7039a0b60f524c2f13a367569757d92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="yc-create-precompiled-header-file"></a>/Yc(미리 컴파일된 헤더 파일 만들기)
컴파일 특정 지점에서 상태를 나타내는 미리 컴파일된 헤더 (.pch) 파일을 만들도록 컴파일러에 지시 합니다.  
  
## <a name="syntax"></a>구문  
  
> __/Yc__
> __/Yc__*파일 이름*  
  
  
## <a name="arguments"></a>인수  
*filename*  
 헤더 (.h) 파일을 지정합니다. 이 인수를 사용 하는 경우 컴파일러 및.h 파일까지 모든 코드를 컴파일합니다.  
  
## <a name="remarks"></a>설명  
 때 **/Yc** 컴파일러 기본 파일에까지 또는 기본 소스 파일의 끝까지 모든 코드를 컴파일하는 인수 없이 지정 된 위치는 [hdrstop](../../preprocessor/hdrstop.md) 지시문 발생 합니다. 결과.pch 파일을 사용 하 여 다른 파일 이름을 지정 하지 않으면 기본 소스 파일과 동일한 기본 이름을는 **hdrstop** pragma 또는 **/Fp** 옵션입니다.  
  
 지정 된 파일의 기본 이름에서 만든 이름으로 미리 컴파일된 코드 파일에 저장 된 **/Yc** 옵션과 확장명이.pch 합니다. 사용할 수도 있습니다는 [/Fp (이름입니다. Pch 파일)](../../build/reference/fp-name-dot-pch-file.md) 미리 컴파일된 헤더 파일에 대 한 이름을 지정 하는 옵션입니다.  
  
 사용 하는 경우 __/Yc__*filename*, 컴파일러 및 이후 사용 하기 위해 지정 된 파일까지 모든 코드를 컴파일하는 [/Yu (미리 컴파일된 헤더 파일 사용)](../../build/reference/yu-use-precompiled-header-file.md) 옵션입니다.  
  
 경우 옵션 __/Yc__*filename* 및 __/Yu__*filename* 같은 명령줄에서 발생 하 고 참조 하거나 암시, 같은 파일 이름을 둘 다 __/Yc__*filename* 우선적으로 적용 합니다. 이 기능은 메이크파일 작성을 단순화 합니다.  
  
 미리 컴파일된 헤더에 대 한 자세한 내용은 다음을 참조 하세요.  
  
-   [/Y (미리 컴파일된 헤더)](../../build/reference/y-precompiled-headers.md)  
  
-   [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  .Cpp 파일을 선택 합니다. .Cpp 파일을 #include 미리 컴파일된 헤더 정보를 포함 하는.h 파일입니다. 프로젝트의 **/Yc** 파일 수준에서 설정을 재정의할 수 있습니다.  
  
2.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
3.  열기는 **구성 속성**, **C/c + +**, **미리 컴파일된 헤더** 속성 페이지.  
  
4.  수정 된 **미리 컴파일된 헤더** 속성입니다.  
  
5.  파일 이름으로 설정 하려면 수정 된 **미리 컴파일된 헤더 파일** 속성입니다.
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>을 참조하십시오.  
  
## <a name="example"></a>예  
 다음 코드를 살펴보세요.  
  
```cpp  
// prog.cpp
// compile with: cl /c /Ycmyapp.h prog.cpp
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
// ...  
```  
  
명령을 사용 하 여이 코드를 컴파일할 때 `CL /YcMYAPP.H PROG.CPP`, 컴파일러 AFXWIN.h, RESOURCE.h에 대 한 모든 전처리를 저장 하 고 미리 컴파일된 헤더 파일에 MYAPP.h MYAPP.pch를 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md) [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)