---
title: -Oi (내장 함수 생성) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions
- /oi
- VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions
dev_langs:
- C++
helpviewer_keywords:
- Oi compiler option [C++]
- intrinsic functions, generate
- /Oi compiler option [C++]
- -Oi compiler option [C++]
- generate intrinsic functions compiler option [C++]
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f28051f5d7aaaa4606fffa4d4c94fb2086031419
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375843"
---
# <a name="oi-generate-intrinsic-functions"></a>/Oi(내장 함수 만들기)
일부 함수 호출을 내장 함수나 특정 형태의 함수 응용 프로그램에 도움이 되는 교체를 더 빠르게 실행 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Oi[-]  
```  
  
## <a name="remarks"></a>설명  
 내장 함수를 사용 하는 프로그램은 더 빠르게 함수 호출의 오버 헤드를 갖지 않는 되었지만 추가 코드를 만들기 때문에 더 큰 수 있습니다.  
  
 참조 [내장](../../preprocessor/intrinsic.md) 자세한 내용은 함수는 내장 형식이 있습니다.  
  
 **/Oi** 만 컴파일러에 교체 하는 요청 일부 함수 호출을 내장 형식;는 컴파일러 수 함수 호출 (및 내장을 함수 호출을 대체 하지) 성능이 향상 되는 결과입니다.  
  
 **x86 특정**  
  
 내장 부동 소수점 함수 않습니다 하지 입력된 값에 대해 특별 한 검사를 수행 하 고 따라서의 입력을 제한 된 범위에서 작동 수 있고 다른 예외 처리와 같은 이름 가진 라이브러리 루틴과 경계 조건입니다. IEEE 예외 처리의 손실과 손실 의미 실제 내장 형식을 사용 하 여 `_matherr` 및 `errno` 기능; 기능 손실 ANSI 규칙을 사용할 수 있습니다. 그러나 내장 형식을 사용 하면 수의 속도를 부동 종점 많은 프로그램 되며 대부분의 프로그램에 대 한 소수점 크게 높일의 합니다.  
  
 사용할 수는 [Za](../../build/reference/za-ze-disable-language-extensions.md) 컴파일러 옵션을 실제 내장 부동 소수점 옵션 생성을 무시 합니다. 이 경우에는 함수가 인수를 프로그램 스택으로 푸시하는 대신 부동 소수점 칩으로 직접 전달하는 라이브러리 루틴으로 생성됩니다.  
  
 **최종 x86 특정**  
  
 또한 사용 [내장](../../preprocessor/intrinsic.md) 내장 함수 또는 [함수 (C/c + +)](../../preprocessor/function-c-cpp.md) 함수 호출을 명시적으로 적용할 합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **최적화** 속성 페이지.  
  
4.  수정 된 **내장 함수 사용** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [/O 옵션 (코드 최적화)](../../build/reference/o-options-optimize-code.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [컴파일러 내장 함수](../../intrinsics/compiler-intrinsics.md)