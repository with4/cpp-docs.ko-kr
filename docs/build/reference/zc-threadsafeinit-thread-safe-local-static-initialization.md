---
title: "/Zc:threadSafeInit (스레드로부터 안전한 로컬 정적 초기화) | Microsoft Docs"
ms.custom: 
ms.date: 03/96/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- threadSafeInit
- /Zc:threadSafeInit
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- threadSafeInit
- Thread-safe Local Static Initialization
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: a0fc4b34-2cf0-45a7-a642-b8afc4ca19f2
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b0d44b807a244ea96a982dc2363f90beceb0806b
ms.sourcegitcommit: eeb2b5ad8d3d22514a7b9bd7d756511b69ae0ccf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2018
---
# <a name="zcthreadsafeinit-thread-safe-local-static-initialization"></a>/Zc:threadSafeInit (스레드로부터 안전한 로컬 정적 초기화)

**/Zc:threadSafeInit** 컴파일러 옵션 컴파일러가 스레드로부터 안전한 방식으로 수동 동기화를 사용할 필요가 없는 정적 로컬 (함수 범위) 변수를 초기화 합니다. 초기화만는 스레드로부터 안전 합니다. 여러 스레드의 정적 지역 변수를 수정 하 고 사용 하 여 여전히 수동으로 동기화 되어야 합니다. 이 옵션은 Visual Studio 2015부터 사용할 수 있습니다. Visual Studio는 기본적으로이 옵션이 활성화 됩니다.

## <a name="syntax"></a>구문

**/Zc:threadSafeInit**[`-`]

## <a name="remarks"></a>설명

표준 C + + 11에서 정적 행이 있는 블록 범위 변수 또는 스레드 저장 기간이 0-초기화 해야 다른 초기화를 수행 하기 전에. 초기화는 제어가 변수 선언을 통해 처음 전달 될 때 발생 합니다. 초기화 하는 동안 예외가 발생 하 고 변수가 초기화 되지 않은 것으로 간주 됩니다 초기화가 다시 시도 시간 컨트롤 다음 선언을 통해 전달 합니다. 컨트롤이 선언 초기화가 완료 된 동안 동시 실행 블록 초기화와 동시에 입력 합니다. 컨트롤 다시 초기화 하는 동안 선언 재귀적으로 입력 하는 경우 동작이 정의 되지 않습니다. 기본적으로 Visual Studio 2015부터 Visual Studio는 이러한 표준 동작을 구현 합니다. 이 동작을 설정 하 여 명시적으로 지정할 수 있습니다는 **/Zc:threadSafeInit** 컴파일러 옵션입니다.

**/Zc:threadSafeInit** 컴파일러 옵션은 기본적으로 합니다. [관대 한 /-](permissive-standards-conformance.md) 옵션이 적용 되지 않습니다 **/Zc:threadSafeInit**합니다.

스레드로부터 안전한 정적 지역 변수 초기화는 (UCRT)의 유니버설 C 런타임 라이브러리에 구현 된 코드를 사용 합니다. 에 UCRT를 방지 하거나 버전의 Visual Studio 2015 이전 Visual Studio의 스레드 안전 하지 않은 초기화 동작을 유지 하려면 사용 된 **/Zc:threadSafeInit-** 옵션입니다. 스레드로부터의 안전성 필요 하지 않습니다.를 알고 있는 경우이 옵션을 사용 하 여 정적 지역 선언 주위 약간 더 작은, 더 빠른 코드를 생성 합니다.

스레드로부터 안전한 정적 지역 변수는 스레드 로컬 저장소 (TLS) 정적 이미 초기화 되었는데 더 효율적인 실행을 내부적으로 사용 합니다. 이 기능의 구현 Windows Vista 이상의 운영 체제에서 Windows 운영 체제 지원 기능에 의존 합니다. Windows XP, Windows Server 2003, 및 이전 운영 체제 없으므로이 지원을 효율성 장점은 수행 하지 않습니다. 이러한 운영 체제 TLS 섹션 로드할 수 있는 수에 대 한 하한값 레이블에도. TLS를 초과 하 여 섹션도 충돌이 발생할 수 있습니다. 이 특히 이전 운영 체제에서 실행 해야 하는 코드에서에서 코드에 문제가 있는 경우 사용 하 여 **/Zc:threadSafeInit-** 스레드 안전 초기화 코드를 사용 하지 않도록 설정 하려면.

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. **구성을** 드롭다운 메뉴에서 선택 **모든 구성**합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 수정 된 **추가 옵션** 포함할 속성을 **/Zc:threadSafeInit** 또는 **/Zc:threadSafeInit-** 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고 항목

[컴파일러 옵션](../../build/reference/compiler-options.md)<br/>
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)<br/>
[/Zc(규칙)](../../build/reference/zc-conformance.md)<br/>
