---
title: "MFC ActiveX 컨트롤 컨테이너 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.activex.container
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], containers
- ActiveX control containers [MFC], creating
- containers [MFC], creating
- OLE controls [MFC], containers
ms.assetid: ec70e137-7c14-4940-bd0e-fd4edcc63ea5
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2054a11365cc6f9db7a5608f0b056d0d85ff117d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-an-mfc-activex-control-container"></a>MFC ActiveX 컨트롤 컨테이너 만들기
ActiveX 컨트롤 컨테이너는 실행 하기 위해 (이전의 OLE) ActiveX 컨트롤에 대 한 환경을 제공 하는 부모 프로그램. 상관 없이, MFC ActiveX 컨트롤을 포함할 수 있는 응용 프로그램을 만들 수 있지만 MFC로 수행할 작업을 훨씬 쉽습니다.  
  
 MFC 프로그램 사용 하 여 컨테이너 만들기는 [MFC 응용 프로그램 마법사](../../mfc/reference/mfc-application-wizard.md) MFC 및 ActiveX 클래스에서 구현 되는 ActiveX 컨트롤 및 자동화의 여러 기능에 액세스할 수 있습니다. 이러한 기능에는 컨트롤에 대 한 지원 및 시각적 편집, 자동화, 복합 파일 만들기, 포함 됩니다. 부모 프로그램에서 지 원하는 MFC 응용 프로그램 마법사 시각적 편집 옵션의 컨테이너, 미니 서버, 전체 서버 및 컨테이너와 서버 둘 다 있는 프로그램 만들기를 포함 합니다.  
  
-   **새 MFC 응용 프로그램**합니다. 자동화를 포함 하는 새 MFC 프로그램을 만들려면 비주얼 편집 복합 파일 또는 제어 지원, MFC 응용 프로그램 마법사를 사용 하 고 적절 한 자동화 옵션 선택 합니다.  
  
-   **기존 MFC 응용 프로그램**합니다. 기존 MFC 응용 프로그램에 컨트롤 포함 기능을 추가 하는 경우 참조 [OLE 컨트롤 컨테이너: OLE 컨트롤 포함 기능 수동으로 활성화](../../mfc/activex-control-containers-manually-enabling-activex-control-containment.md)합니다.  
  
### <a name="to-create-an-activex-container-for-any-of-the-following-types-of-applications"></a>다음과 같은 종류의 응용 프로그램에 대 한 ActiveX 컨테이너를 만들려면  
  
1.  [컨테이너](../../mfc/containers.md)  
  
2.  [비주얼 편집](../../mfc/ole-mfc.md)  
  
3.  [MFC ActiveX 컨트롤](../../mfc/mfc-activex-controls.md)  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++ 프로젝트 형식](../../ide/visual-cpp-project-types.md)

