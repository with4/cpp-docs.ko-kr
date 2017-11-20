---
title: "-NXCOMPAT (데이터 실행 방지 기능과 호환) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /NXCOMPAT
dev_langs: C++
helpviewer_keywords:
- /NXCOMPAT linker option
- -NXCOMPAT linker option
- NXCOMPAT linker option
ms.assetid: 5858e7ff-24d3-4ac3-9046-af2c9e220d9b
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d97b1b84ef6894e4ec161dbcecef47f6b676af23
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="nxcompat-compatible-with-data-execution-prevention"></a>/NXCOMPAT(데이터 실행 방지 기능과 호환)
실행 파일이 Windows 데이터 실행 방지 기능과 호환 되는지 테스트 되었음을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
/NXCOMPAT[:NO]  
```  
  
## <a name="remarks"></a>설명  
 기본적으로 **/NXCOMPAT** 켜져 있습니다.  
  
 **/Nxcompat: no** 명시적으로 데이터 실행 방지와 호환 되지 않는 실행 파일을 지정할 데 사용할 수 있습니다.  
  
 데이터 실행 방지에 대 한 자세한 내용은 다음이 문서를 참조 합니다.  
  
-   [데이터 실행 방지 (DEP) 기능에 대 한 자세한 설명을](http://go.microsoft.com/fwlink/?LinkID=157771) Microsoft 도움말 및 지원 웹 사이트에서  
  
-   [데이터 실행 방지](http://go.microsoft.com/fwlink/?LinkID=157770) MSDN 웹 사이트의  
  
-   [데이터 실행 방지 (Windows Embedded)](http://go.microsoft.com/fwlink/?LinkID=157768) MSDN 웹 사이트의  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  에 대 한 옵션을 입력에서 **추가 옵션** 상자입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)