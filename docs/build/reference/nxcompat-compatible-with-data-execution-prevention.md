---
title: /NXCOMPAT (데이터 실행 방지 기능과 호환) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /NXCOMPAT
dev_langs:
- C++
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb4f8a91545a196bc92fdc0ec44e89a7d5680185
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT(데이터 실행 방지 기능과 호환)

실행 파일이 Windows 데이터 실행 방지 기능과 호환 임을 나타냅니다.

## <a name="syntax"></a>구문

> **/NXCOMPAT**[**: NO**]

## <a name="remarks"></a>설명

기본적으로 **/NXCOMPAT** 켜져 있습니다.

**/Nxcompat: no** 명시적으로 데이터 실행 방지와 호환 되지 않는 실행 파일을 지정할 데 사용할 수 있습니다.

데이터 실행 방지에 대 한 자세한 내용은 다음이 문서를 참조 합니다.

- [데이터 실행 방지 (DEP) 기능에 대 한 자세한 설명](http://go.microsoft.com/fwlink/p/?linkid=157771)

- [데이터 실행 방지](http://go.microsoft.com/fwlink/p/?linkid=157770)

- [데이터 실행 방지 (포함 된 Windows)](http://go.microsoft.com/fwlink/p/?linkid=157768)

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio에서 이 링커 옵션을 설정하려면

1. 프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 에 옵션을 입력에서 **추가 옵션** 상자입니다. 선택 **확인** 또는 **적용** 에 변경 내용을 적용 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[링커 옵션 설정](../../build/reference/setting-linker-options.md)  
[링커 옵션](../../build/reference/linker-options.md)  
