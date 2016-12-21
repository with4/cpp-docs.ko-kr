---
title: "MFC ActiveX 컨트롤 컨테이너 만들기 | Microsoft Docs"
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
  - "vc.appwiz.activex.container"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤 컨테이너[C++], 만들기"
  - "컨테이너[C++], 만들기"
  - "MFC ActiveX 컨트롤[C++], 컨테이너"
  - "OLE 컨트롤[C++], 컨테이너"
ms.assetid: ec70e137-7c14-4940-bd0e-fd4edcc63ea5
caps.latest.revision: 8
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC ActiveX 컨트롤 컨테이너 만들기
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ActiveX 컨트롤 컨테이너는 ActiveX\(이전의OLE\) 컨트롤이 실행되는 환경을 제공하는 상위 프로그램입니다.  ActiveX 컨트롤을 포함할 수 있는 응용 프로그램을 만들 때는 MFC를 사용할 수도 있고 사용하지 않을 수도 있습니다. 그러나 MFC를 사용하여 만드는 것이 훨씬 쉽습니다.  
  
 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md)를 사용하여 MFC 컨테이너 프로그램을 만들면 MFC와 ActiveX 클래스에서 구현된 자동화 및 ActiveX 컨트롤의 다양한 기능에 액세스할 수 있습니다.  이 기능에는 비주얼 편집, 자동화, 복합 파일 만들기, 컨트롤 지원 등이 포함됩니다.  상위 프로그램에서 지원할 MFC 응용 프로그램 마법사의 비주얼 편집 옵션에는 컨테이너, 미니 서버, 풀 서버 및 컨테이너와 서버가 모두 있는 프로그램 만들기가 포함됩니다.  
  
-   **새로운 MFC 응용 프로그램**.  자동화, 비주얼 편집, 복합 파일 또는 컨트롤 지원을 포함하는 새로운 MFC 프로그램을 만들려면 MFC 응용 프로그램 마법사를 사용하고 적절한 자동화 옵션을 선택합니다.  
  
-   **기존 MFC 응용 프로그램**.  기존 MFC 응용 프로그램에 컨트롤 포함을 추가하려면 [OLE 컨트롤 컨테이너: OLE 컨트롤 포함 기능 직접 활성화](../../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)를 참조하십시오.  
  
### 다음과 같은 유형의 응용 프로그램에 대해 ActiveX 컨테이너를 만들려면  
  
1.  [컨테이너](../../mfc/containers.md)  
  
2.  [비주얼 편집](../../mfc/ole-mfc.md)  
  
3.  [MFC ActiveX 컨트롤](../../mfc/mfc-activex-controls.md)  
  
## 참고 항목  
 [Visual C\+\+ 프로젝트 형식](../../ide/visual-cpp-project-types.md)