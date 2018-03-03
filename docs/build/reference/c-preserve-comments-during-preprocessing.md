---
title: "-C (전처리 중에 주석 유지) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.KeepComments
- /c
- VC.Project.VCCLWCECompilerTool.KeepComments
dev_langs:
- C++
helpviewer_keywords:
- comments, not stripping during preprocessing
- preserve comments during preprocessing
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6d27e6ed0f6a2ff6e6f63bc1b87522fb598953c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="c-preserve-comments-during-preprocessing"></a>/C(전처리 중에 주석 유지)
전처리하는 동안 주석을 유지합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/C  
```  
  
## <a name="remarks"></a>설명  
 이 컴파일러 옵션을 사용 하려면는 **/E**, **/P**, 또는 **/EP** 옵션입니다.  
  
 다음 코드 샘플 소스 코드 주석이 표시 됩니다.  
  
```  
// C_compiler_option.cpp  
// compile with: /E /C /c  
int i;   // a variable  
```  
  
 이 예제는 다음과 같은 출력을 생성 합니다.  
  
```  
#line 1 "C_compiler_option.cpp"  
int i;   // a variable  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **전처리기** 속성 페이지.  
  
4.  수정 된 **주석 유지** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [/E (stdout으로 전처리)](../../build/reference/e-preprocess-to-stdout.md)   
 [/P (파일 전처리)](../../build/reference/p-preprocess-to-a-file.md)   
 [/EP (#line 지시문 없이 stdout로 전처리)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)