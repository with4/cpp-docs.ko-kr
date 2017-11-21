---
title: "헤더 컨트롤에 항목 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 792c956d73808ef50308f8e14066f74021cc84b8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="adding-items-to-the-header-control"></a>헤더 컨트롤에 항목 추가
헤더 컨트롤을 만든 후 ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md))의 부모 창에서 항목을 추가할 "헤더" 필요에 따라: 열당 하나씩 일반적으로 합니다.  
  
### <a name="to-add-a-header-item"></a>헤더 항목을 추가 하려면  
  
1.  준비 된 [HD_ITEM](http://msdn.microsoft.com/library/windows/desktop/bb775247) 구조입니다.  
  
2.  호출 [CHeaderCtrl::InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem), 구조를 전달 합니다.  
  
3.  추가 항목에 대 한 1 및 2 단계를 반복 합니다.  
  
 자세한 내용은 참조 [헤더 컨트롤에 항목 추가](http://msdn.microsoft.com/library/windows/desktop/bb775238) Windows sdk에서입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

