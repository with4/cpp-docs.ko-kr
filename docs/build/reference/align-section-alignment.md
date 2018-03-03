---
title: "/ALIGN (섹션 맞춤) | Microsoft Docs"
ms.custom: 
ms.date: 12/29/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
dev_langs:
- C++
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ca4572e84c7ad32be2d03a312f7bb7d8a3f3f29
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="align-section-alignment"></a>/ALIGN(섹션 맞춤)

## <a name="syntax"></a>구문

> **/ALIGN**[**:**_번호_]

### <a name="arguments"></a>인수

*번호*  
바이트 맞춤 값입니다.

## <a name="remarks"></a>설명

**/align** 옵션은 프로그램의 선형 주소 공간 내에서 각 섹션의 맞춤을 지정 합니다. *번호* 인수는 바이트 단위 이며 2의 거듭제곱 이어야 합니다. 기본값은 4k (4096). 링커에서 맞춤 잘못 된 이미지를 생성 합니다. 경고를 표시 합니다.

장치 드라이버 등의 응용 프로그램을 작성 하는 경우가 맞춤을 수정할 필요는 없습니다.

맞춤 매개 변수를 사용 하는 특정 섹션의 맞춤을 수정할 수는 [/section](../../build/reference/section-specify-section-attributes.md) 옵션입니다.

지정 된 맞춤 값의 가장 큰 섹션 맞춤 보다 작을 수 없습니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 에 옵션을 입력에서 **추가 옵션** 상자입니다. 선택 **확인** 또는 **적용** 에 변경 내용을 적용 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[링커 옵션 설정](../../build/reference/setting-linker-options.md)  
[링커 옵션](../../build/reference/linker-options.md)  
