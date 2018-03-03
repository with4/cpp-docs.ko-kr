---
title: "-OUT (출력 파일 이름) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.OutputFile
- /out
dev_langs:
- C++
helpviewer_keywords:
- output files, name linker option
- -OUT linker option
- OUT linker option
- /OUT C++ linker option
- linker [C++], output files
ms.assetid: 976210a4-e51f-4cfb-af5e-c16344455834
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a548e21e6bb485a326a2a9e34c6f47d968bbb6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="out-output-file-name"></a>/OUT(출력 파일 이름)
```  
/OUT:filename  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 출력 파일에 대 한 사용자 지정 이름입니다. 기본 이름을 대체합니다.  
  
## <a name="remarks"></a>설명  
 /OUT 옵션을 기본 이름 및 링커가 만드는 프로그램의 위치를 무시 합니다.  
  
 기본적으로 링커는 적절 한 확장명 (예:.exe 또는.dll) 및 지정 된 첫 번째.obj 파일의 기본 이름을 사용 하 여 파일 이름을 형성 합니다.  
  
 이 옵션은 기본 이름을 대체.mapfile 또는 가져오기 라이브러리에 대 한 합니다. 자세한 내용은 참조 [맵 파일 생성](../../build/reference/map-generate-mapfile.md) (/map) 및 [/IMPLIB](../../build/reference/implib-name-import-library.md)합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **일반** 속성 페이지.  
  
4.  수정 된 **출력 파일** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)