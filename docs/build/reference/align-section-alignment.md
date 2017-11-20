---
title: "맞춤 (섹션 맞춤) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
dev_langs: C++
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
ms.assetid: f2f8ac24-e90e-4bea-8205-f2960a3b1740
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e620719d5a69c333a45664fba5967a740224d4d5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="align-section-alignment"></a>/ALIGN(섹션 맞춤)
```  
/ALIGN[:number]  
```  
  
## <a name="remarks"></a>설명  
 여기서  
  
 `number`  
 맞춤 값입니다.  
  
## <a name="remarks"></a>설명  
 /ALIGN 옵션은 프로그램의 선형 주소 공간 내에서 각 섹션의 맞춤을 지정 합니다. `number` 인수는 바이트 단위 이며 2의 거듭제곱 이어야 합니다. 기본값은 4k (4096). 링커에서 맞춤 잘못 된 이미지를 생성 합니다. 경고를 표시 합니다.  
  
 장치 드라이버 등의 응용 프로그램을 작성 하는 경우가 맞춤을 수정할 필요는 없습니다.  
  
 맞춤 매개 변수를 사용 하는 특정 섹션의 맞춤을 수정할 수는 [/section](../../build/reference/section-specify-section-attributes.md) 옵션입니다.  
  
 지정 된 맞춤 값의 가장 큰 섹션 맞춤 보다 작을 수 없습니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  클릭는 **링커** 폴더입니다.  
  
3.  **명령줄** 속성 페이지를 클릭합니다.  
  
4.  에 옵션을 입력에서 **추가 옵션** 상자입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)