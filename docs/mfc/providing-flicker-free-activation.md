---
title: "깜빡임 없는 활성화 제공 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f14998ce663e5a8e53901acf9192719fa41e724
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="providing-flicker-free-activation"></a>깜빡임 없는 활성화 제공
그리기 작업 및 깜빡임을 비활성 사이 전환할 때는 일반적으로 발생 하는 경우 컨트롤의 비활성 및 활성 상태에서 동일 하 게 자신을 그릴 (창 없는 활성화를 사용 하지 않는)을 제거할 수 있습니다. 및 활성 상태입니다. 이 작업을 수행 하려면 포함 된 **noFlickerActivate** 에서 반환 하는 플래그 집합에서 플래그 [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags)합니다. 예:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]  
  
 선택 하는 경우이 플래그를 포함 하는 코드는 자동으로 생성 됩니다는 **깜빡임 없는 활성화** 옵션에 [제어 설정](../mfc/reference/control-settings-mfc-activex-control-wizard.md) MFC ActiveX 컨트롤 마법사와 컨트롤을 만들 때 페이지.  
  
 창 없는 활성화를 사용 하는 경우이 최적화에 영향을 주지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC ActiveX 컨트롤: 최적화](../mfc/mfc-activex-controls-optimization.md)

