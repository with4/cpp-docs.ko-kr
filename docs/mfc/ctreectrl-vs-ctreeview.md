---
title: "CTreeCtrl vs입니다. CTreeView | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CTreeCtrl
- CTreeView
dev_langs:
- C++
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bb0c1b7a7bf73ab70bbccca6f2a9ccc2ab385516
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl vs입니다. CTreeView
트리 컨트롤을 캡슐화 하는 두 개의 클래스를 제공 하는 MFC: [CTreeCtrl](../mfc/reference/ctreectrl-class.md) 및 [CTreeView](../mfc/reference/ctreeview-class.md)합니다. 각 클래스는 여러 가지 상황에서 유용 합니다.  
  
 사용 하 여 `CTreeCtrl` 일반 자식 창 컨트롤; 필요할 때 대화 상자에서 예를 들어, 합니다. 사용 하려는 특히 `CTreeCtrl` 경우 일반 대화 상자 창에 다른 자식 컨트롤이 됩니다.  
  
 사용 하 여 `CTreeView` 하려는 경우 문서/뷰 아키텍처의 뷰 창과 처럼 동작할 수 트리 컨트롤 및 트리 컨트롤입니다. A `CTreeView` 프레임 창이 또는 분할자 창의 전체 클라이언트 영역을 차지 합니다. 이 자동으로 크기가 조정 됩니다 부모 창의 크기를 조정 하 고, 메뉴, 액셀러레이터 키 및 도구 모음에서 명령 메시지를 처리할 수 있습니다. 트리 컨트롤의 트리를 표시 하는 데 필요한 데이터가 들어 있으므로 해당 문서 개체 복잡 해질 수 않아도-도 사용할 수 있습니다 [CDocument](../mfc/reference/cdocument-class.md) 문서 서식 파일에서 문서 유형으로 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

