---
title: -진단 (컴파일러 진단 옵션) | Microsoft Docs
ms.custom: ''
ms.date: 11/11/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /diagnostics
- VC.Project.VCCLCompilerTool.DiagnosticsFormat
dev_langs:
- C++
helpviewer_keywords:
- /diagnostics compiler diagnostic options [C++]
- -diagnostics compiler diagnostic options [C++]
- diagnostics compiler diagnostic options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d874e26a922a7f9cce7223b574d525d37733598
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="diagnostics-compiler-diagnostic-options"></a>/diagnostics (컴파일러 진단 옵션)  
  
사용 하 여는 **/diagnostics** 컴파일러 옵션을 한 위치 정보를 오류 및 경고 표시를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/diagnostics:{caret|classic|column}
```  

## <a name="remarks"></a>설명  
**/diagnostics** 컴파일러 옵션의 오류 및 경고 정보 표시를 제어 합니다.  
  
**/diagnostics:classic** 옵션은 기본적으로만 문제가 발견 된 줄 번호를 보고 합니다.  
  
**/diagnostics:column** 옵션은 또한 문제가 발견 된 열을 포함 합니다. 이 특정 언어 구문이 포함 되었거나 문제를 일으키는 문자를 확인할 수 있습니다.  
  
**/diagnostics:caret** 옵션에 있는 문제를 찾았으며 캐럿 (^) 위치에 있는 코드 줄에서 문제가 검색 된 배치 열이 포함 되어 있습니다.  
  
경우에 따라를 컴파일러에 문제가 발생 한 위치를 검색 하지 않습니다. 예를 들어, 누락 된 세미콜론, 예기치 않은 기호 있었을 때까지 검색 되지 않습니다. 열 보고 되 하 고 컴파일러는 값이 잘못 되었습니다,이 프로그램을 수정 해야 하는 발견 했습니다 캐럿 배치 됩니다.  
  
**/diagnostics** 옵션은 Visual Studio 2017부터 사용할 수 있습니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1. 프로젝트의를 열고 **속성 페이지** 대화 상자.   
  
2. **구성 속성**, 확장 하 고는 **C/c + +** 폴더를 선택 하 고는 **일반** 속성 페이지.  
  
3. 드롭다운 컨트롤에서 사용 하 여는 **진단 형식** 필드를 한 진단 선택 옵션을 표시 합니다. 선택 **확인** 또는 **적용** 변경 내용을 저장 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)