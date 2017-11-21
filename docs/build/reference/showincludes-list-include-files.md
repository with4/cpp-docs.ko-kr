---
title: "-showIncludes (목록 파일을 포함 하는 데 사용) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ShowIncludes
- VC.Project.VCCLCompilerTool.ShowIncludes
- /showincludes
dev_langs: C++
helpviewer_keywords:
- include files
- /showIncludes compiler option [C++]
- include files, displaying in compilation
- -showIncludes compiler option [C++]
- showIncludes compiler option [C++]
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 72f80202d2d1c8018e9c145951664d335ac759b7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="showincludes-list-include-files"></a>/showIncludes(포함 파일 나열)
컴파일러가 포함 파일의 목록을 출력 합니다. 중첩 된 포함 파일도 표시 됩니다 (포함 하는 파일에서 포함 된).  
  
## <a name="syntax"></a>구문  
  
```  
/showIncludes  
```  
  
## <a name="remarks"></a>설명  
 컴파일하는 동안 포함 파일에 오류가 발생 하면 메시지가 출력 됩니다., 예:  
  
```  
Note: including file: d:\MyDir\include\stdio.h  
```  
  
 중첩 된 포함 파일 예를 들어 들여쓰기, 각 중첩 수준에 대 한 하나의 공간으로 표시 됩니다.  
  
```  
Note: including file: d:\temp\1.h  
Note: including file:  d:\temp\2.h  
```  
  
 이 경우 `2.h` 내에 포함 된 `1.h`, 따라서 들여쓰기입니다.  
  
 **/showIncludes** 를 내보내는 옵션 `stderr`이 아니라 `stdout`합니다.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 컴파일러 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  **C/C++** 폴더를 클릭합니다.  
  
3.  클릭는 **고급** 속성 페이지.  
  
4.  수정 된 **포함 표시** 속성입니다.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>프로그래밍 방식으로 이 컴파일러 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)