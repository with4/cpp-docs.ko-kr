---
title: 'ActiveX 컨트롤 컨테이너: ActiveX 컨트롤 포함 수동 설정 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- AfxEnableControlContainer method [MFC]
- ActiveX control containers [MFC], enabling
- ActiveX controls [MFC], enabling containers
ms.assetid: 833bcde9-c9ad-4709-ad12-2fc2150fb6a5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fde0ee4dc740826c9efdf7b86cd2f021699f8820
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339893"
---
# <a name="activex-control-containers-manually-enabling-activex-control-containment"></a>ActiveX 컨트롤 컨테이너: ActiveX 컨트롤 포함 수동 설정
MFC 응용 프로그램 마법사를 사용 하 여 응용 프로그램을 생성 하는 경우 ActiveX 컨트롤을 지 원하는 설정 하지 않은 경우에이 지원을 수동으로 추가 해야 합니다. 이 문서에서는 ActiveX 컨트롤을 포함할 기존 OLE 컨테이너 응용 프로그램에 수동으로 추가 하는 것에 대 한 프로세스를 설명 합니다. 사전에 OLE 컨테이너에서 ActiveX 컨트롤을 지 원하는 한다고 알고 있는 경우 문서를 참조 하십시오. [MFC ActiveX 컨트롤 컨테이너 만들기](../mfc/reference/creating-an-mfc-activex-control-container.md)합니다.  
  
> [!NOTE]
>  이 문서는 대화 상자 기반 ActiveX 컨트롤 컨테이너 프로젝트 라는 컨테이너와 절차 및 코드에서 예로 Circ 라는 포함 된 컨트롤을 사용 합니다.  
  
 ActiveX 컨트롤을 지원 하려면 두 프로젝트의 파일에 한 줄의 코드를 추가 해야 합니다.  
  
-   주 대화에 수정 `InitInstance` 함수 (컨테이너에서 찾을 수 있습니다. CPP)를 호출 하는 MFC 응용 프로그램 마법사에서 [AfxEnableControlContainer](reference/ole-initialization.md#afxenablecontrolcontainer)다음 예제와 같이,:  
  
     [!code-cpp[NVC_MFCOleContainer#34](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_1.cpp)]  
    [!code-cpp[NVC_MFCOleContainer#35](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_2.cpp)]  
  
-   다음 프로젝트의 STDAFX을 추가 합니다. H 헤더 파일:  
  
     [!code-cpp[NVC_MFCOleContainer#36](../mfc/codesnippet/cpp/activex-control-containers-manually-enabling-activex-control-containment_3.h)]  
  
 이러한 단계를 완료 한 후을 클릭 하 여 프로젝트를 다시 빌드합니다 **빌드** 에 **빌드** 메뉴.  
  
## <a name="see-also"></a>참고 항목  
 [ActiveX 컨트롤 컨테이너](../mfc/activex-control-containers.md)

