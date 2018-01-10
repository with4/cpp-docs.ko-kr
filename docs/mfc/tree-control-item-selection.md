---
title: "트리 컨트롤 항목 선택 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tree controls [MFC], item selection
- controls [MFC], selecting items in
- CTreeCtrl class [MFC], item selection
- item selection in tree controls
ms.assetid: 7bcb3b16-b9c8-4c06-9350-7bc3c1c5009b
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b38761b27c21dcf0fe3118d5b73e104cbaaa673d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-item-selection"></a>트리 컨트롤 항목 선택
때 선택 한 항목에서 다른 구독으로 변경, 트리 컨트롤 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 보냅니다 [TVN_SELCHANGING](http://msdn.microsoft.com/library/windows/desktop/bb773547) 및 [TVN_SELCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb773544) 알림 메시지입니다. 두 알림에 변경 마우스 클릭 이나 키 입력의 결과 인지를 지정 하는 값을 포함 합니다. 또한 알림에는 선택이 취소 하는 항목 및 선택 영역을 손실 되는 항목에 대 한 정보를 포함 합니다. 항목의 선택 상태에 종속 된 항목 속성을 설정 하려면이 정보를 사용할 수 있습니다. 반환 **TRUE** 대 한 응답으로 **TVN_SELCHANGING** 선택을 변경; 반환 되지 않도록 **FALSE** 변경을 허용 합니다.  
  
 응용 프로그램 호출 하 여 선택을 변경할 수는 [SelectItem](../mfc/reference/ctreectrl-class.md#selectitem) 멤버 함수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

