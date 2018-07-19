---
title: 'MFC ActiveX 컨트롤: 스톡 속성 페이지를 사용 하 여 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CLSID_CPicturePropPage
- CLSID_CColorPropPage
- CLSID_CFontPropPage
dev_langs:
- C++
helpviewer_keywords:
- picture stock property pages [MFC]
- CLSID_CFontPropPage [MFC]
- color stock property pages [MFC]
- CLSID_CColorPropPage [MFC]
- fonts [MFC], ActiveX controls
- stock properties [MFC], stock property pages
- CLSID_CPicturePropPage [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 22638d86-ff3e-4124-933e-54b7c2a25968
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5eb8dc1bbdc496072df829531b0f10aaaca069a8
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932197"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>MFC ActiveX 컨트롤: 스톡 속성 페이지 사용
이 문서에서는 ActiveX 컨트롤 및 사용 하는 방법에 사용할 수 있는 스톡 속성 페이지에 설명 합니다.  
  
 ActiveX 컨트롤의 속성 페이지 사용에 대 한 자세한 내용은 다음 문서를 참조 합니다.  
  
-   [MFC ActiveX 컨트롤: 속성 페이지](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [MFC ActiveX 컨트롤: 다른 사용자 지정 속성 페이지 추가](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
 MFC ActiveX 컨트롤 사용 하기 위한 세 가지 스톡 속성 페이지를 제공: `CLSID_CColorPropPage`, `CLSID_CFontPropPage`, 및 `CLSID_CPicturePropPage`합니다. 이러한 페이지는 각각 주식 색, 글꼴 및 그림 속성에 대 한 사용자 인터페이스를 표시 합니다.  
  
 컨트롤에 이러한 속성 페이지를 통합 하려면 컨트롤의 속성 페이지 Id 배열을 초기화 하는 코드를 해당 Id를 추가 합니다. 다음 예제에서는이 코드는 컨트롤 구현 파일에 있는 (합니다. CPP)를 모두 세 개의 스톡 속성 페이지와 기본 속성 페이지를 포함 하도록 배열 초기화 (라는 `CMyPropPage` 이 예에서):  
  
 [!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]  
  
 BEGIN_PROPPAGEIDS 매크로의 속성 페이지의 수는 4를 참고 합니다. 이 ActiveX 컨트롤에서 지 원하는 속성 페이지의 수를 나타냅니다.  
  
 이러한 수정 사항을 적용 된 후 프로젝트를 다시 빌드하십시오. 컨트롤에는 이제 글꼴, 그림 및 색 속성에 대 한 속성 페이지에 있습니다.  
  
> [!NOTE]
>  현재 운영 체제와 MFC DLL (MFCxx.DLL) 제대로 등록 되지 않은 컨트롤 스톡 속성 페이지에 액세스할 수 없는 경우 수 있습니다. 현재 실행 중인 것과에서 다른 운영 체제에서 Visual c + + 설치에서 일반적으로 발생 합니다.  
  
> [!TIP]
>  스톡 속성 페이지에 표시 되지 않는 경우 (이전 참고 참조)를 DLL에 전체 경로 이름 사용 하 여 명령줄에서 RegSvr32.exe를 실행 하 여 DLL을 등록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤](../mfc/mfc-activex-controls.md)   
 [MFC ActiveX 컨트롤: 스톡 속성 추가](../mfc/mfc-activex-controls-adding-stock-properties.md)

