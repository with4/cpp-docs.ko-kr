---
title: 대화 상자 모음 Rebar 컨트롤 함께 사용 하 여 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- WM_EX_TRANSPARENT
dev_langs:
- C++
helpviewer_keywords:
- WS_EX_TRANSPARENT style
- rebar controls [MFC], dialog bars
- dialog bars [MFC], using with rebar bands
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47894c14e3b3d694847f94e7f981c9397383e598
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382908"
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>대화 상자 모음과 Rebar 컨트롤 함께 사용
설명한 것 처럼 [Rebar 컨트롤 및 밴드](../mfc/rebar-controls-and-bands.md), 각 밴드에는 하나의 자식 창 (또는 컨트롤) 포함 될 수 있습니다. 대역 외 당 둘 이상의 자식 창을 포함 하려는이 제한 될 수 있습니다. 문제를 해결은 여러 컨트롤에 대화 상자 모음 리소스를 만들고 다음 rebar 컨트롤에는 rebar 밴드 (대화 상자 막대 포함)를 추가 합니다.  
  
 일반적으로 투명 하 게 나타내려면 대화 상자 모음 밴드를 려 설정한는 **WS_EX_TRANSPARENT** 확장 대화 상자 모음 개체에 대 한 스타일입니다. 그러나 때문에 **WS_EX_TRANSPARENT** 에 몇 가지 문제가 제대로 대화 상자 막대의 배경색을 칠하지, 원하는 효과 달성 하기 위해 약간의 추가 작업을 수행 해야 합니다.  
  
 다음 절차를 사용 하지 않고 투명도 달성 하는 데 필요한 단계에 자세히는 **WS_EX_TRANSPARENT** 확장 스타일입니다.  
  
### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>Rebar 밴드에서 투명 대화 상자를 구현 하려면  
  
1.  사용 하는 [클래스 추가 대화 상자](../mfc/reference/adding-an-mfc-class.md), 새 클래스 추가 (예를 들어 `CMyDlgBar`) 대화 상자 모음 개체를 구현 하는 합니다.  
  
2.  에 대 한 처리기를 추가 `WM_ERASEBKGND` 메시지입니다.  
  
3.  새 처리기를 다음 예제와 일치 하도록 기존 코드를 수정 합니다.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]  
  
4.  에 대 한 처리기를 추가 `WM_MOVE` 메시지입니다.  
  
5.  새 처리기를 다음 예제와 일치 하도록 기존 코드를 수정 합니다.  
  
     [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]  
  
 전달 하 여 대화 상자 막대의 투명도 시뮬레이션 하는 새 처리기는 `WM_ERASEBKGND` 부모 창에는 메시지 및 대화 상자 막대 개체가 이동 될 때마다 다시 그리기를 강제 적용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CReBarCtrl 사용](../mfc/using-crebarctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

