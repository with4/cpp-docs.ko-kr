---
title: "-ALLOWBIND (DLL 바인딩 방지) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.PreventDLLBinding
- /allowbind
dev_langs: C++
helpviewer_keywords:
- /ALLOWBIND linker option
- binding DLLs
- preventing DLL binding
- ALLOWBIND linker option
- -ALLOWBIND linker option
- DLLs [C++], preventing binding
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dc5d5827da555cc11a7fbc1417a9a0e26f953cea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="allowbind-prevent-dll-binding"></a>/ALLOWBIND(DLL 바인딩 방지)
```  
/ALLOWBIND[:NO]  
```  
  
## <a name="remarks"></a>설명  
 /ALLOWBIND:NO는 DLL의 헤더에서 이미지 바인딩을 허용하지 않는 Bind.exe를 가리키는 비트를 설정합니다. 바인딩이 서명을 무효화하므로 디지털 서명된 경우 DLL을 바인딩하지 않으려고 할 수 있습니다.  
  
 /ALLOWBIND 기능을 위해 기존의 DLL을 편집할 수는 [/ALLOWBIND](../../build/reference/allowbind.md) EDITBIN 유틸리티의 옵션입니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 **구성 속성**, **링커**를 선택 하 고 **명령줄**합니다.  
  
3.  입력 `/ALLOWBIND:NO` 에 **추가 옵션**합니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)   
 [BindImage 함수](http://msdn.microsoft.com/library/windows/desktop/ms679278.aspx)   
 [BindImageEx 함수](http://msdn.microsoft.com/library/windows/desktop/ms679279.aspx)