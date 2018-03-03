---
title: "애니메이션 컨트롤 사용 | Microsoft Docs"
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
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 38523c832f4a30f247bd3e1d0b8318f44f5c47b0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-animation-control"></a>애니메이션 컨트롤 사용
애니메이션 컨트롤의 일반적인 사용 패턴을 따릅니다.  
  
-   컨트롤이 만들어집니다. 컨트롤이 대화 상자 템플릿에 지정될 경우 대화 상자를 만들 때 자동으로 만들어집니다. (있어야는 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) 애니메이션 컨트롤에 해당 하는 대화 상자 클래스의 멤버입니다.) 사용할 수 있습니다는 [만들기](../mfc/reference/canimatectrl-class.md#create) 멤버 함수 모든 창의 자식 창으로 컨트롤을 만들 수 있습니다.  
  
-   AVI 클립을 호출 하 여 애니메이션 컨트롤에 로드 된 [열려](../mfc/reference/canimatectrl-class.md#open) 멤버 함수입니다. 이 작업을 수행 하려면 먼저 대화 상자 클래스에는 컨트롤이 해당 애니메이션 컨트롤이 대화 상자에 포함 된 경우 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 함수입니다.  
  
-   클립을 호출 하 여 재생는 [재생](../mfc/reference/canimatectrl-class.md#play) 멤버 함수입니다. 이 작업을 수행 하려면 먼저 대화 상자 클래스에는 컨트롤이 해당 애니메이션 컨트롤이 대화 상자에 포함 된 경우 **OnInitDialog** 함수입니다. 호출 **재생** 애니메이션 컨트롤에 있는 경우에 필요 하지 않습니다는 `ACS_AUTOPLAY` 스타일을 설정 합니다.  
  
-   클립의 일부를 표시 하거나 프레임별으로 사용 하 여 재생 하려는 경우는 `Seek` 멤버 함수입니다. 클립의 재생을 중지 하려면 사용 된 `Stop` 멤버 함수입니다.  
  
-   컨트롤을 즉시 삭제 하지 않을 경우 클립 메모리에서 호출 하 여 제거는 **닫기** 멤버 함수입니다.  
  
-   애니메이션 컨트롤이 대화 상자에 있으면이 고 `CAnimateCtrl` 개체는 자동으로 제거 됩니다. 그렇지 않은 경우 컨트롤 및 `CAnimateCtrl` 개체가 모두 제대로 소멸되었는지 확인해야 합니다. 컨트롤을 자동으로 제거 AVI 클립을 닫습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAnimateCtrl 사용](../mfc/using-canimatectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

