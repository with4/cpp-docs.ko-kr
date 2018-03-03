---
title: "/SECTION (섹션 특성 지정) | Microsoft Docs"
ms.custom: 
ms.date: 12/29/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /section
dev_langs:
- C++
helpviewer_keywords:
- SECTION linker option
- -SECTION linker option
- section attributes
- /SECTION linker option
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aa214c7efeeee595300204df900a333258052772
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="section-specify-section-attributes"></a>/SECTION(섹션 특성 지정)

> **/SECTION:**_이름_, [[**!**] {**DEKPRSW**}] [**, ALIGN =**_번호_]

## <a name="remarks"></a>설명

**/section** 옵션 섹션에 대 한.obj 파일을 컴파일할 때 설정한 특성을 재정의 하 여 섹션의 특성을 변경 합니다.

A *섹션* 이식 가능한 실행 (PE)에서 파일은 코드 또는 데이터를 포함 하는 메모리의 명명 된 연속 블록입니다. 일부 섹션 코드나 프로그램 선언 하 고 다른 데이터 섹션 링커 및 라이브러리 관리자 (lib.exe)가 만들어집니다 및 운영 체제에 중요 한 정보를 포함 하는 동안를 직접 사용 하는 데이터를 포함 합니다. 자세한 내용은 참조 [PE 형식](https://msdn.microsoft.com/library/windows/desktop/ms680547)합니다.

콜론 (:) 및 섹션 지정 *이름*합니다. *이름* 대 소문자를 구분 합니다.

충돌 하 여 표준 이름으로 다음 이름을 사용 하지 마십시오. 예를 들어.sdata RISC 플랫폼에서 사용 됩니다.

- .arch

- .bss

- .data

- .edata

- .idata

- .pdata

- .rdata

- .reloc

- .rsrc

- .sbss

- .sdata

- .srdata

- .text

- .xdata

섹션에 대 한 하나 이상의 특성을 지정 합니다. 아래에 나열 된 특성 문자는 대/소문자 구분 되지 않습니다. 섹션에; 원하는 모든 특성을 지정 해야 합니다. 특성 문자를 생략된 하면 해당 특성 비트가 설정을 해제 해야 합니다. R, W, 또는 E, 기존의 읽기, 쓰기를 지정 하지 않은 경우 실행 상태가 변경 되지 않습니다.

특성을 부정 하 느낌표 (!)와 함께 해당 문자 앞에 야 합니다. 특성 문자의 의미는이 테이블에 나와 있습니다.

|문자|특성|의미|
|---------------|---------------|-------------|
|E|실행|섹션을 실행할 수 있습니다.|
|R|읽기|데이터에서 읽을 수 있습니다.|
|W|Write|데이터에 쓸 수 있습니다.|
|S|공유|이미지를 로드 하는 모든 프로세스에서 섹션을 공유 합니다.|
|D|삭제 가능한|섹션을 삭제할 수 있는 것으로 표시|
|K|캐시할 수|섹션 불가능으로 표시합니다.|
|P|페이징 가능한|섹션을 페이징할 수 없는 것으로 표시합니다.|

K 및 P 부정적인 의미에 해당 하는 섹션 플래그를 사용 하는 한다는 점에서 일반적인 하지 않습니다. 지정 하면 둘 중 하나는.text 섹션에 맞춰져 있으며를 사용 하는 **/SECTION:.text, K** 옵션을 실행 하면 섹션 플래그에서의 차이가 없습니다 [DUMPBIN](../../build/reference/dumpbin-options.md) 와 [/HEADERS](../../build/reference/headers.md)옵션도 있습니다. 섹션은 암시적으로 이미 캐시 되었습니다. 기본값을 제거 하려면 지정 **/SECTION:.text,! K** 대신 합니다. DUMPBIN 섹션 특성을 "캐시 되지 않습니다."를 포함 하 여를 보여 줍니다.

E, R, 또는 W 설정 되지 않은 PE 파일의 섹션은 유효 하지 않습니다.

**ALIGN =**_번호_ 인수를 사용 하면 특정 섹션에 대 한 맞춤 값을 지정할 수 있습니다. _번호_ 인수는 바이트 단위 이며 2의 거듭제곱 이어야 합니다. 참조 [/align](../../build/reference/align-section-alignment.md) 자세한 정보에 대 한 합니다.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면

1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **링커** > **명령줄** 속성 페이지.

1. 에 옵션을 입력에서 **추가 옵션** 상자입니다. 선택 **확인** 또는 **적용** 에 변경 내용을 적용 합니다.

### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[링커 옵션 설정](../../build/reference/setting-linker-options.md)  
[링커 옵션](../../build/reference/linker-options.md)  
