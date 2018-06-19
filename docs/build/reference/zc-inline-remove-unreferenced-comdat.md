---
title: '/Zc: inline (참조 되지 않은 COMDAT 제거) | Microsoft Docs'
ms.custom: ''
ms.date: 03/01/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:inline
- VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData
dev_langs:
- C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
- /Zc:inline
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 067ba5dad4e0751a86835ea56c536a5b7250485d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379590"
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline(참조되지 않은 COMDAT 제거)

COMDAT이거나 내부 링크만 있는 참조되지 않은 함수 또는 데이터를 제거합니다. 때 **/zc: inline** 지정, 컴파일러에 인라인 데이터 또는 인라인 함수를 사용 하는 변환 단위 데이터 또는 함수에 대 한 정의 포함 해야 필요 합니다.

## <a name="syntax"></a>구문

> **/Zc:inline**[**-**]

## <a name="remarks"></a>설명

때 **/zc: inline** 지정, 컴파일러 참조 되지 않은 COMDAT 함수 또는 데이터 나 내부 링크만 있는 데이터 또는 함수에 대 한 기호 정보를 내보내지 않습니다. 이 최적화 간소화 릴리스 빌드에서 링커에 의해 수행 된 작업의 경우 또는 링커 옵션 [/opt: ref](../../build/reference/opt-optimizations.md) 지정 됩니다. 컴파일러가 이러한 최적화를 수행하면 .obj f파일의 크기를 크게 줄이고 링커 속도를 상당히 높일 수 있습니다. 이 컴파일러 옵션에는 최적화가 해제 된 경우 사용 되지 않습니다 ([/Od](../../build/reference/od-disable-debug.md)) 되거나 [/GL (전체 프로그램 최적화)](../../build/reference/gl-whole-program-optimization.md) 지정 됩니다.

이 옵션은 기본적으로 꺼져 (**/Zc:inline-**). [관대 한 /-](permissive-standards-conformance.md) 옵션을 사용 하지 않는 **/zc: inline**합니다.

경우 **/zc: inline** 경우 컴파일러는 C + + 11 요구 사항을 선언한 모든 함수는 지정 된 `inline` 사용 하는 경우 동일한 변환 단위에서 사용할 수 있는 정의가 있어야 합니다. Microsoft 컴파일러는 선언한 함수를 호출 하는 비호환 코드 허용 옵션을 지정 하지 않으면 때 `inline` 표시 되는 정의가 있는 경우에 합니다. 자세한 내용은 섹션 3.2 및 7.1.2에서 C++11 표준을 참조하세요. 이 컴파일러 옵션은 Visual Studio 2013 업데이트 2에서 정의되었습니다.

사용 하 여 **/zc: inline** 옵션, 호환 되지 않는 코드를 업데이트 합니다.

어떻게 정의 없이 인라인 함수 선언의 호환 되지 않는 사용 여전히를 컴파일하고 연결 하는 경우를 보여 주는이 예제는 기본 **/Zc:inline-** 옵션을 사용 합니다.

```cpp
// example.h
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#pragma once

class Example {
public:
   inline void inline_call(); // declared but not defined inline
   void normal_call();
   Example() {};
};
```

```cpp
// example.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#include <stdio.h>
#include "example.h"

void Example::inline_call() {
   printf("inline_call was called.\n"); 
}

void Example::normal_call() {
   printf("normal_call was called.\n"); 
   inline_call(); // with /Zc:inline-, inline_call forced into .obj file
}
```

```cpp
// zcinline.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp
#include "example.h"

void main() {
   Example example;
   example.inline_call(); // normal call when definition unavailable
}
```

때 **/zc: inline** 를 사용 하는 원인이 동일한 코드는 [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) 오류를 컴파일러에 대 한 인라인-처리 된 코드 본문을 생성 하지 않도록 하기 때문에 `Example::inline_call` example.obj에 있습니다. 따라서 `main`에서 인라인되지 않은 호출이 발생해 정의되지 않은 외부 기호를 참조하게 됩니다.

이러한 오류를 해결하기 위해 `inline` 선언에서 `Example::inline_call` 키워드를 제거하거나 `Example::inline_call`의 정의를 헤더 파일로 이동하거나 `Example`의 구현을 main.cpp로 이동할 수 있습니다. 다음 예제에서는 헤더를 포함한 모든 호출자에게 정의가 표시되는 헤더 파일로 정의를 이동합니다.

```cpp
// example2.h
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#pragma once
#include <stdio.h>

class Example2 {
public:
   inline void inline_call() {
      printf("inline_call was called.\n"); 
   }
   void normal_call();
   Example2() {};
};
```

```cpp
// example2.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#include "example2.h"

void Example2::normal_call() {
   printf("normal_call was called.\n"); 
   inline_call(); 
}
```

```cpp
// zcinline2.cpp
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp
#include "example2.h"

void main() {
   Example2 example2;
   example2.inline_call(); // normal call when definition unavailable
}
```

Visual C++의 규칙과 관련된 문제에 대한 자세한 내용은 [Nonstandard Behavior](../../cpp/nonstandard-behavior.md)을 참조하세요.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **언어** 속성 페이지.

1. 수정 된 **참조 되지 않은 코드 및 데이터를 제거** 속성을 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[/Zc(규칙)](../../build/reference/zc-conformance.md)<br/>
