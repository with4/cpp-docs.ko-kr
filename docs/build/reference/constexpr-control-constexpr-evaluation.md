---
title: constexpr (컨트롤 constexpr 평가) | Microsoft Docs
ms.custom: ''
ms.date: 08/15/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /constexpr
- -constexpr
dev_langs:
- C++
helpviewer_keywords:
- /constexpr control constexpr evaluation [C++]
- -constexpr control constexpr evaluation [C++]
- constexpr control constexpr evaluation [C++]
ms.assetid: 76d56784-f5ad-401d-841d-09d1059e8b8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f83f1d9a505ebc4c05ce4e367bb1e978d6a14b78
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (컨트롤 constexpr 평가)  
  
사용 하 여는 **/constexpr** 컴파일러 옵션에 대 한 제어 매개 변수를 `constexpr` 컴파일 타임에 평가 합니다.  
  
## <a name="syntax"></a>구문  
  
> /constexpr:depth*N*  
> /constexpr:backtrace*N*  
> /constexpr:steps*N*  
  
## <a name="arguments"></a>인수  
  
**깊이 * * * N*  
재귀 깊이 제한 `constexpr` 함수를 호출 *N* 수준입니다. 기본값은 512입니다.  
  
**backtrace * * * N*  
최대 표시 *N* `constexpr` 진단에서 평가 합니다. 기본값은 10입니다.  
  
**단계 * * * N*  
종료 `constexpr` 후 계산 *N* 단계입니다. 기본값은 100, 000입니다.  
  
## <a name="remarks"></a>설명  
  
**/constexpr** 컴파일러 옵션의 컴파일 시간 계산을 제어 `constexpr` 식입니다. 평가 단계, 재귀 수준 및 backtrace 깊이 컴파일러에 너무 많은 시간을 소비 하지 못하도록 제어 `constexpr` 평가 합니다. 대 한 자세한 내용은 `constexpr` 언어 요소 참조 [constexpr (c + +)](../../cpp/constexpr-cpp.md)합니다.  

**/constexpr** 옵션은 Visual Studio 2015부터 사용할 수 있습니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1. 프로젝트의를 열고 **속성 페이지** 대화 상자.   
  
2. **구성 속성**, 확장 하 고는 **C/c + +** 폴더를 선택 하 고는 **명령줄** 속성 페이지.  
  
3. 입력 **/constexpr** 컴파일러 옵션에 **추가 옵션** 상자입니다. 선택 **확인** 또는 **적용** 변경 내용을 저장 합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
  
[컴파일러 옵션](../../build/reference/compiler-options.md)   
[컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)