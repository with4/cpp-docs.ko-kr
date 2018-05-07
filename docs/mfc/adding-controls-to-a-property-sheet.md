---
title: 속성 시트에 컨트롤 추가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8437fcdaa04ce7dd2b0a214e4bd3a63ca421d014
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="adding-controls-to-a-property-sheet"></a>속성 시트에 컨트롤 추가
기본적으로 속성 시트의 속성 페이지, 탭 인덱스 및 확인, 취소 및 적용 단추에 대 한 창 영역을 할당합니다. (모덜리스 속성 시트 확인을 취소 하 고 단추를 적용 한 없습니다.) 속성 시트에 다른 컨트롤을 추가할 수 있습니다. 예를 들어 어떤 현재 설정이 다음과 같은 외부 개체에 적용 하는 경우 사용자를 표시 하도록 속성 페이지 영역의 오른쪽에 미리 보기 창에 추가할 수 있습니다.  
  
 컨트롤의 속성 시트 대화 상자에서을 추가할 수는 `OnCreate` 처리기입니다. 일반적으로 추가 제어 기능을 수용 속성 시트 대화 상자 크기를 확장 해야 합니다. 기본 클래스를 호출한 후 **CPropertySheet::OnCreate**, 호출 [GetWindowRect](../mfc/reference/cwnd-class.md#getwindowrect) 확장 사각형의 너비와 높이의 현재 할당 된 속성 시트 창 가져올, 차원 및 호출 [MoveWindow](../mfc/reference/cwnd-class.md#movewindow) 속성 시트 창의 크기를 변경 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 시트](../mfc/property-sheets-mfc.md)   
 [CPropertyPage 클래스](../mfc/reference/cpropertypage-class.md)   
 [CPropertySheet 클래스](../mfc/reference/cpropertysheet-class.md)
