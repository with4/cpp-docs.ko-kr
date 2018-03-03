---
title: "트리 컨트롤 스타일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- TVS_SINGLEEXPAND
- TVS_LINESATROOT
- TVS_HASBUTTONS
- TVS_NOTOOLTIPS
- TVS_HASLINES
dev_langs:
- C++
helpviewer_keywords:
- TVS_LINESATROOT [MFC]
- styles [MFC], CTreeCtrl
- styles [MFC], tree control
- TVS_HASLINES
- TVS_SINGLEEXPAND
- CTreeCtrl class [MFC], styles
- TVS_EDITLABELS [MFC]
- TVS_NOTOOLTIPS [MFC]
- TVS_HASBUTTONS [MFC]
- tree controls [MFC], styles
ms.assetid: f43faebd-a355-479e-888a-bf0673d5e1b4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c141a2b0db673f8d3c5f2c116de5b5d2ec81a8ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-styles"></a>트리 컨트롤 스타일
Tree 컨트롤 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 스타일 트리 컨트롤의 모양을 제어 합니다. 트리 컨트롤을 만들 때 초기 스타일을 설정 합니다. 검색 하 고 사용 하 여 트리 컨트롤을 만든 후 스타일을 변경할 수는 [GetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633584) 및 [SetWindowLong](http://msdn.microsoft.com/library/windows/desktop/ms633591) 지정 하는 Windows 기능의 **GWL_STYLE** 에 대 한 `nIndex` 매개 변수입니다. 스타일의 전체 목록은 참조 하십시오. [트리 뷰 컨트롤 창 스타일](http://msdn.microsoft.com/library/windows/desktop/bb760013) Windows sdk에서입니다.  
  
 **TVS_HASLINES** 스타일 자식 항목을 해당 부모 항목에 연결 하는 선을 그려 트리 컨트롤의 계층 구조를 그래픽으로 나타낸을 향상 시킵니다. 이 스타일 계층의 루트에 있는 항목을 연결 하지 않습니다. 이렇게 하려면 결합 해야는 **TVS_HASLINES** 및 **TVS_LINESATROOT** 스타일입니다.  
  
 사용자 수 목록을 확장 하거나 축소 부모 항목의 자식 항목의 부모 항목을 두 번 클릭 합니다. 가 있는 트리 컨트롤의 **TVS_SINGLEEXPAND** 스타일 하면이 항목이 확장 선택 되 고 축소 하려면 선택 취소 되 고 항목입니다. 선택한 항목을 한 번 클릭 합니다. 마우스를 사용 하는 경우 해당 항목이 닫혀 확장 됩니다. 선택한 항목은 한 번 클릭 열려 있으면를 축소 합니다.  
  
 가 있는 트리 컨트롤의 **TVS_HASBUTTONS** 스타일의 각 부모 항목 왼쪽에 단추를 추가 합니다. 확장 하거나 부모 항목을 두 번 클릭 하는 대신 하위 항목 축소 단추를 클릭할 수 있습니다. **TVS_HASBUTTONS** 계층의 루트에 있는 항목에 단추를 추가 하지 않습니다. 이렇게 하려면 결합 해야 **TVS_HASLINES**, **TVS_LINESATROOT**, 및 **TVS_HASBUTTONS**합니다.  
  
 **TVS_EDITLABELS** 스타일을 사용 하면 트리 컨트롤 항목의 레이블을 편집 하 여 사용자에 대 한 수입니다. 레이블 편집 하는 방법에 대 한 자세한 내용은 참조 [트리 컨트롤 레이블 편집](../mfc/tree-control-label-editing.md) 이 항목의 뒷부분에 나오는 합니다.  
  
 **TVS_NOTOOLTIPS** 스타일 트리 뷰 컨트롤의 자동 도구 설명 기능을 해제 합니다. 이 기능에는 자동으로 전체 제목이 현재 표시 되지 않는 경우 마우스 커서 아래 항목의 제목을 포함 하는 도구 설명이 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

