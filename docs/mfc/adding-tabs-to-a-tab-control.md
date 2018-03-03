---
title: "탭 컨트롤에 탭 추가 | Microsoft Docs"
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
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 46012a265c1ecefa7af63f829be22e6132e036cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-tabs-to-a-tab-control"></a>탭 컨트롤에 탭 추가
탭 컨트롤을 만든 후 ([CTabCtrl](../mfc/reference/ctabctrl-class.md))를 필요한 만큼 많은 탭을 추가 합니다.  
  
### <a name="to-add-a-tab-item"></a>탭 항목을 추가 하려면  
  
1.  준비는 [TCITEM](http://msdn.microsoft.com/library/windows/desktop/bb760554) 구조입니다.  
  
2.  호출 [CTabCtrl::InsertItem](../mfc/reference/ctabctrl-class.md#insertitem), 구조를 전달 합니다.  
  
3.  탭이 추가로 항목에 대 한 1 및 2 단계를 반복 합니다.  
  
 자세한 내용은 참조 [탭 컨트롤을 만드는](http://msdn.microsoft.com/library/windows/desktop/bb760550) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTabCtrl 사용](../mfc/using-ctabctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

