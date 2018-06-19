---
title: 목록 항목 및 이미지 목록 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CImageList class [MFC], and list items
- image lists [MFC], list items
- CListCtrl class [MFC], image lists
- list items [MFC], image lists
ms.assetid: 317d095f-f978-47da-acb6-7bfe7dd3bc69
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f6bd7a97330a8a646a880bf229562dbec9a70181
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349115"
---
# <a name="list-items-and-image-lists"></a>목록 항목 및 이미지 목록
목록 컨트롤에서 "item" ([CListCtrl](../mfc/reference/clistctrl-class.md)) 아이콘, 레이블 및 수 있는 기타 정보 ("하위 항목")를에서 구성 합니다.  
  
 목록 컨트롤 항목에 대 한 아이콘 이미지 목록에 포함 되어 있습니다. 하나의 이미지 목록 아이콘 보기에 사용 되는 전체 화면 아이콘을 포함 합니다. 두 번째 (선택 사항) 이미지 목록 컨트롤의 다른 보기에서 사용 하기 위해 같은 아이콘 중 더 작은 버전을 포함합니다. 특정 보기의 작은 아이콘 앞에 표시 하기 위해 확인란과 같은 "state" 이미지를 포함 하는 세 번째 선택적 목록입니다. 목록 컨트롤의 개별 헤더 항목에 표시 되는 이미지를 포함 하는 네 번째 선택적 목록은입니다.  
  
> [!NOTE]
>  Listview 컨트롤을 만든 경우의 `LVS_SHAREIMAGELISTS` 스타일을 담당 하는 경우는 더 이상 사용 중 이미지 목록을 제거 합니다. 여러 목록 보기 컨트롤;에 이미지를 할당 하는 경우에이 스타일 목록을 지정합니다 그렇지 않으면 개 이상의 컨트롤이 동일한 이미지 목록을 삭제 하려고 할 수 있습니다.  
  
 목록 항목에 대 한 자세한 내용은 참조 [목록 뷰 이미지 목록](http://msdn.microsoft.com/library/windows/desktop/bb774736) 및 [항목과 하위 항목이](http://msdn.microsoft.com/library/windows/desktop/bb774736) Windows sdk에서입니다. 또한 클래스를 참조 하십시오. [CImageList](../mfc/reference/cimagelist-class.md) 에 *MFC 참조* 및 [CImageList 사용 하 여](../mfc/using-cimagelist.md) 이의 문서에 있습니다.  
  
 목록 컨트롤을 만들려면 목록에 새 항목을 삽입할 때 사용 되는 이미지 목록을 제공 해야 합니다. 다음 예제에서는이 절차를 보여 줍니다. 여기서 `m_pImagelist` 형식의 포인터는 `CImageList` 및 `m_listctrl` 는 `CListCtrl` 데이터 멤버입니다.  
  
 [!code-cpp[NVC_MFCControlLadenDialog#19](../mfc/codesnippet/cpp/list-items-and-image-lists_1.cpp)]  
  
 그러나 목록 뷰 또는 목록 컨트롤에 아이콘을 표시 하지 않으려는 경우 이미지 목록 필요는 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 [CListCtrl 사용](../mfc/using-clistctrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

