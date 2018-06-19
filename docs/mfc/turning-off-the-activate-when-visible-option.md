---
title: 때 표시 활성화 옵션 해제 하면 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], activate options
- Activate When Visible option [MFC]
ms.assetid: 8f7ddc5a-a7a6-4da8-bcb9-1b569f0ecb48
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5625e7d05ea09188aaa2ea50ca629204a4bacc07
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384783"
---
# <a name="turning-off-the-activate-when-visible-option"></a>표시되었을 때 활성화 옵션 해제
컨트롤은 활성 및 비활성의 두 가지 기본 상태를 가집니다. 일반적으로 이러한 상태는 컨트롤에 창이 있는지 여부에 따라 구분됩니다. 활성 컨트롤에는 창이 있지만 비활성 컨트롤에는 창이 없습니다. 창 없는 활성화의 도입으로 이러한 구분은 더 이상 일반적이지 않지만 여전히 많은 컨트롤에 적용됩니다.  
  
 일반적으로 ActiveX 컨트롤에 의해 수행 된 초기화의 나머지 부분에 비해 창 만드는 속도가 매우 느린 작업 합니다. 이상적으로 컨트롤 반드시 필요한 경우가 아니면 될 때까지 창을 만들지 않는 것입니다.  
  
 대부분의 컨트롤 컨테이너에 표시 되는 동안 활성화 될 필요가 없습니다. 종종, 컨트롤 사용자 (예: 마우스 클릭 하거나 TAB 키를 누르면) 활성화 되도록 요구 하는 작업을 수행할 때까지 비활성 상태로에 남아 있습니다. 제거를 하 게 고가용성을 달성 하려면 컨테이너 필요할 때까지 비활성 상태로 유지 하는 컨트롤의 **OLEMISC_ACTIVATEWHENVISIBLE** 컨트롤의 기타 플래그의 플래그:  
  
 [!code-cpp[NVC_MFC_AxOpt#9](../mfc/codesnippet/cpp/turning-off-the-activate-when-visible-option_1.cpp)]  
  
 **OLEMISC_ACTIVATEWHENVISIBLE** 플래그를 해제 하면 생략 하면 자동으로 **활성화 보이는** 옵션에 [제어 설정](../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC ActiveX의 페이지 컨트롤을 만들 때 마법사를 제어 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)

