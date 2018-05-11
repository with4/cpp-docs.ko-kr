---
title: '끌어서 놓기: 놓기 소스 구현 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE drag and drop [MFC], initiating drag operations
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], drop source
- OLE drag and drop [MFC], calling DoDragDrop
- drag and drop [MFC], initiating drag operations
- drag and drop [MFC], drop source
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c057657605296b3ba65128f26b25aa526f45b211
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="drag-and-drop-implementing-a-drop-source"></a>끌어서 놓기: 놓기 소스 구현
이 문서에는 응용 프로그램 데이터를 끌어서 놓기 작업을 제공 하도록 하는 방법을 설명 합니다.  
  
 놓기 소스의 기본 구현을 비교적 간단 합니다. 첫 번째 단계는 끌기 작업을 시작 하는 이벤트를 결정 하는 것입니다. 사용자 인터페이스 지침 데이터의 선택으로 끌기 작업의 시작 부분을 정의 하는 것이 좋습니다. 및 `WM_LBUTTONDOWN` 선택한 데이터 내부의 한 지점에서 발생 하는 이벤트입니다. MFC OLE 샘플 [OCLIENT](../visual-cpp-samples.md) 및 [HIERSVR](../visual-cpp-samples.md) 다음이 지침을 따릅니다.  
  
 응용 프로그램은 컨테이너 이며 선택된 된 데이터에 연결 되어 또는 포함 된 형식의 개체 `COleClientItem`, 호출 해당 `DoDragDrop` 멤버 함수입니다. 그렇지 않은 경우 생성 된 `COleDataSource` 개체 하 고, 선택 영역을 사용 하 여 초기화 한 다음 데이터 원본 개체를 호출 `DoDragDrop` 멤버 함수입니다. 서버 응용 프로그램을 사용 하는 경우 사용 하 여 `COleServerItem::DoDragDrop`합니다. 표준 끌어서 놓기 동작을 사용자 지정 하는 방법에 대 한 내용은 문서 참조 [끌어서 놓기: 사용자 지정](../mfc/drag-and-drop-customizing.md)합니다.  
  
 경우 `DoDragDrop` 반환 `DROPEFFECT_MOVE`, 소스 문서에서 원본 데이터를 즉시 삭제 합니다. 다른 반환 값 없음 `DoDragDrop` 놓기 소스에 적용 합니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [놓기 대상 구현](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [사용자 지정 끌어서 놓기](../mfc/drag-and-drop-customizing.md)  
  
-   [만들고 OLE 데이터 개체 및 데이터 소스 제거](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [OLE 데이터 개체 및 데이터 소스 조작](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="see-also"></a>참고 항목  
 [끌어서 놓기 (OLE)](../mfc/drag-and-drop-ole.md)   
 [Coledatasource:: Dodragdrop](../mfc/reference/coledatasource-class.md#dodragdrop)   
 [COleClientItem::DoDragDrop](../mfc/reference/coleclientitem-class.md#dodragdrop)   
 [CView::OnDragLeave](../mfc/reference/cview-class.md#ondragleave)

