---
title: "-bigobj (에서 섹션의 증가 수입니다. Obj 파일) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /bigobj
dev_langs: C++
helpviewer_keywords:
- -bigobj compiler option [C++]
- /bigobj compiler option [C++]
- bigobj compiler option [C++]
ms.assetid: ba94d602-4015-4a8d-86ec-49241ab74c12
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 73e6da121b099bdf6e67cdffe4d7d2bd0892d32a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="bigobj-increase-number-of-sections-in-obj-file"></a>/bigobj(.Obj 파일의 섹션 수 늘리기)
**/bigobj** 개체 파일을 포함할 수 있는 섹션의 수를 늘립니다.  
  
## <a name="syntax"></a>구문  
  
```  
/bigobj  
```  
  
## <a name="remarks"></a>설명  
 기본적으로 개체 파일에는 최대 65, 536 포함할 수 있습니다 (2 ^16) 주소 지정 가능한 섹션. 지정된 대상 플랫폼과는 관계가 없습니다. **/bigobj** 하면 주소 용량을 4294967296 (2 ^32).  
  
 대부분의 모듈에서 65, 536 개 이상의 섹션이 포함 된.obj 파일을 생성 하지 않습니다. 그러나 생성 된 코드, 컴퓨터 또는 템플릿 라이브러리를 많이 사용 하는 코드 섹션을 더 보유할 수 있는.obj 파일에 필요할 수 있습니다. **/bigobj** 컴퓨터에서 생성 된 XAML 코드에 대량의 헤더가 포함 되어 있으므로 Windows 스토어 프로젝트에서 기본적으로 사용 됩니다. Windows 스토어 응용 프로그램 프로젝트에서 이 옵션을 사용하지 않도록 설정하면 컴파일러 오류 C1128이 발생할 가능성이 높습니다.  
  
 Visual c + + 2005 이전에 판매 된 링커를 사용 하 여 생성 하는.obj 파일을 읽을 수 없습니다 **/bigobj**합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  **추가 옵션** 상자에 컴파일러 옵션을 입력합니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)