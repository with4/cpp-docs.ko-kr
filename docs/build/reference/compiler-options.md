---
title: 컴파일러 옵션 | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler
- x86 Visual C++ compiler
- ARM Visual C++ compiler
- compiler options, C++
- x64 Visual C++ compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bea07361a292ee5e7cde99cedad2d5ac4c8a53aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="compiler-options"></a>컴파일러 옵션

cl.exe는 Microsoft Visual c + + (MSVC) C 및 c + + 컴파일러 및 링커를 제어 하는 도구입니다. cl.exe 기간을 지 원하는 Microsoft Visual Studio에 대 한 운영 체제에만 실행할 수 있습니다.

> [!NOTE]  
> Visual Studio 개발자 명령 프롬프트 에서만에서이 도구를 시작할 수 있습니다. 시스템 명령 프롬프트 또는 파일 탐색기에서는 시작할 수 없습니다. 자세한 내용은 참조 [명령줄에서 빌드 C/c + + 코드](../building-on-the-command-line.md)합니다.

컴파일러는 파일 형식은 COFF (공용 개체) 개체 (.obj) 파일을 생성합니다. 링커는 실행 파일 (.exe) 파일 또는 동적 연결 라이브러리 (Dll)를 생성 합니다.

모든 컴파일러 옵션은 대/소문자 구분을 참고 합니다. 어느 슬래시를 사용할 수 있습니다 (`/`) 또는 대시 (`-`) 컴파일러 옵션을 지정할 수 있습니다.

링크 하지 않고 컴파일하려면를 사용 하 여는 [/c](../../build/reference/c-compile-without-linking.md) 옵션입니다.

## <a name="find-a-compiler-option"></a>컴파일러 옵션

특정 컴파일러 옵션을 보려면, 다음 목록 중 하나를 참조 합니다.

- [컴파일러 옵션 사전순 목록](../../build/reference/compiler-options-listed-alphabetically.md)

- [컴파일러 옵션 범주별 목록](../../build/reference/compiler-options-listed-by-category.md)

## <a name="specify-compiler-options"></a>컴파일러 옵션을 지정 합니다.

각 컴파일러 옵션에 대 한 알아봅니다 방법을 개발 환경에서 설정할 수 있습니다. 개발 환경 외부에서 옵션을 지정 하는 내용은 다음을 참조 하십시오.

- [컴파일러 명령줄 구문](../../build/reference/compiler-command-line-syntax.md)

- [CL 명령 파일](../../build/reference/cl-command-files.md)

- [CL 환경 변수](../../build/reference/cl-environment-variables.md)

## <a name="related-build-tools"></a>관련된 빌드 도구

[링커 옵션](../../build/reference/linker-options.md) 프로그램 빌드 방법을 영향을 줍니다.

## <a name="see-also"></a>참고자료

[C/C++ 빌드 참조](../../build/reference/c-cpp-building-reference.md)  
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)  
[컴파일 속도 향상](../../build/reference/fast-compilation.md)  
[CL에서의 링커 호출](../../build/reference/cl-invokes-the-linker.md)  
