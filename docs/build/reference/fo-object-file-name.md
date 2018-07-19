---
title: -Fo (개체 파일 이름) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Fo
- VC.Project.VCCLCompilerTool.ObjectFile
- VC.Project.VCCLWCECompilerTool.ObjectFile
dev_langs:
- C++
helpviewer_keywords:
- Fo compiler option [C++]
- object files, naming
- /Fo compiler option [C++]
- -Fo compiler option [C++]
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea552b149270b8e644140a4dd51f220648ef376e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374010"
---
# <a name="fo-object-file-name"></a>/Fo(개체 파일 이름)
기본값 대신 사용할 개체(.obj) 파일 이름 또는 디렉터리를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/Fopathname  
```  
  
## <a name="remarks"></a>설명  
 이 옵션을 사용 하지 않는 경우 소스 파일 및.obj 확장의 기본 이름 개체 파일에 사용 합니다. 다른 이름 및 확장명을 사용할 수 있지만 권장 사용 하는 것입니다. obj.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  **출력 파일** 속성 페이지를 클릭합니다.  
  
4.  수정 된 **개체 파일 이름** 속성입니다.  개발 환경에서 개체 파일의 확장 되어 있어야 합니다. obj.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 명령줄에 있는 기존 디렉터리를 \OBJECT, 2. 드라이브에서 THIS.obj 라는 개체 파일을 만듭니다.  
  
```  
CL /FoB:\OBJECT\ THIS.C  
```  
  
## <a name="see-also"></a>참고 항목  
 [출력 파일 (/ F) 옵션](../../build/reference/output-file-f-options.md)   
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)   
 [경로 이름 지정](../../build/reference/specifying-the-pathname.md)