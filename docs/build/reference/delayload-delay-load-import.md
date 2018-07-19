---
title: -DELAYLOAD (가져오기 로드 지연) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /delayload
- VC.Project.VCLinkerTool.DelayLoadDLLS
dev_langs:
- C++
helpviewer_keywords:
- DELAYLOAD linker option
- -DELAYLOAD linker option
- /DELAYLOAD linker option
- delayed loading of DLLs, /DELAYLOAD option
ms.assetid: 39ea0f1e-5c01-450f-9c75-2d9761ff9b28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74d65caa8a0ea140f93bf156e3c14a85232e6e56
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372258"
---
# <a name="delayload-delay-load-import"></a>/DELAYLOAD(가져오기 로드 지연)
```  
/DELAYLOAD:dllname  
```  
  
## <a name="parameters"></a>매개 변수  
 `dllname`  
 로드를 지연할 DLL의 이름입니다.  
  
## <a name="remarks"></a>설명  
 /DELAYLOAD 옵션을 사용하면 `dllname`으로 지정된 DLL에서 프로그램이 함수를 처음 호출할 때만 해당 DLL이 로드됩니다. 자세한 내용은 참조 [링커의 지연 로드 된 Dll 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)합니다. 이 옵션을 필요한 횟수만큼 사용하여 선택한 수만큼의 DLL을 지정할 수 있습니다. 프로그램을 링크할 때 Delayimp.lib를 사용해야 하거나, 고유한 지연 로드 도우미 함수를 구현할 수 있습니다.  
  
 [지연/](../../build/reference/delay-delay-load-import-settings.md) 옵션 바인딩 및 로드 각 지연 로드 된 DLL에 대 한 옵션을 지정 합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  에 **링커** 폴더를 선택는 **입력** 속성 페이지.  
  
3.  수정 된 **지연 로드 된 Dll** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)