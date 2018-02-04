---
title: "-Yl (디버그 라이브러리에 PCH 참조 넣기) | Microsoft Docs"
ms.custom: 
ms.date: 01/29/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /yl
dev_langs:
- C++
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 43e960906c504e5378a77d047c8eb1ab4d4594fe
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/03/2018
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl(디버그 라이브러리에 PCH 참조 넣기)

**/Yl** 옵션은 미리 컴파일된 헤더 파일에 고유한 기호를 생성 하 고이 기호에 대 한 참조는 미리 컴파일된 헤더를 사용 하는 모든 개체 파일에 주입 합니다.

## <a name="syntax"></a>구문

>**/Yl**  
>**/Yl**_name_  
>**/Yl-**  

### <a name="arguments"></a>인수

*name*  
고유한 기호의 일환으로 사용 하는 선택적 이름입니다.

*\-*  
대시 (-) 명시적으로 비활성화 된 **/Yl** 컴파일러 옵션입니다.

## <a name="remarks"></a>설명

**/Yl** 사용 하 여 만든 미리 컴파일된 헤더 파일에 고유한 기호 정의 생성 하는 컴파일러 옵션은 [/Yc](../../build/reference/yc-create-precompiled-header-file.md) 옵션입니다. 이 기호에 대 한 참조는 자동으로 사용 하 여 미리 컴파일된 헤더를 포함 하는 모든 파일에 지정 된 된 [/Yu](../../build/reference/yu-use-precompiled-header-file.md) 컴파일러 옵션입니다. **/Yl** 옵션은 기본적으로 때 **/Yc** 미리 컴파일된 헤더 파일을 만드는 데 사용 됩니다.

**/Yl**_이름_ 옵션이 미리 컴파일된 헤더 파일에서 식별이 가능한 기호를 만드는 데 사용 됩니다. 컴파일러가 사용 하는 *이름* 생성, 비슷합니다 데코레이팅된 기호 이름의 일부로 인수 \_ \_ @@ \_PchSym\_@00@... @ *이름*, 고유한 컴파일러에서 생성 된 줄임표 (...) 나타내는 문자열입니다. 경우는 *이름* 인수를 생략 하면, 컴파일러에서 자동으로 기호 이름을 생성 합니다. 일반적으로 기호 이름을 알 필요가 없습니다. 그러나 프로젝트에 사용 하는 경우 둘 이상의 미리 컴파일된 헤더 파일의 **/Yl**_이름_ 옵션 개체가 미리 컴파일된 헤더를 사용 하 여 파일을 확인 하는 데 유용할 수 있습니다. 사용할 수 있습니다 *이름* 검색 문자열로 덤프 파일에 기호 파일에 대 한 참조를 찾을 수 있습니다.

**/Yl-** 기본 동작을 비활성화 하 고 미리 컴파일된 헤더 파일에서 식별 기호를 넣지 않습니다. 이 미리 컴파일된 헤더를 포함 하는 컴파일된 파일에서 공용 기호 참조를 얻지 못합니다.

때 **/Yc** 를 지정 하지 않으면 모든 **/Yl** 옵션은 모든 일치 해야 하는 경우 지정 하지만 효과가 없습니다 **/Yl** 옵션 경우 전달 된 **/Yc** 은 지정 합니다.

사용 하는 경우 **/Yl-**, **/Yc** 및 [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md) 디버깅 정보가 미리 컴파일된 헤더 파일을 작성 하는 옵션을 만드는 데 소스 파일에 대 한 개체 파일에 저장 됩니다는 미리 컴파일된 헤더를 별도.pdb 파일이 아닌 합니다. 이 개체 파일을 라이브러리의 일부 완료 되 면 경우 [LNK1211](../../error-messages/tool-errors/linker-tools-error-lnk1211.md) 오류 또는 [LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md) 소스 파일을 만드는 데 사용 하는 경우이 라이브러리 및 미리 컴파일된 헤더 파일을 사용 하는 빌드에 경고가 발생할 수 있습니다는 미리 컴파일된 헤더 파일 정의 하지 않습니다 모든 기호 자체. 링커는 라이브러리 클라이언트에서 참조 될 개체 파일의 경우 nothing 때 연관 된 디버깅 정보를 함께 링크에서 개체 파일을 제외 될 수 있습니다. 이 문제를 해결 하려면 지정 **/Yl** (또는 제거는 **/Yl-** 옵션) 사용 하는 경우 **/Yc** 미리 컴파일된 헤더 파일을 만들 수 있습니다. 이렇게 하면 디버깅 정보가 포함 된 라이브러리의 개체 파일 빌드에 연결을 가져옵니다.

미리 컴파일된 헤더에 대 한 자세한 내용은 다음을 참조 하세요.

- [/Y(미리 컴파일된 헤더)](../../build/reference/y-precompiled-headers.md)

- [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **구성 속성** > **C/c + +** > **명령줄** 속성 페이지.

1. 추가 **/Yl**_이름_ 컴파일러 옵션에는 **추가 옵션** 상자입니다. 선택 **확인** 변경 내용을 저장 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[컴파일러 옵션](../../build/reference/compiler-options.md)  
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)  
