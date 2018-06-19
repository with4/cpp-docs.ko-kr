---
title: 헤더 항목에 대 한 끌어서 놓기 지원 제공 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50cd19d4828269d0591afd0b46768e9917b96906
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349346"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>헤더 항목에 대한 끌어서 놓기 지원 제공
헤더 항목에 대 한 끌어서 놓기 지원 제공 하려면 지정 된 `HDS_DRAGDROP` 스타일입니다. 헤더 항목에 대 한 끌어서 놓기 지원 사용자의 헤더 컨트롤의 헤더 항목의 순서는 기능을 제공 합니다. 기본 동작 헤더 항목을 삭제할 경우 끌고 헤더 항목의 반투명 끌기 이미지 및 새 위치를 나타내는 시각적 표시기를 제공 합니다.  
  
 일반적인 끌어서 놓기 기능을 처리 하 여 기본 끌어서 놓기 동작을 확장할 수 있습니다 때는 **HDN_BEGINDRAG** 및 **HDN_ENDDRAG** 알림입니다. 재정의 하 여 끌기 이미지의 모양을 사용자 지정할 수도 있습니다는 [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage) 멤버 함수입니다.  
  
> [!NOTE]
>  목록 컨트롤에는 포함 된 헤더 컨트롤에 대 한 끌어서 놓기 지원 제공 하는 경우의 스타일 확장 섹션을 참조는 [목록 컨트롤 스타일 변경](../mfc/changing-list-control-styles.md) 항목입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CHeaderCtrl 사용](../mfc/using-cheaderctrl.md)

