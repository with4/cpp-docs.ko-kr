---
title: "-X (표준 무시 경로 포함) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /x
- VC.Project.VCCLCompilerTool.OVERWRITEStandardIncludePath
- VC.Project.VCCLWCECompilerTool.OVERWRITEStandardIncludePath
dev_langs: C++
helpviewer_keywords:
- /X compiler option [C++]
- include files, ignore standard path
- -X compiler option [C++]
- include directories, ignore standard
- X compiler option
- Ignore Standard Include Paths compiler option
ms.assetid: 16bdf2cc-c8dc-46e4-bdcc-f3caeba5e1ef
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5ed251e1b937d14c42d105d98c2771ed0a2d6172
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="x-ignore-standard-include-paths"></a>/X(표준 포함 경로 무시)
컴파일러를 PATH 및 INCLUDE 환경 변수에 지정 된 디렉터리에서 포함 파일을 검색할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
/X  
```  
  
## <a name="remarks"></a>설명  
 이 옵션을 사용할 수 있습니다는 [/I (추가 포함 디렉터리)](../../build/reference/i-additional-include-directories.md) (**/I**`directory`) 옵션입니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **전처리기** 속성 페이지.  
  
4.  수정 된 **표준 포함 경로 무시** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.IgnoreStandardIncludePath%2A>을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 명령에서 `/X` PATH 및 INCLUDE 환경 변수에서 지정한 위치를 무시 하도록 컴파일러에 지시 하 고 `/I` 을 검색할 디렉터리를 지정 포함 파일:  
  
```  
CL /X /I \ALT\INCLUDE MAIN.C  
```  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)