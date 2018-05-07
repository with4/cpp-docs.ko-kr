---
title: 이미지 목록 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], creating image lists for
- image lists [MFC], creating for CListCtrl
- lists [MFC], image
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e5f5ac8396c32e56e4c0f2f951f45bb33714822
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="creating-the-image-lists"></a>이미지 목록 만들기
사용 하 든 동일는 이미지 목록 만들기 [CListView](../mfc/reference/clistview-class.md) 또는 [CListCtrl](../mfc/reference/clistctrl-class.md)합니다.  
  
> [!NOTE]
>  만 필요 이미지 목록은 목록 컨트롤에 포함 된 경우는 `LVS_ICON` 스타일입니다.  
  
 클래스를 사용 하 여 `CImageList` (큰 아이콘, 작은 아이콘 및 상태)에 하나 이상의 이미지 목록을 만들 수 있습니다. 참조 [CImageList](../mfc/reference/cimagelist-class.md), 참조 및 [목록 뷰 이미지 나열](http://msdn.microsoft.com/library/windows/desktop/bb774736) Windows sdk에서입니다.  
  
 호출 [CListCtrl::SetImageList](../mfc/reference/clistctrl-class.md#setimagelist) 각각에 대 한 이미지 목록입니다; 적절 한 포인터를 전달 `CImageList` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

