---
title: "슬라이더 컨트롤을 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4fdab6a7fae25845da81ee7263e045e50951f557
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-slider-controls"></a>슬라이더 컨트롤 사용
슬라이더 컨트롤의 일반적인 사용은 아래의 패턴을 따릅니다.  
  
-   컨트롤이 만들어집니다. 컨트롤이 대화 상자 템플릿에 지정될 경우 대화 상자를 만들 때 자동으로 만들어집니다. (있어야는 [CSliderCtrl](../mfc/reference/csliderctrl-class.md) 슬라이더 컨트롤에 해당 하는 대화 상자 클래스의 멤버입니다.) 사용할 수 있습니다는 [만들기](../mfc/reference/csliderctrl-class.md#create) 멤버 함수 모든 창의 자식 창으로 컨트롤을 만들 수 있습니다.  
  
-   다양한 Set 멤버 함수를 호출하여 컨트롤에 대한 값을 설정합니다. 슬라이더에 대한 최소 및 최대 위치 설정, 눈금 표시 그리기, 선택 범위 설정 및 슬라이더 위치 조정을 변경할 수 있습니다. 대화 상자에서 컨트롤에 대 한이 작업을 수행 하는 데 좋은 시간이 중인 대화 상자의 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 함수입니다.  
  
-   사용자가 컨트롤과 상호 작용하여 다양한 알림 메시지가 전송됩니다. 호출 하 여 컨트롤에서 슬라이더 값을 추출할 수 있습니다는 [GetPos](../mfc/reference/csliderctrl-class.md#getpos) 멤버 함수입니다.  
  
-   컨트롤을 사용하여 작업을 완료한 경우 제대로 제거되었는지 확인해야 합니다. 대화 상자에 슬라이더 컨트롤이 있는 경우 해당 컨트롤 및 `CSliderCtrl` 개체는 자동으로 소멸됩니다. 그렇지 않은 경우 컨트롤 및 `CSliderCtrl` 개체가 모두 제대로 소멸되었는지 확인해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CSliderCtrl 사용](../mfc/using-csliderctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

