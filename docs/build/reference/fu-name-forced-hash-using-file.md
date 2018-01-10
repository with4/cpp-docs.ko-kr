---
title: "-FU (Name Forced #using 파일) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.ForcedUsingFiles
- /FU
- VC.Project.VCNMakeTool.ForcedUsingAssemblies
dev_langs: C++
helpviewer_keywords:
- -FU compiler option [C++]
- FU compiler option [C++]
- /FU compiler option [C++]
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 17b62859aaf0c9dc6b3313fbb726602b5b83a82c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fu-name-forced-using-file"></a>/FU(강제 #using 파일 이름 지정)
파일 이름을 전달 하는 대신 사용할 수 있는 컴파일러 옵션 [#using 지시문](../../preprocessor/hash-using-directive-cpp.md) 소스 코드에서.  
  
## <a name="syntax"></a>구문  
  
```  
/FU file  
```  
  
## <a name="arguments"></a>인수  
 `file`  
 이 컴파일 과정에서 참조 하는 메타 데이터 파일을 지정 합니다.  
  
## <a name="remarks"></a>설명  
 /FU 스위치는 파일 이름을 하나만 사용합니다. 여러 파일을 지정하려면 각 항목에 대해 /FU를 사용합니다.  
  
 사용 중인 경우 [!INCLUDE[cppcli](../../build/reference/includes/cppcli_md.md)] 및 사용 하 고 메타 데이터 참조는 [Friend 어셈블리](../../dotnet/friend-assemblies-cpp.md) 사용할 수 없는 기능을 **/FU**합니다. `#using` 특성과 함께 `[as friend]`을 사용해서 코드에서 메타데이터를 참조해야 합니다. Friend 어셈블리는 [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)]([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)])에서 지원되지 않습니다.  
  
 어셈블리 또는 공용 언어 런타임 (CLR)에 대 한 모듈을 만드는 방법에 대 한 정보를 참조 하십시오. [/clr (공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)합니다. 작성 하는 방법에 대 한 내용은 [!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)], 참조 [응용 프로그램 및 라이브러리 빌드](../../cppcx/building-apps-and-libraries-c-cx.md)합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **C/c + +** 폴더입니다.  
  
3.  선택 된 **고급** 속성 페이지.  
  
4.  수정 된 **강제 #using** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [출력 파일 (/ F) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)