---
title: "-Ob (인라인 함수 확장) | Microsoft Docs"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.InlineFunctionExpansion
- VC.Project.VCCLCompilerTool.InlineFunctionExpansion
- /ob
dev_langs: C++
helpviewer_keywords:
- inline functions, function expansion compiler option [C++]
- -Ob1 compiler option [C++]
- -Ob0 compiler option [C++]
- /Ob0 compiler option [C++]
- /Ob1 compiler option [C++]
- any suitable compiler option [C++]
- Ob2 compiler option [C++]
- Ob1 compiler option [C++]
- /Ob2 compiler option [C++]
- Ob compiler option [C++]
- -Ob2 compiler option [C++]
- disable compiler option [C++]
- -Ob compiler option [C++]
- /Ob compiler option [C++]
- only __inline compiler option [C++]
- Ob0 compiler option [C++]
- inline expansion, compiler option
ms.assetid: f134e6df-e939-4980-a01d-47425dbc562a
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b83d470eaf6a30698d8c2836620a0688daa35cc1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ob-inline-function-expansion"></a>/Ob(인라인 함수 확장)

함수의 인라인 확장을 제어합니다.

## <a name="syntax"></a>구문

> /Ob {0 | 1 | 2}

## <a name="arguments"></a>인수

**0**  
인라인 확장을 사용하지 않도록 설정합니다. 기본적으로 모든 기능에 대 한 컴파일러의 판단에 따라 확장 발생 라고도 *자동 인라인*합니다.

**1**  
으로 표시 된 확장 [인라인](../../cpp/inline-functions-cpp.md), `__inline`, 또는 `__forceinline`, 또는 클래스 선언에 정의 된 c + + 멤버 함수입니다.

**2**  
기본값입니다. `inline`, `__inline` 또는 `__forceinline`으로 표시된 함수와 컴파일러에서 선택한 기타 함수를 확장합니다.

**/Ob2** 때 적용 됩니다 [/O1, /O2 (크기 최소화, 속도 최대화)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) 또는 [/Ox (활성화 가장 속도 최적화)](../../build/reference/ox-full-optimization.md) 사용 됩니다.

이 옵션을 사용 하려면 사용 하 여 최적화를 사용 하는 **/O1**, **/O2**, **/Ox**, 또는 **/Og**합니다.  

## <a name="remarks"></a>설명

컴파일러는 인라인 확장 옵션과 키워드를 제안으로 처리합니다. 함수가 인라인 확장된다는 보장은 없습니다. 인라인 확장을 사용하지 않을 수 있으나 `__forceinline` 키워드를 사용하는 경우에도 컴파일러가 강제로 특정 함수를 인라인 확장하도록 할 수는 없습니다.

사용할 수는 `#pragma` [auto_inline](../../preprocessor/auto-inline.md) 지시문으로 함수를 인라인 확장 후보 고려 대상에서 제외 합니다. 또한 참조는 `#pragma` [내장](../../preprocessor/intrinsic.md) 지시문입니다.

> [!NOTE]
> 프로 파일링 테스트 실행에서 수집 되는 정보 재정의 될 수 있는 효과에 지정 하는 경우 최적화 **/Ob**, **/Os**, 또는 **/Ot**합니다. 자세한 내용은 참조 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)합니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 확장 **구성 속성**, **C/c + +**를 선택 하 고 **최적화**합니다.

1. 수정 된 **인라인 함수 확장** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[/O 옵션 (코드 최적화)](../../build/reference/o-options-optimize-code.md)  
[컴파일러 옵션](../../build/reference/compiler-options.md)  
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)