---
title: -FORCE (파일 출력 강제) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.ForceLink
- /force
dev_langs:
- C++
helpviewer_keywords:
- FORCE linker option
- file output in linker
- /FORCE linker option
- -FORCE linker option
ms.assetid: b1e9a218-a5eb-4e60-a4a4-65b4be15e5da
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1daa27ce48590d4a122eafde9f63f7142271610
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="force-force-file-output"></a>/FORCE(파일 출력 강제)
```  
/FORCE:[MULTIPLE|UNRESOLVED]  
```  
  
## <a name="remarks"></a>설명  
 /FORCE 옵션 올바른.exe 파일을 만드는 링커에서 또는 DLL에 기호 있지 않고 참조 되는 경우에 정의 된 또는 여러 번 정의 되어 있습니다.  
  
 /FORCE 옵션은 선택적 인수를 사용할 수 있습니다.  
  
-   /FORCE:MULTIPLE를 사용 하 여 링크는 기호에 대 한 개 이상의 정의 찾습니다. 여부 출력 파일을 만듭니다.  
  
-   /FORCE를 사용 하 여: UNRESOLVED를 링크 정의 되지 않은 기호를 찾습니다. 여부 출력 파일을 만듭니다. / 강제로: 확인 되지 않은 진입점 기호 해결 되지 않은 경우 무시 됩니다.  
  
 / 인수 없이 강제 모두 여러를 의미 하며 확인할 수 없습니다.  
  
 이 옵션을 사용 하 여 만든 파일 예상 대로 실행 되지 않을 수 있습니다. /FORCE 옵션을 지정 하는 경우 링커 증분 방식으로 연결 되지 않습니다.  
  
 모듈은으로 컴파일된 경우 **/clr**, **/force** 이미지를 만들지는 것입니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  에 옵션을 입력에서 **추가 옵션** 상자입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)