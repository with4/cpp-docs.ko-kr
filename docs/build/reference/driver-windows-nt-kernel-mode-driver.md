---
title: -드라이버 (Windows NT 커널 모드 드라이버) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.driver
- /driver
dev_langs:
- C++
helpviewer_keywords:
- kernel mode driver
- -DRIVER linker option
- DRIVER linker option
- /DRIVER linker option
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 29234e3c0e368c7710f9071c753422bc4e6ef2b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="driver-windows-nt-kernel-mode-driver"></a>/DRIVER(Windows NT 커널 모드 드라이버)

>/ 드라이버 [: UPONLY |: WDM]

## <a name="remarks"></a>설명

사용 하 여는 **/DRIVER** 링커 옵션을 Windows NT 커널 모드 드라이버를 작성 합니다.

**/DRIVER:UPONLY** 링커가 추가 하는 **IMAGE_FILE_UP_SYSTEM_ONLY** 비트를 단일 프로세서 (업) 드라이버 임을 지정 하려면 출력 헤더의 특성입니다. 운영 체제에서는 UP 드라이버 다중 프로세서 시스템 MP ()를 로드 하지 합니다.

**/Driver: wdm** 링커가 설정 하는 **IMAGE_DLLCHARACTERISTICS_WDM_DRIVER** 선택적 헤더의 DllCharacteristics 필드에 비트입니다.

경우 **/DRIVER** 를 지정 하지 않으면 이러한 비트 링커에 의해 설정 되지 않습니다.

경우 **/DRIVER** 지정 됩니다.

- **/Fixed: no** 적용 됩니다. 자세한 내용은 [/FIXED(고정 기준 주소)](../../build/reference/fixed-fixed-base-address.md)를 참조하세요.

- 출력 파일의 확장명.sys로 설정 됩니다. 사용 하 여 **/out** 기본 파일 이름 및 확장명을 변경할 수 있습니다. 자세한 내용은 [/OUT(출력 파일 이름)](../../build/reference/out-output-file-name.md)을 참조하세요.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.

1. 클릭는 **링커** 폴더입니다.

1. 클릭는 **시스템** 속성 페이지.

1. 수정 된 **드라이버** 속성입니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- 참조 [VCLinkerTool.driver 속성](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.driver?view=visualstudiosdk-2017#Microsoft_VisualStudio_VCProjectEngine_VCLinkerTool_driver)합니다.

## <a name="see-also"></a>참고 항목

[링커 옵션 설정](../../build/reference/setting-linker-options.md)   
[링커 옵션](../../build/reference/linker-options.md)
