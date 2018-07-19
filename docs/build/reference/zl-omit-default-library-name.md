---
title: -Zl (기본 라이브러리 이름 생략) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zi
- VC.Project.VCCLCompilerTool.OmitDefaultLibName
dev_langs:
- C++
helpviewer_keywords:
- -Zl compiler option [C++]
- ZI compiler option
- Omit Default Library Name compiler option
- /Zl compiler option [C++]
- default libraries, omitting names
ms.assetid: b27d39d0-44d6-498c-84ae-27c1326fee59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c14a3217334c2c43bac7fbcce8b0bfd60a609d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379720"
---
# <a name="zl-omit-default-library-name"></a>/Zl(기본 라이브러리 이름 생략)
.Obj 파일에서 기본 C 런타임 라이브러리 이름을 생략합니다. 기본적으로 컴파일러는 올바른 라이브러리로 링커를 보내기 위해 라이브러리 이름을 .obj 파일에 넣습니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Zl  
```  
  
## <a name="remarks"></a>설명  
 기본 라이브러리에 대 한 자세한 내용은 참조 하십시오. [런타임 라이브러리 사용](../../build/reference/md-mt-ld-use-run-time-library.md)합니다.  
  
 사용할 수 있습니다 **/Zl** 라이브러리에 배치 하려는.obj 파일을 컴파일할 수 있습니다. 라이브러리 이름 생략 소량의 단일.obj 파일에 대 한 공간을 저장 하지만 저장 된 총 공간은 많은 개체 모듈을 포함 하는 라이브러리에 중요 한입니다.  
  
 이 옵션은 고급 옵션입니다. 응용 프로그램이이 지원에 따라 링크 타임 오류가 발생 응용 프로그램에 필요할 수 있는 특정 C 런타임 라이브러리 지원을 제거이 옵션을 설정 합니다. 이 옵션을 사용 하는 경우 다른 방법으로의 필수 구성 요소를 제공 해야 합니다.  
  
 사용 하 여 [/NODEFAULTLIB (라이브러리 무시)](../../build/reference/nodefaultlib-ignore-libraries.md)합니다. 모든.obj 파일에 라이브러리 참조를 무시 하도록 링커에 지시 합니다.  
  
 자세한 내용은 [CRT 라이브러리 기능](../../c-runtime-library/crt-library-features.md)을 참조하세요.  
  
 로 컴파일할 때 **/Zl**, `_VC_NODEFAULTLIB` 정의 됩니다.  예를 들어:  
  
```  
// vc_nodefaultlib.cpp  
// compile with: /Zl  
void Test() {  
   #ifdef _VC_NODEFAULTLIB  
      int i;  
   #endif  
  
   int i;   // C2086  
}  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **고급** 속성 페이지.  
  
4.  수정 된 **기본 라이브러리 이름 생략** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)