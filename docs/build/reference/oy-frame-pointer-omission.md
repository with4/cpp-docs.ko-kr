---
title: "-Oy (프레임 포인터 생략) | Microsoft Docs"
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.OmitFramePointers
- /oy
dev_langs:
- C++
helpviewer_keywords:
- omit frame pointer
- Oy compiler option [C++]
- stack frame pointer compiler option [C++]
- -Oy compiler option [C++]
- frame pointer omission compiler option [C++]
- suppress frame pointer creation
- /Oy compiler option [C++]
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 15a760d1a9df383356ead2eb2d1e1b08e8b9ca57
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="oy-frame-pointer-omission"></a>/Oy(프레임 포인터 생략)

호출 스택에서 프레임 포인터를 생성하지 않습니다.

## <a name="syntax"></a>구문

> /Oy [-]

## <a name="remarks"></a>설명

프레임 포인터를 설정하고 제거할 필요가 없기 때문에 이 옵션을 사용하면 함수 호출 속도가 빨라집니다. 또한 자주 사용되는 변수와 하위 식을 저장하는 데 필요한 레지스터 하나(Intel 386 이상 버전의 EBP)도 추가로 확보할 수 있습니다.

**/Oy** 프레임 포인터 생략을 사용 하도록 설정 하 고 **/Oy-** 생략을 사용 하지 않도록 설정 합니다. **/Oy** x86 에서만 사용할 수 컴파일러입니다.

하는 경우 코드에 EBP 기반 주소 지정 요구를 지정할 수 있습니다는 **/Oy-** 옵션 다음의 **/Ox** 다시 실행 하거나 사용 하 여 [최적화](../../preprocessor/optimize.md) 으로 "**y**" 및 **오프** EBP 기반 주소 지정 최대로 최적화할에 대 한 인수입니다. 컴파일러가 EBP 기반 주소 지정이 필요한 상황을 대부분 인식합니다. 예를 들어, `_alloca` 및 `setjmp` 함수와 구조적 예외 처리가 있는 경우에 EBP 기반 주소 지정이 필요합니다.

[/Ox (활성화 가장 속도 최적화)](../../build/reference/ox-full-optimization.md) 및 [/O1, /O2 (크기 최소화, 속도 최대화)](../../build/reference/o1-o2-minimize-size-maximize-speed.md) 옵션 **/Oy**합니다. 지정 **/Oy-** 후의 **/Ox**, **/O1**, 또는 **/O2** 옵션이 비활성화 **/Oy**인지, 명시적 또는 묵시적 합니다.

**/Oy** 컴파일러 옵션을 선택 하면 컴파일러에서 프레임 포인터 정보가 제한 되므로 더 어렵게 디버거를 사용 합니다. 디버그 컴파일러 옵션을 지정 하는 경우 ([/Z7, /Zi, /ZI](../../build/reference/z7-zi-zi-debug-information-format.md))를 지정 하는 것이 좋습니다는 **/Oy-** 다른 최적화 컴파일러 옵션 뒤 옵션입니다.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면

1. 프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.

1. **C/C++** 폴더를 클릭합니다.

1. 클릭는 **최적화** 속성 페이지.

1. 수정 된 **프레임 포인터 생략** 속성입니다. 이 속성을 추가 또는 제거는 **/Oy** 옵션입니다. 추가 하려는 경우는 **/Oy-** 옵션을 클릭 하 여 **명령줄** 수정 **추가 옵션**합니다.

### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>을 참조하세요.

## <a name="see-also"></a>참고 항목

[/O 옵션 (코드 최적화)](../../build/reference/o-options-optimize-code.md)

[컴파일러 옵션](../../build/reference/compiler-options.md)

[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)