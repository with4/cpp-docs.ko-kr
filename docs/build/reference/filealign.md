---
title: "/ FILEALIGN (파일의 섹션 맞춤) | Microsoft Docs"
ms.date: 10/23/2017
ms.technology: cpp-tools
ms.topic: article
f1_keywords: /filealign
dev_langs: C++
helpviewer_keywords:
- linker align sections
- /FILEALIGN linker option
- -FILEALIGN linker option
- FILEALIGN linker option
ms.assetid: c1017a35-8d71-4ad9-934b-a3e3ea037fa0
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 753f6c5fade4211654246aec19af60c60706d7ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="filealign-align-sections-in-files"></a>/ FILEALIGN (파일의 섹션 맞춤)

**/FILEALIGN** 링커 옵션을 사용 하면 지정 된 크기의 배수도 출력 파일에 기록 하는 섹션의 맞춤을 지정 합니다.

## <a name="syntax"></a>구문

> __/ FILEALIGN:__*크기*

### <a name="parameters"></a>매개 변수

*size*  
섹션 맞춤 크기 바이트, 2의 거듭제곱 이어야 합니다.

## <a name="remarks"></a>설명

**/FILEALIGN** 의 배수인 경계에 출력 파일의 각 섹션에 맞게 링커 옵션을 사용 하면는 *크기* 값입니다. 기본적으로 링커는 고정 된 맞춤 크기를 사용 하지 않습니다.

**/FILEALIGN** 디스크 사용률을 더욱 효율적으로 지정 하려면 옵션을 사용할 수 있습니다 또는 페이지를 디스크에서 더 빠르게 로드할 수 있습니다. 더 작은 섹션 크기 다운로드가 더 작게 유지 하거나 소형 장치에서 실행 되는 앱에 대 한 유용할 수 있습니다. 섹션 맞춤 디스크에 메모리에서 맞춤의 영향을 주지 않습니다.

출력 파일의 섹션에 대한 정보를 확인하려면 [DUMPBIN](dumpbin-reference.md)을 사용하세요.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **명령줄** 속성 페이지에는 **링커** 폴더입니다.

1. 옵션 이름 입력 **/FILEALIGN:** 의 크기와는 **추가 옵션** 상자입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[링커 옵션 설정](../../build/reference/setting-linker-options.md)   
[링커 옵션](../../build/reference/linker-options.md)