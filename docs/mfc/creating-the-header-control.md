---
title: "헤더 컨트롤 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CHeaderCtrl class [MFC], creating
- header controls [MFC], creating
ms.assetid: 7864d9d2-4a2c-4622-b58b-7b110a1e28d2
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c47e458d4cd6e9df556eef5e1f61806633208011
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-the-header-control"></a>헤더 컨트롤 만들기
헤더 컨트롤 (하지만 헤더 컨트롤을 포함 하는 목록 컨트롤을 추가할 수 있습니다) 대화 상자 편집기에서 직접 사용할 수 있는있지 않습니다.  
  
### <a name="to-put-a-header-control-in-a-dialog-box"></a>대화 상자에 헤더 컨트롤을 배치할  
  
1.  형식의 멤버 변수를 수동으로 포함 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) 대화 상자 클래스에 있습니다.  
  
2.  [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog), 만들기 및 설정에 대 한 스타일의 `CHeaderCtrl`, 놓고 표시 합니다.  
  
3.  헤더 컨트롤에 항목을 추가 합니다.  
  
4.  모든 헤더 컨트롤 알림 메시지에 대 한 대화 상자 클래스의 처리기 함수에 매핑할 속성 창에서 처리 해야 하는 사용 하 여 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)).  
  
### <a name="to-put-a-header-control-in-a-view-not-a-clistview"></a>헤더 컨트롤 보기 (하지 CListView)에 넣을 수  
  
1.  포함 된 [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md) 뷰 클래스에는 개체입니다.  
  
2.  스타일, 위치, 및에서 보기의 헤더 컨트롤 창을 표시 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) 멤버 함수입니다.  
  
3.  헤더 컨트롤에 항목을 추가 합니다.  
  
4.  처리기 함수를 매핑합니다 뷰 클래스의 모든 헤더 컨트롤 알림 메시지에 대 한 속성 창에서 처리 해야 하는 사용 하 여 (참조 [함수에 메시지 매핑](../mfc/reference/mapping-messages-to-functions.md)).  
  
 두 경우 모두 포함 된 컨트롤 개체가 뷰 또는 대화 상자 개체를 만들 때 만들어집니다. 다음 호출 해야 [CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create) 컨트롤 창을 만들 수 있습니다. 컨트롤의 위치를 호출 [CHeaderCtrl::Layout](../mfc/reference/cheaderctrl-class.md#layout) 컨트롤의 초기 크기와 위치를 결정 하 고 [SetWindowPos](../mfc/reference/cwnd-class.md#setwindowpos) 원하는 위치를 설정 합니다. 에 설명 된 대로 다음 항목을 추가 [헤더 컨트롤에 항목 추가](../mfc/adding-items-to-the-header-control.md)합니다.  
  
 자세한 내용은 참조 [헤더 컨트롤 만들기](http://msdn.microsoft.com/library/windows/desktop/bb775238) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

