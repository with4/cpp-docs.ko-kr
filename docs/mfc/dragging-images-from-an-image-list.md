---
title: "이미지 목록에서 이미지 끌기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CImageList class [MFC], dragging images from
- dragging images from image lists [MFC]
- image lists [MFC], dragging images from
- images [MFC], dragging from image lists
ms.assetid: af691db8-e4f0-4046-b7b9-9acc68d3713d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ae41d50f227c2fa70091aee4e17bf28a40a9b287
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="dragging-images-from-an-image-list"></a>이미지 목록에서 이미지 끌기
[CImageList](../mfc/reference/cimagelist-class.md) 화면에 이미지를 끌어 올 함수가 포함 됩니다. 끌기 함수가 컬러 상태로 커서의 깜빡임 없이 이미지를 원활 하 게 이동합니다. 마스크 및 마스크 해제 된 이미지를 끌 수 있습니다.  
  
 [먼저 BeginDrag](../mfc/reference/cimagelist-class.md#begindrag) 멤버 함수는 끌기 작업을 시작 합니다. 매개 변수는 이미지 내 핫 스폿 위치과 끌어 이미지의 인덱스를 포함 합니다. 핫 스폿 이미지의 정확한 화면 위치로 끌기 함수가 인식 하는 단일 픽셀입니다. 일반적으로 응용 프로그램 마우스 커서의 핫 스폿과 일치 되도록 핫 스폿 설정 합니다. [DragMove](../mfc/reference/cimagelist-class.md#dragmove) 멤버 함수는 이미지를 새 위치로 이동 합니다.  
  
 [수행](../mfc/reference/cimagelist-class.md#dragenter) 멤버 함수는 창 내에서 끌기 이미지의 초기 위치를 설정 하 고 위치에서 이미지를 그립니다. 매개 변수를 이미지와 창 내에서 처음 위치 좌표를 지정 하는 지점을 그릴 창에 대 한 포인터를 포함 합니다. 좌표는 클라이언트 영역이 아니라 창의 왼쪽 위 모퉁이 기준으로 합니다. 모든 좌표를 매개 변수로 사용 하는 이미지 끌기 함수에도 마찬가지입니다. 즉, 좌표를 지정 하는 경우의 테두리, 제목 표시줄 및 메뉴 모음 같은 창 요소의 너비에 대 한 보완 해야 합니다. 지정 하는 경우는 **NULL** 창 핸들을 호출할 때 `DragEnter`, 끌기 함수가 바탕 화면 창와 연결 된 장치 컨텍스트에 이미지를 그리기 및 좌표는 화면의 왼쪽 위 모퉁이 기준으로 합니다.  
  
 `DragEnter`끌기 작업 중 지정된 된 창에 다른 모든 업데이트를 잠급니다. 끌어서 놓기 작업의 대상 강조 하는 등의 끌기 작업 중에 그리기를 수행 해야 할 경우 임시로 숨길 수 있습니다 끌어온된 이미지를 사용 하 여는 [현재의](../mfc/reference/cimagelist-class.md#dragleave) 멤버 함수입니다. 사용할 수도 있습니다는 [DragShowNoLock](../mfc/reference/cimagelist-class.md#dragshownolock) 멤버 함수입니다.  
  
 호출 [EndDrag](../mfc/reference/cimagelist-class.md#enddrag) 완료 하면 이미지를 끌기 합니다.  
  
 [SetDragCursorImage](../mfc/reference/cimagelist-class.md#setdragcursorimage) 멤버 함수는 지정 된 이미지 (일반적으로 마우스 커서 이미지) 현재 끌기 이미지와 결합 하 여 새 끌기 이미지를 만듭니다. Windows를 사용 해야 끌기 함수가 끌기 작업 중 새 이미지를 사용 하므로 [ShowCursor](http://msdn.microsoft.com/library/windows/desktop/ms648396) 함수를 호출한 후 실제 마우스 커서를 숨기려면 `SetDragCursorImage`합니다. 그렇지 않은 경우 시스템은 끌기 작업의 기간에 대 한 두 개의 마우스 커서를 가져야 나타날 수 있습니다.  
  
 응용 프로그램 호출 하는 경우 `BeginDrag`, 임시 내부 이미지 목록이 만들어집니다 및 복사에 지정된 된 내부 목록에 이미지를 끕니다. 임시 끌기 이미지 목록에 대 한 포인터를 사용 하 여 검색할 수 있습니다는 [GetDragImage](../mfc/reference/cimagelist-class.md#getdragimage) 멤버 함수입니다. 함수는 또한 끌어서 위치를 기준으로 끌기 이미지의 오프셋과 현재 끌어서 위치를 검색합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CImageList 사용](../mfc/using-cimagelist.md)   
 [컨트롤](../mfc/controls-mfc.md)

