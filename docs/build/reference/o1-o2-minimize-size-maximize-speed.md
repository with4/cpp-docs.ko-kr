---
title: "-O1,-O2 (크기 최소화, 속도 최대화) | Microsoft Docs"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /o2
- /o1
dev_langs: C++
helpviewer_keywords:
- maximize speed compiler option [C++]
- minimize size compiler option [C++]
- -O2 compiler option [C++]
- fast code
- small code
- O2 compiler option [C++]
- /O2 compiler option [C++]
- -O1 compiler option [C++]
- O1 compiler option [C++]
- /O1 compiler option [C++]
ms.assetid: 2d1423f5-53d9-44da-8908-b33a351656c2
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f880b3cb806efa63299bf6cfa4aab4c72df23817
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>/O1, /O2(크기 최소화, 속도 최대화)

생성 된 코드의 속도 및 미리 정의 된 집합이 크기에 영향을 주는 옵션을 선택 합니다.

## <a name="syntax"></a>구문

> /O1  
> /O2

## <a name="remarks"></a>설명

**/O1** 및 **/O2** 컴파일러 옵션은 신속 하 게 한 번에 몇 가지 특정 최적화 옵션을 설정 합니다. **/O1** 옵션의 대부분의 경우 가장 작은 코드를 작성 하는 개별 최적화 옵션을 설정 합니다. **/O2** 옵션의 대부분의 경우 가장 빠른 코드를 작성 하는 옵션을 설정 합니다. **/O2** 옵션이 릴리스 빌드에 대 한 기본값입니다. 이 테이블에서 설정 하는 특정 옵션을 보여 줍니다. **/O1** 및 **/O2**:

|옵션|와 동일|
|------------|-------------------|
|**/O1** (크기 최소화)|[/Og](../../build/reference/og-global-optimizations.md) [/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) [/Oy](../../build/reference/oy-frame-pointer-omission.md) [/Ob2](../../build/reference/ob-inline-function-expansion.md) [/Gs](../../build/reference/gs-control-stack-checking-calls.md) [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) [/Gy](../../build/reference/gy-enable-function-level-linking.md)|
|**/O2** (속도 최대화)|[/Og](../../build/reference/og-global-optimizations.md) [/Oi](../../build/reference/oi-generate-intrinsic-functions.md) [/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) [/Oy](../../build/reference/oy-frame-pointer-omission.md) [/Ob2](../../build/reference/ob-inline-function-expansion.md) [/Gs](../../build/reference/gs-control-stack-checking-calls.md) [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) [/Gy](../../build/reference/gy-enable-function-level-linking.md)|

**/O1** 및 **/O2** 함께 사용할 수 없습니다.

> [!NOTE]  
> **x86 특정**  
> 프레임 포인터 생략의 사용을 의미 하는 이러한 옵션 ([/Oy](../../build/reference/oy-frame-pointer-omission.md)) 옵션입니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 아래 **구성 속성**개방형 **C/c + +** 선택한 후는 **최적화** 속성 페이지.

1. 수정 된 **최적화** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[/O 옵션 (코드 최적화)](../../build/reference/o-options-optimize-code.md)  
[컴파일러 옵션](../../build/reference/compiler-options.md)  
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)  
[/EH (예외 처리 모델)](../../build/reference/eh-exception-handling-model.md)