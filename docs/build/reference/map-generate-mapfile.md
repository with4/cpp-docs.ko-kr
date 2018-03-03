---
title: "맵 (맵 파일 생성) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /map
- VC.Project.VCLinkerTool.MapFileName
- VC.Project.VCLinkerTool.GenerateMapFile
dev_langs:
- C++
helpviewer_keywords:
- mapfiles, creating linker
- generate mapfile linker option
- mapfile linker option
- mapfiles, information about program being linked
- MAP linker option
- -MAP linker option
- mapfiles, specifying file name
- /MAP linker option
ms.assetid: 9ccce53d-4e36-43da-87b0-7603ddfdea63
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f01daff11d41263766b66ed335c60d4bf83ced45
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="map-generate-mapfile"></a>/MAP(맵파일 생성)
```  
/MAP[:filename]  
```  
  
## <a name="remarks"></a>설명  
 다음은 각 문자에 대한 설명입니다.  
  
 *filename*  
 맵 파일에 대 한 사용자 지정 이름입니다. 기본 이름을 대체합니다.  
  
## <a name="remarks"></a>설명  
 /MAP 옵션을 맵 파일을 만들도록 링커에 지시 합니다.  
  
 기본적으로 링커는 프로그램과 확장.map의 기본 이름으로 맵 파일의 이름을 합니다. 선택적 *filename* 맵 파일에 대 한 기본 이름을 재정의할 수 있습니다.  
  
 맵 파일에 링크 되는 프로그램에 대 한 다음 정보를 포함 하는 텍스트 파일은:  
  
-   이 파일의 기본 이름을 모듈 이름  
  
-   (에서 아니라 파일 시스템) 프로그램 파일 헤더에서 타임 스탬프  
  
-   각 그룹의 시작 주소를 사용 하 여 프로그램을 그룹 목록 (으로 *섹션*:*오프셋*), 길이, 그룹 이름 및 클래스  
  
-   공용 기호 목록은 (으로 *섹션*:*오프셋*), 이름, 플랫 주소 및.obj 파일 기호가 정의 된 기호  
  
-   진입점 (으로 *섹션*:*오프셋*)  
  
 [/MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md) 옵션 맵 파일에 포함 되도록 추가 정보를 지정 합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **디버그** 속성 페이지.  
  
4.  수정 된 **맵 파일 생성** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateMapFile%2A> 및 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MapFileName%2A>을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)