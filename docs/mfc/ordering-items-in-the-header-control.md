---
title: 헤더 컨트롤에서 항목을 주문 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- DS_DRAGDROP
dev_langs:
- C++
helpviewer_keywords:
- sequence [MFC]
- sequence [MFC], header control items
- OrderToIndex method [MFC]
- DS_DRAGDROP notification [MFC]
- GetOrderArray method [MFC]
- SetOrderArray method [MFC]
- header controls [MFC], ordering items
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aac3c9ba284abc634af2fbeb25633b812e07f926
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928572"
---
# <a name="ordering-items-in-the-header-control"></a>헤더 컨트롤에서 항목 순서 지정
한 후 [헤더 컨트롤에 항목 추가](../mfc/adding-items-to-the-header-control.md)를 조작 하거나 다음 함수를 사용 하 여 순서에 대 한 정보를 가져올 수 있습니다.  
  
-   [CHeaderCtrl::GetOrderArray](../mfc/reference/cheaderctrl-class.md#getorderarray) 및 [CHeaderCtrl::SetOrderArray](../mfc/reference/cheaderctrl-class.md#setorderarray)  
  
     검색 하 고 헤더 항목의 왼쪽-오른쪽 순서를 설정 합니다.  
  
-   [CHeaderCtrl::OrderToIndex](../mfc/reference/cheaderctrl-class.md#ordertoindex)합니다.  
  
     특정 헤더 항목에 대 한 인덱스 값을 검색합니다.  
  
 이전 멤버 함수 이외에도 HDS_DRAGDROP 스타일에는 머리글 항목 헤더 컨트롤에서 끌어서 사용자 수 있습니다. 자세한 내용은 참조 [헤더 항목에 대 한 끌어서 놓기 지원 제공](../mfc/providing-drag-and-drop-support-for-header-items.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)

