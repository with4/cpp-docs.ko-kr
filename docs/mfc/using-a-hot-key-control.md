---
title: "바로 가기 키 컨트롤을 사용 하 여 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 016243de093ced7483506068e6e6478c024b07d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="using-a-hot-key-control"></a>바로 가기 키 컨트롤 사용
바로 가기 키 컨트롤의 일반적인 사용 패턴을 따릅니다.  
  
-   컨트롤이 만들어집니다. 컨트롤이 대화 상자 템플릿에 지정될 경우 대화 상자를 만들 때 자동으로 만들어집니다. (있어야는 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) 바로 가기 키 컨트롤에 해당 하는 대화 상자 클래스의 멤버입니다.) 사용할 수 있습니다는 [만들기](../mfc/reference/chotkeyctrl-class.md#create) 멤버 함수 모든 창의 자식 창으로 컨트롤을 만들 수 있습니다.  
  
-   컨트롤에 대 한 기본값을 설정 하려는 경우 호출 된 [SetHotKey](../mfc/reference/chotkeyctrl-class.md#sethotkey) 멤버 함수입니다. 특정 상태 전환이 (를) 금지 하려면 호출 [SetRules](../mfc/reference/chotkeyctrl-class.md#setrules)합니다. 대화 상자에서 컨트롤에 대 한 대화 상자에서이 작업을 수행 하는 데 좋은 시간이 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 함수입니다.  
  
-   바로 가기 키 컨트롤에 포커스가 있을 때 바로 가기 키 조합 키를 눌러 컨트롤에서 사용자 상호 작용 합니다. 사용자 다음 나타냅니다이 작업이 완료 되었음을, 아마도 대화 상자에서 단추를 클릭 하 여 합니다.  
  
-   멤버 함수를 사용 해야 사용자가 바로 가기 키를 선택 하면 프로그램에서 알림을 때 [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) 바로 가기 키 컨트롤에서 가상 키 및 shift 상태 값을 검색 합니다.  
  
-   에 설명 된 방법 중 하나를 사용 하 여 바로 가기 키를 설정할 수는 사용자가 선택한 키 것을 알고 있다면 [바로 가기 키 설정](../mfc/setting-a-hot-key.md)합니다.  
  
-   대화 상자에서이 바로 가기 키 컨트롤 것 및 `CHotKeyCtrl` 개체는 자동으로 제거 됩니다. 그렇지 않은 경우 컨트롤 및 `CHotKeyCtrl` 개체가 모두 제대로 소멸되었는지 확인해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CHotKeyCtrl 사용](../mfc/using-chotkeyctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

