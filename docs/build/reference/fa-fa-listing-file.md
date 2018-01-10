---
title: "/FA, /Fa (목록 파일) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AssemblerListingLocation
- VC.Project.VCCLCompilerTool.ConfigureASMListing
- VC.Project.VCCLWCECompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.AssemblerListingLocation
- /fa
- VC.Project.VCCLCompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing
dev_langs: C++
helpviewer_keywords:
- FA compiler option [C++]
- /FA compiler option [C++]
- -FA compiler option [C++]
- listing file type
- assembly-only listing
ms.assetid: c7507d0e-c69d-44f9-b8e2-d2c398697402
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0cd569cf16e7b2a14faaa119eacaef0994d09dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fa-fa-listing-file"></a>/FA, /Fa(목록 파일)
어셈블러 코드가 포함 된 목록 파일을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
> **/FA**[**c**\][**s**\][**u**]  
> **/Fa**_경로 이름_  
  
## <a name="remarks"></a>설명  
`/FA` 컴파일러 옵션 C 또는 c + + 소스 파일은 일반적으로 해당 컴파일에서 각 변환 단위에 대 한 어셈블러 목록 파일을 생성 합니다. 기본적으로만 어셈블러 ANSI로 인코딩 되는 목록 파일에 포함 됩니다. 선택적 `c`, `s`, 및 `u` 에 대 한 인수 `/FA` 제어 여부 기계어 코드 또는 소스 코드는 목록, 어셈블러 출력 및 목록 u t F-8로 인코딩 되는 여부입니다.  
  
기본적으로 각 목록 파일은 소스 파일과 동일한 기본 이름을 가져오고.asm 확장명이 합니다. 기계어 코드를 사용 하 여 포함 된 경우는 `c` 옵션을 목록 파일에.cod 확장 합니다. 이름 및 목록 파일을 사용 하 여 만들어진 디렉터리의 확장을 변경할 수 있습니다는 `/Fa` 옵션입니다.  

### <a name="fa-arguments"></a>/FA 인수  
없음  
어셈블러 언어만 목록에 포함 되어 있습니다.  
  
`c`  
선택 사항입니다. 기계어 코드 목록에 포함 되어 있습니다.  
  
`s`  
선택 사항입니다. 목록에서 소스 코드를 포함 합니다.  
  
`u`선택 사항입니다. 목록 파일에 utf-8 형식으로 인코딩하고 바이트 순서 마커를 포함 합니다. 기본적으로 파일은 ANSI로 인코딩됩니다. 사용 하 여 `u` 를 모든 시스템에 올바르게 표시 하는 목록 파일을 만드는 컴파일러에 대 한 입력으로 유니코드를 사용 하는 경우 또는 소스 코드 파일.  
  
두 `s` 및 `u` 지정 되 고 소스 코드 파일 경우 u t F-8로 다음 코드 줄.asm 파일에 올바르게 표시 되지 않을 이외의 유니코드 인코딩을 사용 합니다.  
  
### <a name="fa-argument"></a>/Fa 인수  
없음  
하나의 *소스*컴파일할에서 각 소스 코드 파일에 대해.asm 파일이 만들어집니다.  
  
*filename* 라는 목록 파일 *filename*.asm 현재 디렉터리에 배치 됩니다. 이 단일 소스 코드 파일을 컴파일할 때에 유효 합니다.  
  
*filename.extension*  
목록 파일 이름이 *filename.extension* 현재 디렉터리에 배치 됩니다. 이 단일 소스 코드 파일을 컴파일할 때에 유효 합니다.  
  
*디렉터리*\  
하나의 *source_file*.asm 파일을 만들고 지정 된 배치 *디렉터리* 컴파일할에서 각 소스 코드 파일에 대 한 합니다. Note 뒤의 백슬래시 필요 합니다. 현재 디스크에 경로만 허용 됩니다.  
  
*디렉터리*\\*filename* 라는 목록 파일 *filename*.asm 놓입니다 지정 된 *디렉터리*합니다. 이 단일 소스 코드 파일을 컴파일할 때에 유효 합니다.  
  
*디렉터리*\\*filename.extension*  
목록 파일 이름이 *filename.extension* 놓입니다 지정 된 *디렉터리*합니다. 이 단일 소스 코드 파일을 컴파일할 때에 유효 합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  열기는 **C/c + +** 폴더를 선택은 **출력 파일** 속성 페이지.  
  
3.  수정 된 **어셈블러 출력** 속성을 설정 하려면는 `/FAc` 및 `/FAs` 어셈블러, 컴퓨터 및 소스 코드에 대 한 옵션입니다. 수정 된 **어셈블러 목록에 대 한 사용 하 여 유니코드** 속성을 설정 하려면는 `/FAu` ANSI 또는 u t F-8 출력에 대 한 옵션입니다. 수정 된 **ASM 목록 위치** 설정 하는 `/Fa` 파일 이름 및 위치를 나열 하기 위한 옵션입니다.  
  
둘 다 설정 **어셈블러 출력** 및 **어셈블러 목록에 대 한 사용 하 여 유니코드** 속성으로 지정 하면 [명령줄 경고 D9025](../../error-messages/tool-errors/command-line-warning-d9025.md)합니다. IDE에서 이러한 옵션을 결합 하려면 사용 하 여는 **추가 옵션** 필드에 **명령줄** 속성 페이지 대신 합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerListingLocation%2A> 또는 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerOutput%2A>을 참조하십시오. 지정 하려면 `/FAu`, 참조 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>합니다.  
  
## <a name="example"></a>예  
다음 명령줄을 조합 된 소스를 생성 하 고 기계어 코드 hello.cod:  
  
```  
CL /FAcs HELLO.CPP  
```  
  
## <a name="see-also"></a>참고 항목  
 [출력 파일 (/ F) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)