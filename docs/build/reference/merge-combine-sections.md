---
title: -병합 (섹션 결합) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /merge
- VC.Project.VCLinkerTool.MergeSections
dev_langs:
- C++
helpviewer_keywords:
- sections, combining
- /MERGE linker option
- sections, naming
- sections
- -MERGE linker option
- MERGE linker option
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ece36de793b17b8cc064ec3837ea481a1ce870a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373477"
---
# <a name="merge-combine-sections"></a>/병합(섹션 결합)
```  
/MERGE:from=to  
```  
  
## <a name="remarks"></a>설명  
 /MERGE 옵션 결합 되는 첫 번째 섹션 (*에서*)의 두 번째 섹션 (*를*), 고 결과 섹션 *를*합니다. 예를 들어, `/merge:.rdata=.text`을 입력합니다.  
  
 링크 섹션의 이름을 두 번째 섹션이 없는 경우 *에서* 으로 *를*합니다.  
  
 /MERGE 옵션은 Vxd 만들고 섹션 컴파일러에서 생성 된 이름을 재정의할 데 유용 합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  클릭는 **고급** 속성 페이지.  
  
4.  수정 된 **섹션 병합** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)