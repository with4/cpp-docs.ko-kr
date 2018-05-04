---
title: 컴파일러 및 링커에서의 유니코드 지원 | Microsoft Docs
ms.custom: ''
ms.date: 12/15/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
dev_langs:
- C++
helpviewer_keywords:
- Unicode, Visual C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec0b84cd62f3fcca378ab55de16006925e685b37
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>컴파일러 및 링커에서의 유니코드 지원

대부분의 Visual c + + 빌드 도구 유니코드 입 / 출력을 지원합니다.

## <a name="filenames"></a>파일 이름

명령줄에서 또는 컴파일러 지시문에 지정 된 파일 이름 (예: `#include`) 유니코드 문자를 포함할 수 있습니다.

## <a name="source-code-files"></a>소스 코드 파일

유니코드 문자는 식별자, 매크로, 문자열 및 문자 리터럴, 한 주석에서 지원 됩니다.  유니버설 문자 이름 에서도 지원 됩니다.

다음 인코딩에서는 소스 코드 파일에 유니코드를 입력할 수 있습니다.

- U t F-16 little endian 바이트 순서 표시 (BOM) 유무

- Utf-16 big endian BOM 유무

- U t F-8 bom

## <a name="output"></a>출력

컴파일하는 동안 컴파일러 진단 u t F-16으로 콘솔에 출력합니다.  콘솔에 표시 될 수 있는 문자는 콘솔 창 속성에 따라 달라 집니다.  컴파일러 출력을 파일로 리디렉션되의 현재 ANSI 콘솔 코드 페이지가 있는 경우

## <a name="linker-response-files-and-def-files"></a>링커 지시 파일 및 합니다. DEF 파일

응답 파일 및 DEF 파일 BOM 또는 ANSI 중 하나가 u t F-16을 수 있습니다.

## <a name="asm-and-cod-dumps"></a>.asm 및.cod 덤프

.asm 및.cod 덤프 MASM 호환을 위해 기본적으로 ansi에서 됩니다. 사용 하 여 [/FAu](../../build/reference/fa-fa-listing-file.md) u t F-8을 출력 합니다. 지정 하는 경우 유의 **/FAs**, 소스가 직접 인쇄 됩니다 및 보일 수 있습니다, 예를 들어 소스 코드는 u t F-8을 지정 하지 않은 경우 **/FAsu**합니다.

## <a name="see-also"></a>참고자료

[명령줄에서 C/C++ 코드 빌드](../../build/building-on-the-command-line.md)