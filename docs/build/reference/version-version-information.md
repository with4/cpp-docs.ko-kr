---
title: "-버전 (버전 정보) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.Version
- /version
dev_langs: C++
helpviewer_keywords:
- -VERSION linker option
- Version Information linker option
- version numbers, specifying in .exe
- /VERSION linker option
- VERSION linker option
ms.assetid: b86d0e86-dca6-4316-aee2-d863ccb9f223
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aeb8d2845c5e8daa931e354b149fc1c35b37fbd7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="version-version-information"></a>/VERSION(버전 정보)
```  
/VERSION:major[.minor]  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *주요*및 *부*  
 .Exe 또는.dll 파일의 헤더에 포함 하려는 버전 번호입니다.  
  
## <a name="remarks"></a>설명  
 /VERSION 옵션을 사용 하면 링커에서.exe 또는.dll 파일의 머리글에 버전 번호를 삽입 하려면. DUMPBIN을 사용 하 여 [/HEADERS](../../build/reference/headers.md) /VERSION의 효과를 확인 하면 OPTIONAL HEADER VALUES의 이미지 버전 필드를 볼 수 있습니다.  
  
 *주요* 및 *부* 인수는 0-65535 범위의 10 진수 숫자입니다. 기본값은 0.0 버전입니다.  
  
 /VERSION으로 지정된 정보는 파일 탐색기에서 해당 속성을 볼 때 응용 프로그램에 대해 표시되는 버전 정보에 영향을 주지 않습니다. 해당 버전 정보는 응용 프로그램을 작성 하는 데 사용 되는 리소스 파일에서 가져옵니다. 참조 [버전 정보 편집기](../../windows/version-information-editor.md) 자세한 정보에 대 한 합니다.  
  
 버전 번호를 삽입 하는 다른 방법은 인는 [버전](../../build/reference/version-c-cpp.md) 모듈 정의 문의 합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **일반** 속성 페이지.  
  
4.  수정 된 **버전** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Version%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)