---
title: "-Fp (이름입니다. Pch 파일) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- /fp
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
dev_langs: C++
helpviewer_keywords:
- Fp compiler option [C++]
- -Fp compiler option [C++]
- naming precompiler header files
- PCH files, naming
- names [C++], PCH
- .pch files, naming
- precompiled header files, naming
- /Fp compiler option [C++]
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d00b7a4007229dc545923f0dc89ab7607111c6f1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="fp-name-pch-file"></a>/Fp(.PCH 파일 이름 지정)
기본 경로 이름을 사용 하는 대신 미리 컴파일된 헤더에 대 한 경로 이름을 제공 합니다.  
  
## <a name="syntax"></a>구문  
  
> **/Fp**_경로 이름_  
  
## <a name="remarks"></a>설명  
 이 옵션을 사용 하 여 [/Yc (미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md) 또는 [/Yu (미리 컴파일된 헤더 파일 사용)](../../build/reference/yu-use-precompiled-header-file.md) 기본 경로 이름을 사용 하는 대신 미리 컴파일된 헤더에 대 한 경로 이름을 제공 합니다. 사용할 수도 있습니다 **/Fp** 와 **/Yc** 와 다른 미리 컴파일된 헤더 파일의 사용을 지정할 수는 **/Yc***filename* 인수 및 소스 파일의 기본 이름입니다.  
  
 경로 이름의 일부로 확장을 지정 하지 않으면 한 확장명을.pch 간주 됩니다. 파일 이름 없이 디렉터리를 지정 하는 경우 기본 파일 이름은 VC*x*0.pch, 여기서 *x* 은 사용 중인 Visual c + +의 주 버전.  
  
 사용할 수도 있습니다는 **/Fp** 옵션과 함께 **/Yu**합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **미리 컴파일된 헤더** 속성 페이지.  
  
4.  수정 된 **미리 컴파일된 헤더 파일** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderFile%2A>을 참조하세요.  
  
## <a name="example"></a>예제  
 프로그램의 디버깅 버전에 대 한 미리 컴파일된 헤더 파일을 만들려고 할 헤더 파일과 소스 코드를 컴파일하는 경우와 같은 명령을 지정할 수 있습니다.  
  
```  
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP  
```  
  
## <a name="example"></a>예제  
 다음 명령은 MYPCH.pch 라는 미리 컴파일된 헤더 파일의 사용을 지정 합니다. 컴파일러는 PROG.cpp의 소스 코드 미리 컴파일 MYAPP.h 통해 하며 MYPCH.pch에 미리 컴파일된 코드를 가정 합니다. MYPCH.pch 콘텐츠를 사용 하 고.obj 파일을 만드는 PROG.cpp의 나머지를 컴파일합니다. 이 예의 출력은 PROG.exe 이라는 파일로 내보내집니다.  
  
```  
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP  
```  
  
## <a name="see-also"></a>참고 항목  
 [출력 파일 (/ F) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)