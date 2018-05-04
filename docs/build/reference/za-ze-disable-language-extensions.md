---
title: -Za,-Ze (언어 확장명 사용 안 함) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions
- /za
- /ze
- VC.Project.VCCLCompilerTool.DisableLanguageExtensions
dev_langs:
- C++
helpviewer_keywords:
- -Za compiler option [C++]
- Za compiler option [C++]
- language extensions, disabling in compiler
- -Ze compiler option [C++]
- language extensions
- enable language extensions
- /Za compiler option [C++]
- /Ze compiler option [C++]
- Disable Language Extensions compiler option
- Ze compiler option [C++]
ms.assetid: 65e49258-7161-4289-a176-7c5c0656b1a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2949a3d60af6d9058f02d12aac1fd86dead5affa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="za-ze-disable-language-extensions"></a>/Za, /Ze(언어 확장명 사용 안 함)
**/Za** 컴파일러 옵션은 ANSI c 89에서 또는 C + + 11 ISO와 호환 되지 않는 언어 구문에 대 한 오류를 내보냅니다. **/Ze** 컴파일러 옵션을 기본적으로 켜져 있는 Microsoft 확장을 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Za  
/Ze  
```  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  **/Ze** 옵션은 기본적으로 켜져 동작 때문에 거부 됩니다. 사용 하는 것이 좋습니다는 [/Zc (규칙)](../../build/reference/zc-conformance.md) 컴파일러 옵션을 특정 언어 확장 기능을 제어 합니다. 목록이 사용 되지 않는 컴파일러 옵션에 대 한 참조는 **사용 되지 않음 및 컴파일러 옵션 제거** 섹션 [컴파일러 옵션 범주별 목록](../../build/reference/compiler-options-listed-by-category.md)합니다.  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] 컴파일러는 다양 한 ANSI c 89에서, ISO C99 또는 ISO c + + 표준에 지정 된 것 이상의 기능을 제공 합니다. 이러한 기능은 C 및 c + +에 대 한 Microsoft 확장으로 전체적으로 알려져 있습니다. 이러한 확장은 기본적으로 사용할 수 있으며 사용할 수 없는 경우는 **/Za** 옵션을 지정 합니다. 특정 확장에 대 한 자세한 내용은 참조 [C 및 c + +에 대 한 Microsoft 확장](../../build/reference/microsoft-extensions-to-c-and-cpp.md)합니다.  
  
 언어 확장을 사용 하지 않도록 지정 하 여는 것이 좋습니다는 **/Za** 옵션이 프로그램 다른 환경으로 이식 하려는 경우. 때 **/Za** 컴파일러가 처리 Microsoft 확장 키워드 단순 식별자로 지정 된 다른 Microsoft 확장을 사용 하지 않도록 설정 하 고 자동으로 정의 된 `__STDC__` C 프로그램에 대 한 미리 정의 된 매크로입니다.  
  
 다른 컴파일러 옵션을 사용한 **/Za** 컴파일러에서 표준 규칙을 준수 하는 방식에 영향을 줄 수 있습니다. 예를 들어 **/Za** 및 [/fp (부동 소수점 동작 지정)](../../build/reference/fp-specify-floating-point-behavior.md) ISO C99 또는 C + + 11 표준에 맞지 않는 부동 소수점 형식 승격 동작이 발생할 수 있습니다.  
  
 특정 표준을 준수 동작 설정을 지정 하는 방법은 참조 하십시오.는 [/Zc](../../build/reference/zc-conformance.md) 컴파일러 옵션입니다.  
  
 규칙과 관련 된 문제에 대 한 자세한 내용은 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)], 참조 [비표준 동작](../../cpp/nonstandard-behavior.md)합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  탐색 창에서 선택 **구성 속성**, **C/c + +**, **언어**합니다.  
  
3.  수정 된 **언어 확장 사용 안 함** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [/Zc(규칙)](../../build/reference/zc-conformance.md)