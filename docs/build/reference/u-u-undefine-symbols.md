---
title: "-U,-u (기호 정의 해제) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLWCECompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLCompilerTool.UndefineAllPreprocessorDefinitions
- /u
- VC.Project.VCCLWCECompilerTool.UndefineAllPreprocessorDefinitions
dev_langs:
- C++
helpviewer_keywords:
- -U compiler option [C++]
- Undefine Symbols compiler option
- /U compiler option [C++]
- U compiler option [C++]
ms.assetid: 7bc0474f-6d1f-419b-807d-0d8816763b2a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18fdaf0c2cb980f1ed19fdfc0577769a9985cf85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="u-u-undefine-symbols"></a>/U, /u(기호 정의 해제)
**/U** 컴파일러 옵션에 지정된 된 전처리기 기호 정의 해제 합니다. **/u** 컴파일러 옵션에는 컴파일러를 정의 하는 Microsoft 전용 기호 정의 해제 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/U[ ]symbol  
/u  
```  
  
## <a name="arguments"></a>인수  
 `symbol`  
 전처리기 기호 정의 해제입니다.  
  
## <a name="remarks"></a>설명  
 모두는 **/U** 또는 **/u** 옵션 사용 하 여 만든 기호 정의 해제할 수는 **#define** 지시문입니다.  
  
 **/U** 옵션 사용 하 여 이전에 정의 된 기호 정의 해제할 수는 **/D** 옵션입니다.  
  
 기본적으로 컴파일러는 다음 Microsoft 전용 기호를 정의합니다.  
  
|기호|함수|  
|------------|--------------|  
|_CHAR_UNSIGNED|기본 char 형식은 부호가 없습니다. 경우 정의 [/J](../../build/reference/j-default-char-type-is-unsigned.md) 옵션을 지정 합니다.|  
|_CPPRTTI|로 컴파일된 코드 정의 [/GR](../../build/reference/gr-enable-run-time-type-information.md) 옵션입니다.|  
|_CPPUNWIND|로 컴파일된 코드 정의 [/EHsc](../../build/reference/eh-exception-handling-model.md) 옵션입니다.|  
|_DLL|경우 정의 [/MD](../../build/reference/md-mt-ld-use-run-time-library.md) 옵션을 지정 합니다.|  
|_M_IX86|기본적으로 x86 600으로 정의 된 대상으로 합니다.|  
|_MSC_VER|자세한 내용은 [Predefined Macros](../../preprocessor/predefined-macros.md)을 참조하십시오.|  
|_WIN32|WIN32 응용 프로그램에 대해 정의 합니다. 항상 정의되어 있습니다.|  
|_MT|경우 정의 [/MD 또는 /MT](../../build/reference/md-mt-ld-use-run-time-library.md) 옵션을 지정 합니다.|  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **고급** 속성 페이지.  
  
4.  수정 된 **전처리기 정의 해제** 또는 **모든 전처리기 정의 해제** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions%2A> 또는 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions%2A>을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [/J (부호 형식은 기본 문자)](../../build/reference/j-default-char-type-is-unsigned.md)   
 [/GR (런타임 형식 정보 사용)](../../build/reference/gr-enable-run-time-type-information.md)   
 [/EH (예외 처리 모델)](../../build/reference/eh-exception-handling-model.md)   
 [/MD, /MT, /LD (런타임 라이브러리 사용)](../../build/reference/md-mt-ld-use-run-time-library.md)