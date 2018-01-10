---
title: "-EP (#line 지시문 없이 stdout로 전처리) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ep
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFileNoLines
dev_langs: C++
helpviewer_keywords:
- copy preprocessor output to stdout
- preprocessor output, copy to stdout
- -EP compiler option [C++]
- EP compiler option [C++]
- /EP compiler option [C++]
ms.assetid: 6ec411ae-e33d-4ef5-956e-0054635eabea
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9d7b2a64ec8fa7565d17ab04683fec07c48aea3f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ep-preprocess-to-stdout-without-line-directives"></a>/EP(#line 지시문 없이 stdout로 전처리)
C 및 c + + 소스 파일을 전처리 하 고 표준 출력 장치 전처리 파일을 복사 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/EP  
```  
  
## <a name="remarks"></a>설명  
 프로세스에서 모든 전처리기 지시문이 실행 되 매크로 확장이 수행 및 주석이 제거 됩니다. 전처리 된 출력에 메모를 유지 하기 위해 사용 하 여는 [(보존 설명 하는 동안 전처리) /C](../../build/reference/c-preserve-comments-during-preprocessing.md) 옵션과 함께 **/EP**합니다.  
  
 **/EP** 옵션은 컴파일을 억제 합니다. 컴파일에 대 한 전처리 파일을 전송 해야 합니다. **/EP** 출력 파일이 표시는 **/FA**, **/Fa**, 및 **/Fm** 옵션입니다. 자세한 내용은 참조 [/FA, /Fa (목록 파일)](../../build/reference/fa-fa-listing-file.md) 및 [/Fm (맵 파일 이름)](../../build/reference/fm-name-mapfile.md)합니다.  
  
 처리의 이후 단계 동안 발생 한 오류는 원래 원본 파일 보다는 전처리 된 파일의 줄 번호를 참조 하십시오. 줄 번호를 원본 소스 파일을 참조 하려는 경우 사용할 [/E (stdout으로 전처리)](../../build/reference/e-preprocess-to-stdout.md) 대신 합니다. **/E** 옵션 추가 `#line` 지시문이이 용도 대 한 출력입니다.  
  
 전처리 된 출력으로 보낼 `#line` 지시문을 파일에 사용 된 [/P (파일 전처리)](../../build/reference/p-preprocess-to-a-file.md) 옵션을 사용 합니다.  
  
 와 함께 stdout으로 전처리 된 출력을 보낼 `#line` 지시문을 사용 하 여 **/P** 및 **/EP** 함께 합니다.  
  
 미리 컴파일된 헤더를 사용할 수 없습니다는 **/EP** 옵션입니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **전처리기** 속성 페이지.  
  
4.  수정 된 **전처리 파일 생성** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>을 참조하세요.  
  
## <a name="example"></a>예  
 다음 명령줄을 실행 하면 `ADD.C`, 의견, 유지 및 표준 출력 장치에 결과 표시 합니다.  
  
```  
CL /EP /C ADD.C  
```  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)