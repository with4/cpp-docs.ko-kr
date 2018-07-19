---
title: 애니메이션 컨트롤 사용 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], animation
- CAnimateCtrl class [MFC], animation controls
- animation controls [MFC]
ms.assetid: a009a464-e12d-4112-bf52-04a09b28dd88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d6b6b07040fbece5fae24fb2ca6be8985695eb0
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950539"
---
# <a name="using-an-animation-control"></a>애니메이션 컨트롤 사용
애니메이션 컨트롤의 일반적인 사용 패턴을 따릅니다.  
  
-   컨트롤이 만들어집니다. 컨트롤이 대화 상자 템플릿에 지정될 경우 대화 상자를 만들 때 자동으로 만들어집니다. (있어야는 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md) 애니메이션 컨트롤에 해당 하는 대화 상자 클래스의 멤버입니다.) 사용할 수 있습니다는 [만들기](../mfc/reference/canimatectrl-class.md#create) 멤버 함수 모든 창의 자식 창으로 컨트롤을 만들 수 있습니다.  
  
-   AVI 클립을 호출 하 여 애니메이션 컨트롤에 로드 된 [열려](../mfc/reference/canimatectrl-class.md#open) 멤버 함수입니다. 이 작업을 수행 하려면 먼저 대화 상자 클래스에는 컨트롤이 해당 애니메이션 컨트롤이 대화 상자에 포함 된 경우 [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 함수입니다.  
  
-   클립을 호출 하 여 재생는 [재생](../mfc/reference/canimatectrl-class.md#play) 멤버 함수입니다. 이 작업을 수행 하려면 먼저 대화 상자 클래스에는 컨트롤이 해당 애니메이션 컨트롤이 대화 상자에 포함 된 경우 `OnInitDialog` 함수입니다. 호출 `Play` 애니메이션 컨트롤에 설정 된 ACS_AUTOPLAY 스타일 경우 필요 하지 않습니다.  
  
-   클립의 일부를 표시 하거나 프레임별으로 사용 하 여 재생 하려는 경우는 `Seek` 멤버 함수입니다. 클립의 재생을 중지 하려면 사용 된 `Stop` 멤버 함수입니다.  
  
-   컨트롤을 즉시 삭제 하지 않을 경우 클립 메모리에서 호출 하 여 제거는 `Close` 멤버 함수입니다.  
  
-   애니메이션 컨트롤이 대화 상자에 있으면이 고 `CAnimateCtrl` 개체는 자동으로 제거 됩니다. 그렇지 않은 경우 컨트롤 및 `CAnimateCtrl` 개체가 모두 제대로 소멸되었는지 확인해야 합니다. 컨트롤을 자동으로 제거 AVI 클립을 닫습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CAnimateCtrl 사용](../mfc/using-canimatectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

