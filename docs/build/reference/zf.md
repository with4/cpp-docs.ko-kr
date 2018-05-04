---
title: /Zf (더 빠르게 PDB 생성) | Microsoft Docs
ms.date: 03/29/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zf
dev_langs:
- C++
helpviewer_keywords:
- /Zf
- -Zf
author: corob-msft
ms.author: corob
ms.openlocfilehash: 968ce17302fa608888c7ae2fedf695946b0119bd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="zf-faster-pdb-generation"></a>/Zf (더 빠르게 PDB 생성)

Mspdbsrv.exe에 대 한 RPC 호출을 최소화 하 여 병렬 빌드에서 더 빠른 PDB 생성을 사용 합니다.

## <a name="syntax"></a>구문

> **/Zf**

## <a name="remarks"></a>설명

**/Zf** 옵션을 사용 하는 경우 더 빠른 생성 PDB 파일에 대 한 컴파일러 지원 사용 하면는 [/MP (여러 프로세스로 빌드)](mp-build-with-multiple-processes.md) 옵션을 경우 또는 빌드 시스템 (예를 들어 [MSBuild ](/visualstudio/msbuild/msbuild-reference) 또는 [CMake](../../ide/cmake-tools-for-visual-cpp.md)) 동시에 여러 cl.exe 컴파일러 프로세스 실행 될 수 있습니다. 이 옵션 컴파일, 끝날 때까지 PDB 파일의 각 형식 레코드에 대 한 형식 인덱스의 생성을 지연 시킬 컴파일러 프런트 엔드 사용 하면 다음 모두 각 레코드에 대 한 RPC 요청을 만드는 대신 mspdbsrv.exe 한 번 RPC 호출에에서이 요청 합니다. Mspdbsrv.exe 프로세스 여러 cl.exe 컴파일러 프로세스가 동시에 실행 하는 환경에 대 한 RPC 부하를 줄여 빌드 처리량을 크게 높일 수 있습니다이 합니다.

때문에 **/Zf** 필요 옵션 PDB 생성에만 적용 됩니다는 [/Zi](z7-zi-zi-debug-information-format.md) 또는 [/ZI](z7-zi-zi-debug-information-format.md) 옵션입니다.

**/Zf** 옵션은 기본적으로 해제 되어 있는 Visual Studio 2017 15.1, 버전부터 사용할 수 있습니다. Visual Studio 2017 15.7 버전부터 미리 보기 3,이 옵션이 기본적으로 켜져 때는 **/Zi** 또는 **/ZI** 옵션을 사용할 수 있습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 수정 된 **추가 옵션** 포함할 속성을 **/Zf** 선택한 후 **확인**합니다.

## <a name="see-also"></a>참고자료

[컴파일러 옵션 사전순 목록](compiler-options-listed-alphabetically.md)<br/>
[/MP(여러 프로세스로 빌드)](mp-build-with-multiple-processes.md)<br/>
