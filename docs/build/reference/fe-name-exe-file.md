---
title: -Fe (EXE 파일 이름) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fe
dev_langs:
- C++
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0afd8a863c9b8482e2b7f3868047845818bd2923
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377059"
---
# <a name="fe-name-exe-file"></a>/Fe(EXE 파일 이름 지정)

이름 및.exe 파일 또는 컴파일러에서 만든 DLL에 대 한 디렉터리를 지정 합니다.

## <a name="syntax"></a>구문

> **/Fe**[_pathname_]  
> **/ Fe:** _경로 이름_  

### <a name="arguments"></a>인수

*pathname*<br/>
상대 또는 절대 경로 및 기본 파일 이름 또는 상대 또는 절대 경로 디렉터리 또는 생성된 된 실행 파일에 사용할 기본 파일 이름입니다.

## <a name="remarks"></a>설명

**/Fe** 옵션을 사용 하면 출력 디렉터리, 출력 실행 파일 이름 또는 생성 된 실행 파일에 대 한 둘 다 지정할 수 있습니다. 경우 *pathname* 경로 구분 기호에 종료 (**&#92;**)만 출력 디렉터리를 지정 하는로 간주 됩니다. 그렇지 않은 경우의 마지막 구성 요소 *pathname* 출력 파일 기본 이름 및의 나머지 부분으로 사용 *pathname* 출력 디렉터리를 지정 합니다. 경우 *pathname* 경로 구분 기호를 없는 현재 디렉터리에 출력 파일 이름을 지정 하는로 간주 됩니다. *pathname* 큰따옴표로 묶어야 합니다 (**"**) 예: 공백, 짧은 경로에 사용할 수 없는 모든 문자가 포함 된 경우 확장 문자 또는 경로 구성 요소 8 자 보다 긴 시간입니다.

경우는 **/Fe** 옵션을 지정 하지 않으면 또는에 기본 파일 이름을 지정 하지 않으면 *pathname*, 컴파일러에서는 출력 파일이 지정 된 첫 번째 소스 또는 개체 파일의 기본 이름을 사용 하 여 기본 이름 명령줄 및 확장명이.exe 또는.dll

지정 하는 경우는 [(컴파일 없이 링크 사용) /c](c-compile-without-linking.md) 옵션을 **/Fe** 영향을 주지 않습니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 열기는 **구성 속성** > **링커** > **일반** 속성 페이지.

1. 수정 된 **출력 파일** 속성입니다. 선택 **확인** 변경 내용을 저장 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>을 참조하세요.

## <a name="example"></a>예제

다음 명령줄을 컴파일하고 현재 디렉터리의 모든 C 소스 파일을 연결 합니다. 결과 실행 파일 PROCESS.exe 라고 하 고 "C:\Users\User Name\repos\My Project\bin" 디렉터리에 만들어집니다.

```
CL /Fe"C:\Users\User Name\repos\My Project\bin\PROCESS" *.C
```

## <a name="example"></a>예제

다음 명령줄의 실행 파일을 만듭니다 `C:\BIN` 현재 디렉터리에 첫 번째 소스 파일과 동일한 기본 이름을 가진:

```
CL /FeC:\BIN\ *.C
```

## <a name="see-also"></a>참고자료

[출력 파일(/F) 옵션](../../build/reference/output-file-f-options.md)<br/>
[컴파일러 옵션](../../build/reference/compiler-options.md)<br/>
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)<br/>
[경로 이름 지정](../../build/reference/specifying-the-pathname.md)<br/>
