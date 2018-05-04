---
title: -GX (예외 처리 사용) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gx
dev_langs:
- C++
helpviewer_keywords:
- exception handling, enabling
- /GX compiler option [C++]
- -GX compiler option [C++]
- cl.exe compiler, exception handling
- enable exception handling compiler option [C++]
- GX compiler option [C++]
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee2d3d31a9f091e6aa3fbed39f702471047a01dd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="gx-enable-exception-handling"></a>/GX(예외 처리 사용)
더 이상 사용되지 않습니다. 동기 예외 처리 기능 하는 가정을 사용 하 여 사용 하 여 선언 하면 `extern "C"` 예외를 throw 하지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
/GX  
```  
  
## <a name="remarks"></a>설명  
 **/GX** 는 사용 되지 않습니다. 에 해당 하는 사용 하 여 [/EHsc](../../build/reference/eh-exception-handling-model.md) 옵션을 사용 합니다. 목록이 사용 되지 않는 컴파일러 옵션에 대 한 참조는 **사용 되지 않음 및 컴파일러 옵션 제거** 섹션 [컴파일러 옵션 범주별 목록](../../build/reference/compiler-options-listed-by-category.md)합니다.  
  
 기본적으로 **/EHsc**, 해당 **/GX**, Visual Studio 개발 환경을 사용 하 여 컴파일하는 경우 적용 됩니다. 명령줄 도구를 사용 하 여 예외 처리 하지 지정 됩니다. 이 해당 하는 **/GX-** 합니다.  
  
 자세한 내용은 참조 [c + + 예외 처리](../../cpp/cpp-exception-handling.md)합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  탐색 창에서 선택 **구성 속성**, **C/c + +**, **명령줄**합니다.  
  
3.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [/EH(예외 처리 모델)](../../build/reference/eh-exception-handling-model.md)