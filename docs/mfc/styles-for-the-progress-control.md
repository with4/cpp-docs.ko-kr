---
title: 진행률 컨트롤 스타일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- PBS_SMOOTH style
- progress controls [MFC], styles
- PBS_VERTICAL style
- CProgressCtrl class [MFC], styles
ms.assetid: 39eb8081-bc20-4552-91b9-e7cdd1b7d8ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b29d0df8342ce00a2ddb0d46970d9504a06edd8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956683"
---
# <a name="styles-for-the-progress-control"></a>진행률 컨트롤 스타일
진행률 컨트롤을 처음 만들 ([CProgressCtrl::Create](../mfc/reference/cprogressctrl-class.md#create))를 사용 하 여는 *dwStyle* 매개 변수를 진행률 컨트롤에 대 한 원하는 창 스타일을 지정 합니다. 다음 목록에는 적용 가능한 창 스타일을 자세히 설명합니다. 컨트롤은 여기에 나열 되지 않는 창 스타일을 무시 합니다. 일반적으로 대화 상자 부모의 자식 창으로 컨트롤 항상 만들어야 합니다.  
  
|창 스타일|효과|  
|------------------|------------|  
|WS_BORDER|창 주변의 테두리를 만듭니다.|  
|WS_CHILD|자식 창을 만듭니다. (에 항상 사용할 `CProgressCtrl`).|  
|WS_CLIPCHILDREN|부모 창 내에서 그릴 때 자식 창으로 사용 하는 영역을 제외 합니다. 부모 창을 만들 때 사용 합니다.|  
|WS_CLIPSIBLINGS|자식 창을 서로 기준으로 자릅니다.|  
|WS_DISABLED|처음부터 사용할 창을 만듭니다.|  
|WS_VISIBLE|처음에 표시 되는 창을 만듭니다.|  
|WS_TABSTOP|사용자가을 이동 하려면 TAB 키를 누를 때 컨트롤이 포커스를 받을 수를 지정 합니다.|  
  
 또한, 두 가지 스타일은 진행률 컨트롤에만 적용 되 PBS_VERTICAL 및 PBS_SMOOTH를 지정할 수 있습니다.  
  
 PBS_VERTICAL를 사용 하 여 가로 대신을 세로로 컨트롤 방향을 지정 합니다. PBS_SMOOTH를 사용 하 여 증분 방식으로 컨트롤을 작성 하는 작은 점으로 구분 된 사각형을 표시 하는 대신 컨트롤을 완전히 채웁니다.  
  
 PBS_SMOOTH 스타일 없이:  
  
 ![표준 진행률 막대 스타일](../mfc/media/vc4ruw1.gif "vc4ruw1")  
  
 PBS_SMOOTH 및 PBS_VERTICAL 스타일:  
  
 ![진행률 막대 스타일, 부드러운 및 세로](../mfc/media/vc4ruw2.gif "vc4ruw2")  
  
 자세한 내용은 참조 [창 스타일](../mfc/reference/styles-used-by-mfc.md#frame-window-styles-mfc) 에 *MFC 참조*합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CProgressCtrl 사용](../mfc/using-cprogressctrl.md)

