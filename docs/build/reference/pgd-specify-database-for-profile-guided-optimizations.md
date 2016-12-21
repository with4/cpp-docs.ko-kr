---
title: "/PGD(프로필 기반 최적화를 위한 데이터베이스 지정) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.ProfileGuidedDatabase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/PGD 링커 옵션"
  - "-PGD 링커 옵션"
ms.assetid: 9f312498-493b-461f-886f-92652257e443
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /PGD(프로필 기반 최적화를 위한 데이터베이스 지정)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/PGD:`filename`  
  
## 설명  
 다음은 각 문자에 대한 설명입니다.  
  
 `filename`  
 실행 중인 프로그램에 대한 정보를 저장하는 데 사용할 .pgd 파일의 이름을 지정합니다.  
  
## 설명  
 [\/LTCG:PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md)를 사용하는 경우 \/PGD를 사용하여 .pgd 파일에 대해 사용자 정의 이름이나 위치를 지정합니다.  \/PGD를 지정하지 않으면 .pgd 파일 이름이 출력 파일\(.exe 또는 .dll\)의 이름과 동일하게 지정되고 링크가 실행된 디렉터리에 파일이 생성됩니다.  
  
 \/LTCG:PGOPTIMIZE를 사용하는 경우 \/PGD를 사용하여 최적화된 이미지 생성에 사용할 .pgd 파일의 이름을 지정합니다.  
  
 자세한 내용은 [프로필 기반 최적화](../../build/reference/profile-guided-optimizations.md)를 참조하십시오.  
  
### Visual Studio 개발 환경에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트의 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [Visual C\+\+ 프로젝트 속성 설정](../../ide/working-with-project-properties.md)을 참조하십시오.  
  
2.  **구성 속성** 노드를 확장합니다.  
  
3.  **링커** 노드를 확장합니다.  
  
4.  **최적화** 속성 페이지를 선택합니다.  
  
5.  **프로필 기반 데이터베이스** 속성을 수정합니다.  
  
### 프로그래밍 방식으로 이 링커 옵션을 설정하려면  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>를 참조하십시오.  
  
## 참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)