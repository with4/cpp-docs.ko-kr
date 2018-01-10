---
title: "-NOENTRY (진입점 없음) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ResourceOnlyDLL
- /noentry
dev_langs: C++
helpviewer_keywords:
- entry points [C++], linker specifying
- -NOENTRY linker option
- resource-only DLLs [C++], creating
- NOENTRY linker option
- /NOENTRY linker option [C++]
- DLLs [C++], creating
ms.assetid: 0214dd41-35ad-43ab-b892-e636e038621a
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5990123d809a5fdaa00e3fd44666dd3fc37c69bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="noentry-no-entry-point"></a>/NOENTRY(진입점 없음)
```  
/NOENTRY  
```  
  
## <a name="remarks"></a>설명  
 실행 코드가 없는 리소스 전용 DLL을 만들려면 /NOENTRY 옵션을 지정해야 합니다. 자세한 내용은 참조 [Resource-Only DLL 만들기](../../build/creating-a-resource-only-dll.md)합니다.  
  
 이 옵션을 사용하면 LINK가 `_main`에 대한 참조를 DLL로 링크하는 것을 방지할 수 있습니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  선택 된 **링커** 폴더입니다.  
  
3.  선택 된 **고급** 속성 페이지.  
  
4.  수정 된 **진입점 없음** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ResourceOnlyDLL%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [리소스 전용 DLL 만들기](../../build/creating-a-resource-only-dll.md)   
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)