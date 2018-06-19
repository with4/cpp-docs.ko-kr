---
title: -P (파일 전처리) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFile
- /p
- VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile
dev_langs:
- C++
helpviewer_keywords:
- /P compiler option [C++]
- -P compiler option [C++]
- P compiler option [C++]
- output files, preprocessor
- preprocessing output files
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 26e9d2d63c7244990a047749f15273b45229c7bd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377146"
---
# <a name="p-preprocess-to-a-file"></a>/P(파일 전처리)
C 및 c + + 소스 파일을 전처리 하 고 전처리 된 출력 파일을 씁니다.  
  
## <a name="syntax"></a>구문  
  
```  
/P  
```  
  
## <a name="remarks"></a>설명  
 파일 이름이 같은 기본 소스 파일 및.i 확장명입니다. 프로세스에서 모든 전처리기 지시문이 실행 되 매크로 확장이 수행 및 주석이 제거 됩니다. 전처리 된 출력에 메모를 유지 하기 위해 사용 하 여는 [(보존 설명 하는 동안 전처리) /C](../../build/reference/c-preserve-comments-during-preprocessing.md) 옵션과 함께 **/P**합니다.  
  
 **/P** 추가 `#line` 지시문을 시작과 끝에 포함된 된 파일의 그리고 조건부 컴파일 용 전처리기 지시문에 의해 제거 된 줄에 출력 합니다. 이러한 지시문 전처리 파일의 줄 번호를 다시 지정 합니다. 결과적으로, 처리의 이후 단계 동안 발생 한 오류는 전처리 파일의 줄 보다는 원본 소스 파일의 줄 번호를 참조 하십시오. 생성 되지 않게 하려면 `#line` 지시문을 사용 하 여 [/EP (#line 지시문 없이 stdout로 전처리)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) 으로 **/P**합니다.  
  
 **/P** 옵션은 컴파일을 억제 합니다. 사용 하는 경우에.obj 파일을 생성 하지 않으므로 [/Fo (개체 파일 이름)](../../build/reference/fo-object-file-name.md)합니다. 컴파일에 대 한 전처리 파일을 전송 해야 합니다. **/P** 출력 파일이 표시는 **/FA**, **/Fa**, 및 **/Fm** 옵션입니다. 자세한 내용은 참조 [/FA, /Fa (목록 파일)](../../build/reference/fa-fa-listing-file.md) 및 [/Fm (맵 파일 이름)](../../build/reference/fm-name-mapfile.md)합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **전처리기** 속성 페이지.  
  
4.  수정 된 **전처리 파일 생성** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 명령줄을 실행 하면 `ADD.C`주석을 유지, 추가, `#line` 지시문을 파일에 결과 기록 `ADD.I`:  
  
```  
CL /P /C ADD.C  
```  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [/Fi(출력 파일 이름 전처리)](../../build/reference/fi-preprocess-output-file-name.md)