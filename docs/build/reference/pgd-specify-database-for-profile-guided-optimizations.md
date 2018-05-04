---
title: /PGD (프로필 기반 최적화에 대 한 데이터베이스 지정) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
dev_langs:
- C++
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7685f99137a1b599a5f9020fac9e3cae4ba3bc3c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD(프로필 기반 최적화를 위한 데이터베이스 지정)

**/PGD 옵션을 사용 하는 사용 되지 않습니다.** Visual Studio 2015부터 선호는 [/GENPROFILE 또는 /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) 링커 옵션을 대신 합니다. 프로필 기반 최적화 프로세스에서 사용 하 여.pgd 파일의 이름을 지정 하려면이 옵션은 사용 됩니다.

## <a name="syntax"></a>구문

> **/PGD:**_filename_

## <a name="argument"></a>인수

*filename*<br/>
실행 중인 프로그램에 대 한 정보를 저장 하는 데 사용 되는.pgd 파일의 이름을 지정 합니다.

## <a name="remarks"></a>설명

사용 되지 않는 경우 [/ltcg: pginstrument](../../build/reference/ltcg-link-time-code-generation.md) 옵션을 사용 하 여 **/PGD** 기본값이 아닌 이름이 나.pgd 파일의 위치를 지정할 수 있습니다. 지정 하지 않으면 **/PGD**,.pgd 파일 기본 이름은 출력 파일 (.exe 또는.dll) 기본 이름은 동일 하 고 링크가 호출 되는 동일한 디렉터리에 생성 됩니다.

사용 되지 않는 경우 **/ltcg: pgoptimize** 옵션을 사용 하 여는 **/PGD** 최적화 된 이미지를 만드는 데 사용할.pgd 파일의 이름을 지정 하는 옵션입니다. *filename* 인수 일치 해야는 *filename* 에 지정 된 **/ltcg: pginstrument**합니다.

자세한 내용은 참조 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **최적화** 속성 페이지.

1. 수정 된 **프로필 기반 데이터베이스** 속성입니다. 선택 **확인** 변경 내용을 저장 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

1. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>을 참조하세요.

## <a name="see-also"></a>참고자료

[링커 옵션 설정](../../build/reference/setting-linker-options.md)<br/>
[링커 옵션](../../build/reference/linker-options.md)<br/>
