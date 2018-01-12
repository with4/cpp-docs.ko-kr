---
title: "-Yl (디버그 라이브러리에 PCH 참조 넣기) | Microsoft Docs"
ms.custom: 
ms.date: 12/04/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /yl
dev_langs: C++
helpviewer_keywords:
- -Yl compiler option [C++]
- Yl compiler option [C++]
- /Yl compiler option [C++]
ms.assetid: 8e4a396a-6790-4a9f-8387-df015a3220e7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6e777977f6d869d2bbc28d980f6445851e54396b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="yl-inject-pch-reference-for-debug-library"></a>/Yl(디버그 라이브러리에 PCH 참조 넣기)

**/Yl** 옵션 미리 컴파일된 헤더 파일에 대 한 공용 기호를 만들고 미리 컴파일된 헤더를 사용 하는 모든 파일에서이 기호에 대 한 참조를 삽입 합니다. 이렇게 하면 미리 컴파일된 헤더를 사용 하는 모든 파일에서 디버거를 사용할 수 있는 미리 컴파일된 헤더 기호에 대 한 완전 한 형식 정보입니다. 기본적으로 이 옵션은 사용하도록 설정됩니다. 이 옵션을 사용 하는 미리 컴파일된 헤더를 사용 하는 연결 된 라이브러리의 디버그 정보를 누락 되어 링커 오류를 방지할 수 있습니다.

## <a name="syntax"></a>구문

>**/Yl**  
>**/Yl**_이름_  
>**/Yl-**  

### <a name="arguments"></a>인수

*name*  
기호를 정의 하거나 미리 컴파일된 헤더를 사용 하는 저장 및에서 참조 된 개체 파일 수를 정의 하는 데는 선택적 이름입니다.

*\-*  
대시 (-) 명시적으로 비활성화 된 **/Yl** 컴파일러 옵션입니다.

## <a name="remarks"></a>설명

**/Yl** 옵션을 사용 하면 디버거를 미리 컴파일된 헤더를 포함 하는 모든 파일에서 미리 컴파일된 헤더의 형식에 대 한 전체 정보를 가져옵니다. 이 옵션에서는 내부 기호 이름을, 삽입 하 여 미리 컴파일된 헤더를 만드는 데 개체 파일에 기호 정의 [/Yc](../../build/reference/yc-create-precompiled-header-file.md) 옵션을 미리 컴파일된 포함 하는 모든 파일의 기호에 대 한 참조를 삽입 합니다. 사용 하 여 헤더는 [/Yu](../../build/reference/yu-use-precompiled-header-file.md) 컴파일러 옵션입니다. 미리 컴파일된 헤더를 사용 하는 모든 소스 파일 이름이 지정 된 기호를 참조 하기 때문에 링커는 항상 기호와 연결 된 미리 컴파일된 헤더 디버깅 정보를 정의 하는 개체 파일을 연결 합니다. 기본적으로 이 옵션은 사용하도록 설정됩니다.

**/Yl**_이름_ 옵션이 미리 컴파일된 헤더 파일에 대 한 식별 기호를 명시적으로 만드는 데 사용 됩니다. 컴파일러가 사용 하는 *이름* 기호를 만들려면 비슷합니다 인수 \_ \_ @@ \_PchSym\_@00@... @*이름* 여기서 줄임표 (...)는 링커 생성 나타냅니다 문자 문자열입니다. 인수를 생략 하면 컴파일러에 기호 이름을 자동으로 생성 합니다.

**/Yl-** 기본 동작을 비활성화 하 고 미리 컴파일된 헤더를 포함 하는 개체 파일에 대 한 식별 하는 기호 참조를 넣지 않습니다. 이 옵션은 미리 컴파일된 헤더 파일이 표시 하지 않고 컴파일된 파일에 대 한 필요할 수 있습니다.

사용 하는 경우 **/Yl-**, **/Yc** 및 [/Z7](../../build/reference/z7-zi-zi-debug-information-format.md) 컴파일러 라이브러리를 작성 하는 옵션에 저장 된 디버깅 정보를 포함 하는 미리 컴파일된 헤더 파일을 만듭니다는 개체 아니라 파일.pdb 파일 [LNK1211](../../error-messages/tool-errors/linker-tools-error-lnk1211.md) 오류 또는 [LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md) 이 라이브러리를 사용 하는 빌드 경고가 발생할 수 있습니다 및 소스 파일을 미리 컴파일된 헤더를 만드는 데 사용 하는 경우에 미리 컴파일된 헤더 기호를 정의 하지 않습니다. 개체 파일의 경우 nothing 라이브러리 클라이언트에서 참조 될 때 링커가 미리 컴파일된 헤더 관련된 디버그 정보와 함께 링크에서이 라이브러리 개체 파일을 제외 될 수 있습니다. 이 문제를 해결 하려면 지정 **/Yl** 사용 하는 경우 **/Yc** 미리 컴파일된 헤더 파일을 만들려면 및 **/Yu** 사용할 수 있습니다. 이렇게 하면 디버깅 정보를 포함 하는 개체 파일 빌드에 포함 됩니다.

미리 컴파일된 헤더에 대 한 자세한 내용은 다음을 참조 하세요.

- [/Y (미리 컴파일된 헤더)](../../build/reference/y-precompiled-headers.md)

- [미리 컴파일된 헤더 파일 만들기](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. 선택 된 **명령줄** 속성 페이지에는 **C/c + +** 폴더입니다.

1. 추가 **/Yl**_이름_ 컴파일러 옵션에는 **추가 옵션** 상자입니다. 선택 **확인** 변경 내용을 저장 합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[컴파일러 옵션](../../build/reference/compiler-options.md)  
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)  
