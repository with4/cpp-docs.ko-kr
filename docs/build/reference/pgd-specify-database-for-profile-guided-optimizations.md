---
title: "-PGD (프로필 기반 최적화에 대 한 데이터베이스 지정) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.ProfileGuidedDatabase
dev_langs: C++
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 37113ef23adbbb50e36b51ed8ef0035ee20e885e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD(프로필 기반 최적화를 위한 데이터베이스 지정)
/PGD:`filename`  
  
## <a name="remarks"></a>설명  
 여기서  
  
 `filename`  
 실행 중인 프로그램에 대 한 정보를 보관 하는 데 사용 될.pgd 파일의 이름을 지정 합니다.  
  
## <a name="remarks"></a>설명  
 사용 하는 경우 [/ltcg: pginstrument](../../build/reference/ltcg-link-time-code-generation.md), /PGD를 사용 하 여 기본값이 아닌 이름이 나.pgd 파일의 위치를 지정 합니다. /PGD를 지정 하지 않으면.pgd 파일 이름이 출력 파일 (.exe 또는.dll) 이름과 되 고 링크가 호출 되는 동일한 디렉터리에 생성 됩니다.  
  
 /Ltcg: pgoptimize를 사용 하면 최적화 된 이미지를 만드는 데 사용할.pgd 파일의 이름을 지정 하려면 /PGD를 사용 합니다.  
  
 자세한 내용은 참조 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)합니다.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [Visual c + + 프로젝트 속성 설정](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 된 **구성 속성** 노드.  
  
3.  확장 된 **링커** 노드.  
  
4.  선택 된 **최적화** 속성 페이지.  
  
5.  수정 된 **프로필 기반 데이터베이스** 속성입니다.  
  
### <a name="to-set-this-linker-option-programmatically"></a>프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)