---
title: -O 옵션 (코드 최적화) | Microsoft Docs
ms.custom: ''
ms.date: 09/25/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.Optimization
- /o
- VC.Project.VCCLWCECompilerTool.Optimization
dev_langs:
- C++
helpviewer_keywords:
- performance, cle.exe compiler
- cl.exe compiler, performance
ms.assetid: 77997af9-5555-4b3d-aa57-6615b27d4d5d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 83ddebec9db7a02db40ef31c89c7ff48a66cf665
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="o-options-optimize-code"></a>/O 옵션(코드 최적화)

**/O** 다양 한 옵션으로 제어 코드 속도 최대 또는 최소 크기를 만들 수 있는 최적화 합니다.

- [/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) 최소 크기 코드를 생성 하는 최적화의 조합을 설정 합니다.

- [/O2](../../build/reference/o1-o2-minimize-size-maximize-speed.md) 최대 속도 대 한 코드를 최적화 하는 최적화의 조합을 설정 합니다.

- [/Ob](../../build/reference/ob-inline-function-expansion.md) 인라인 함수 확장을 제어 합니다.

- [/Od](../../build/reference/od-disable-debug.md) 컴파일 및 디버깅을 간소화 하려면 최적화를 사용할 수 있습니다.

- [/Og](../../build/reference/og-global-optimizations.md) 전역 최적화를 사용 합니다.

- [/Oi](../../build/reference/oi-generate-intrinsic-functions.md) 적절 한 함수 호출에 대 한 내장 함수를 생성 합니다.

- [/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) 컴파일러가 크기에 대 한 최적화 속도 최적화 보다 우선 합니다.

- [/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) (기본 설정) 컴파일러가 속도 최적화 크기에 대 한 최적화 보다 우선 합니다.

- [/Ox](../../build/reference/ox-full-optimization.md) 선택 하는 속도에 중점을 두어 최적화 기능 중 몇 가지 조합 옵션입니다. 하위 집합이 고 **/O2** 최적화 합니다.

- [/Oy](../../build/reference/oy-frame-pointer-omission.md) 빠르게 함수 호출에 대 한 호출 스택에서 프레임 포인터를 생성 하지 않습니다.

## <a name="remarks"></a>설명

여러 결합할 수 **/O** 단일 옵션 문으로 옵션입니다. 예를 들어 **/Odi** 동일 **/Od /Oi**합니다. 일부 옵션은 상호 배타적 이므로 함께 사용 하는 경우 컴파일러 오류가 발생 합니다. 개별 참조 **/O** 옵션을 참조 하십시오.

## <a name="see-also"></a>참고 항목

[컴파일러 옵션](../../build/reference/compiler-options.md)   
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)