---
title: -Ox (대부분의 속도 최적화 사용에 필요) | Microsoft Docs
ms.custom: ''
ms.date: 09/25/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.ToolOptimization
- /ox
dev_langs:
- C++
helpviewer_keywords:
- Ox compiler option [C++]
- fast code [C++]
- /Ox compiler option [C++]
- -Ox compiler option [C++]
ms.assetid: 3ad7c30b-c615-428c-b1d0-2e024f81c760
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 569563bff030904988e93db749438eaeb58ce9db
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ox-enable-most-speed-optimizations"></a>/Ox (대부분의 속도 최적화 사용에 필요)

**/Ox** 컴파일러 옵션을 사용 하면 속도 유사한 최적화 되도록 설정 합니다. Visual Studio IDE 및 컴파일러 도움말 메시지의 일부 버전에서는이 매개 변수 이라고 *최대 최적화*, 하지만 **/Ox** 컴파일러 옵션으로 사용 하도록 설정 하는 속도 최적화 옵션의 하위 집합만 사용 하면 **/O2**합니다.

## <a name="syntax"></a>구문

> /Ox

## <a name="remarks"></a>설명

**/Ox** 컴파일러 옵션 사용은 **/O** 컴파일러 옵션은 총 속도입니다. **/Ox** 추가 컴파일러 옵션을 다루지 않습니다 [/GF (중복 문자열 제거)](../../build/reference/gf-eliminate-duplicate-strings.md) 및 [/Gy (함수 수준 링크 사용)](../../build/reference/gy-enable-function-level-linking.md) 로사용하도록설정하는옵션[/O1 또는 /O2 (크기 최소화, 속도 최대화)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)합니다. 추가 옵션에서 적용 **/O1** 및 **/O2** 디버깅에 영향을 줄 수 있는 대상 주소 및 엄격한 언어 규칙에 따라 공유 함수 또는 문자열에 대 한 포인터를 발생할 수 있습니다. **/Ox** 옵션은 포함 하지 않고 대부분의 최적화를 사용 하도록 설정 하는 쉬운 방법을 **/GF** 및 **/Gy**합니다. 자세한 내용은의 설명을 참조는 [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) 및 [/Gy](../../build/reference/gy-enable-function-level-linking.md) 옵션입니다.

**/Ox** 컴파일러 옵션 조합 하 여 다음 옵션을 사용 하 여 것과 같습니다.

- [/Ob (인라인 함수 확장)](../../build/reference/ob-inline-function-expansion.md)option 매개 변수는 2, (**/Ob2**)

- [/Og(전역 최적화)](../../build/reference/og-global-optimizations.md)

- [/Oi(내장 함수 만들기)](../../build/reference/oi-generate-intrinsic-functions.md)

- [/Ot (크기 우선 빠른 코드)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)

- [/Oy (프레임 포인터 생략)](../../build/reference/oy-frame-pointer-omission.md)

**/Ox** 에서 함께 사용할 수 없습니다.

- [/O1 (크기 최소화)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)

- [/ O 2 (속도 최대화)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)

- [/Od(디버그 사용 안 함)](../../build/reference/od-disable-debug.md)

오차의 속도 취소할 수는 **/Ox** 컴파일러 옵션을 지정 하는 경우 **/Oxs**를 결합 하는 **/Ox** 컴파일러 옵션을 [(크기 우선 작은 /Os 코드)](../../build/reference/os-ot-favor-small-code-favor-fast-code.md)합니다. 조합 된 옵션이 더 작은 코드 크기를 선호합니다.

지정할수록 좋습니다 릴리스 빌드에 사용할 수 있는 모든 파일-수준 최적화를 적용 하려면 [/O2 (속도 최대화)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) 대신 **/Ox**, 및 [/O1 (크기 최소화)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) 대신 **/Oxs**합니다. 릴리스에서 더 많은 최적화 빌드에 대해 고려해는 [/GL (전체 프로그램 최적화)](../../build/reference/gl-whole-program-optimization.md) 컴파일러 옵션 및 [/LTCG (링크 타임 코드 생성)](../../build/reference/ltcg-link-time-code-generation.md) 링커 옵션입니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 아래 **구성 속성**개방형 **C/c + +** 선택한 후는 **최적화** 속성 페이지.

1. 수정 된 **최적화** 속성입니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[/O 옵션(코드 최적화)](../../build/reference/o-options-optimize-code.md)  
[컴파일러 옵션](../../build/reference/compiler-options.md)  
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)