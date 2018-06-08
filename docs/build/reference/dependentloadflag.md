---
title: / DEPENDENTLOADFLAG (기본 종속 부하 플래그를 설정)
description: /DEPENDENTLOADFLAG 옵션 LoadLibrary를 사용 하 여 로드 된 Dll에 대 한 기본 플래그를 설정 합니다.
ms.custom: ''
ms.date: 05/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- dependentloadflag
dev_langs:
- C++
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a171f3c2edbbbf614a986ff78dd2405e734a1d1
ms.sourcegitcommit: d1f576a0f59678edc3d93508cf46485138332178
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753716"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/ DEPENDENTLOADFLAG (기본 종속 부하 플래그를 설정)

때에 사용 되는 기본 부하 플래그 설정 `LoadLibrary` Dll을 로드 하는 데 사용 됩니다.

## <a name="syntax"></a>구문

> **/ DEPENDENTLOADFLAG**[**:**_loadflags_]

### <a name="arguments"></a>인수

|||
|-|-|
*loadflags*|선택적 "C" 스타일 16 비트 정수 값 10 진수, 8 진수 앞에 0, 또는 시작 하는 16 진수 `0x`, 모든 적용 하려면 종속 부하 플래그를 지정 하는 [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187) 호출 합니다. 기본값은 0입니다.

## <a name="remarks"></a>설명

이 옵션은 Visual Studio 2017 년의 새로운 기능 및 Windows 10 RS1 및 이후 버전에서 실행 되는 앱에만 적용 됩니다. 이 옵션은 응용 프로그램을 실행 하는 다른 운영 체제에서 무시 됩니다.

지원 되는 운영 체제에서이 옵션은 변경에 대 한 호출의 효과가 `LoadLibrary("dependent.dll")` 에 해당 하는 `LoadLibraryEx("dependent.dll", 0, loadflags)`합니다. 에 대 한 호출이 [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091) 영향을 받지 않습니다. 이 옵션에는 응용 프로그램에 의해 로드 된 Dll에 재귀적으로 적용 되지 않습니다.

공격 효과 얻습니다 DLL을 방지 하기 위해이 플래그를 사용할 수 있습니다. 예를 들어, 앱에서 사용 하는 경우 `LoadLibrary` 종속 DLL을 로드 하려면 공격자 수 공장 동일한 이름 가진 DLL에서 사용 하는 검색 경로에 `LoadLibrary`는 현재 디렉터리와 같이 확인 될 수 있습니다 시스템 디렉터리 전에 안전 DLL 검색 모드가 사용 되는 경우 사용할 수 없습니다. 안전 DLL 검색 모드 검색 순서로 나중에 사용자의 현재 디렉터리에 배치 하 고 Windows XP SP2 이상 버전에서 기본적으로 사용 됩니다. 자세한 내용은 참조 [동적 연결 라이브러리 검색 순서](https://msdn.microsoft.com/library/windows/desktop/ms682586.aspx)합니다.

연결 옵션을 지정 하는 경우 `/DEPENDENTLOADFLAG:0xA00` (결합 된 플래그의 값 `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`), DLL 검색 경로 공격자에 대 한 더 어려운 보호 된 디렉터리에 제한 된 사용자의 컴퓨터에 안전 하 게 보호 DLL 검색 모드가 해제 되는 경우에 변경 합니다. 사용 가능한 플래그에 대 한 정보 및 해당 기호 및 숫자 값에 대 한 참조는 *dwFlags* 에 매개 변수 설명을 [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091)합니다.

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 DEPENDENTLOADFLAG 링커 옵션을 설정 하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 에 옵션을 입력 **추가 옵션**합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

- [링커 옵션 설정](setting-linker-options.md)
- [링커 옵션](linker-options.md)
- [암시적으로 DLL에 연결 하는 방법](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [사용할 연결 방법을 결정 합니다.](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187)
- [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091)
- [동적 연결 라이브러리 검색 순서](https://msdn.microsoft.com/library/windows/desktop/ms682586.aspx)
