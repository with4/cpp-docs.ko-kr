---
title: 트리 컨트롤 이미지 목록 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- images [MFC], lists in tree controls
- tree controls [MFC], image lists
- CTreeCtrl class [MFC], image lists
ms.assetid: f560c4f2-20d2-4d28-ac33-4017e65fb0a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef74b656cc85fbdcc29c7965b9398a5cbd2f44e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="tree-control-image-lists"></a>트리 컨트롤 이미지 목록
트리 컨트롤의 각 항목 ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) 연결 된 비트맵 이미지의 쌍을 가질 수 있습니다. 이미지 항목의 레이블 왼쪽에 나타납니다. 항목을 선택 하 고 항목을 선택 하지 않은 경우 표시 되 면 다른 한 이미지가 표시 됩니다. 예를 들어 항목 선택 하지 않으면 열린 폴더를 선택 하 고 닫혀 있는 폴더가 표시할 수 있습니다.  
  
 항목 이미지를 사용 하려면 만들어야 이미지 목록을 구성 하 여는 [CImageList](../mfc/reference/cimagelist-class.md) 개체와 사용 하는 [CImageList::Create](../mfc/reference/cimagelist-class.md#create) 연결 된 이미지 목록을 만들 함수입니다. 그런 다음 목록에 원하는 비트맵을 추가 하 고 트리 컨트롤 목록을 사용 하 여 연결 된 [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist) 멤버 함수입니다. 기본적으로 모든 항목이 선택 되 고 선택 되지 않은 상태에 대 한 이미지 목록에서 첫 번째 이미지를 표시 합니다. 사용 하 여 트리 컨트롤 항목을 추가할 때 선택 되 고 선택 되지 않은 이미지의 인덱스를 지정 하 여 특정 항목에 대 한 기본 동작을 변경할 수는 [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) 멤버 함수입니다. 사용 하 여 항목을 추가한 후 인덱스를 변경할 수는 [SetItemImage](../mfc/reference/ctreectrl-class.md#setitemimage) 멤버 함수입니다.  
  
 트리 컨트롤 이미지 목록 항목 이미지 위에 놓을 수 있도록 설계 된 오버레이 이미지를 포함할 수도 있습니다. 오버레이 이미지의 1부터 시작 인덱스를 지정 하는 8에서 11 비트 트리 컨트롤 항목 상태에에서 0이 아닌 값 (0는 오버레이 이미지가 없음을 나타냄). 4 비트, 1부터 시작 하는 인덱스를 사용 하기 때문에 오버레이 이미지는 이미지 목록에서 처음 15 이미지 중 하나 여야 합니다. 트리 컨트롤 항목 상태에 대 한 자세한 내용은 참조 [트리 컨트롤 항목 상태 개요](../mfc/tree-control-item-states-overview.md) 이 항목의에서 앞부분입니다.  
  
 상태 이미지 목록을 지정 하는 경우 트리 컨트롤 상태 이미지에 대 한 각 항목의 아이콘의 왼쪽에는 공간을 예약 합니다. 응용 프로그램 정의 항목 상태를 나타낼 수 상태 이미지를 선택 및 선택이 취소 확인란을 사용할 수 있습니다. 상태 이미지의 1부터 시작 하는 인덱스를 지정 하는 12-15 비트에서 0이 아닌 값 (0은 없음 상태 이미지를 나타냄).  
  
 지정 하 여는 **I_IMAGECALLBACK** 값 대신 이미지의 인덱스를 지연 시킬 수 있습니다는 항목에 대 한 다시 그려야 하는 때까지 선택 되거나 선택 하지 않은 이미지를 지정 합니다. **I_IMAGECALLBACK** 전송 하 여 인덱스에 대 한 응용 프로그램을 쿼리 하는 트리 컨트롤이 보냅니다는 [TVN_GETDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773518) 알림 메시지입니다.  
  
 [GetImageList](../mfc/reference/ctreectrl-class.md#getimagelist) 멤버 함수는 트리 컨트롤 이미지 목록의 핸들을 검색 합니다. 이 함수는 목록에 이미지를 추가 해야 할 경우에 유용 합니다. 이미지 목록에 대 한 자세한 내용은 참조 [CImageList 사용 하 여](../mfc/using-cimagelist.md), [CImageList](../mfc/reference/cimagelist-class.md) 에 *MFC 참조*, 및 [이미지 목록](http://msdn.microsoft.com/library/windows/desktop/bb761389) 에 Windows SDK입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CTreeCtrl 사용](../mfc/using-ctreectrl.md)   
 [컨트롤](../mfc/controls-mfc.md)

