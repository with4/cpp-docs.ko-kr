---
title: "트리 컨트롤과 통신 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 33835dcaa40b217e9248e5c03b775f968332b687
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="communicating-with-a-tree-control"></a>트리 컨트롤과 통신
멤버 함수를 호출 하는 것에 대 한 다양 한 방법을 사용 하면 한 [CTreeCtrl](../mfc/reference/ctreectrl-class.md) 개체가 생성 된 방식에 따라 개체:  
  
-   형식의 멤버 변수를 사용 하 여 트리 컨트롤이 대화 상자에 포함 된 경우 `CTreeCtrl` 대화 상자 클래스에서 만드는 합니다.  
  
-   자식 창 트리 컨트롤을 사용 하는 경우 사용 하 여는 `CTreeCtrl` 개체를 생성 하는 데 개체 (또는 포인터).  
  
-   사용 중인 경우는 `CTreeView` 개체, 함수를 사용 하 여 [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) 트리 컨트롤에 대 한 참조를 얻으려고 합니다. 이 값과 다른 참조를 초기화 하거나에 대 한 참조의 주소를 할당할 수는 `CTreeCtrl` 포인터입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

