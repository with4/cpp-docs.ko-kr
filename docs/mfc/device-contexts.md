---
title: "장치 컨텍스트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- OnPrepareDC method [MFC]
- windows [MFC], and device context
- drawing [MFC], device context
- CClientDC class [MFC], and GetDC method [MFC]
- drawing [MFC], in mouse and device contexts
- CDC class [MFC], objects
- device contexts [MFC]
- client areas
- CMetaFileDC class [MFC], and OnPrepareDC method [MFC]
- GDI objects [MFC], device contexts
- graphic objects [MFC], device contexts
- frame windows [MFC], device contexts
- metafiles and device contexts
- EndPaint method [MFC]
- printers [MFC], device contexts
- mouse [MFC], drawing and device contexts
- BeginPaint method, CPaintDC
- CPaintDC class [MFC], device context for painting
- windows [MFC], drawing directly into
- client areas, and device context
- device contexts [MFC], CDC class [MFC]
- user interface [MFC], device contexts
- device-independent drawing
- GetDC method and CClientDC class [MFC]
- CClientDC class [MFC], and ReleaseDC method [MFC]
- ReleaseDC method [MFC]
- device contexts [MFC], about device contexts
- drawing [MFC], directly into windows
- painting and device context
ms.assetid: d0cd51f1-f778-4c7e-bf50-d738d10433c7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 26d4a0e32a8b24a72447cf4227be128659316c0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="device-contexts"></a>장치 컨텍스트
장치 컨텍스트에 화면 또는 프린터와 같은 장치 그리기 특성에 대 한 정보를 포함 하는 Windows 데이터 구조입니다. 모든 그리기 호출은 그리기 선, 도형 및 텍스트에 대 한 Windows Api를 캡슐화 하는 장치 컨텍스트 개체를 통해 수행 됩니다. 장치 컨텍스트는 Windows에서 장치 독립적 그리기를 허용합니다. 장치 컨텍스트 화면, 프린터 또는 메타 파일을 그리는 데 사용할 수 있습니다.  
  
 [CPaintDC](../mfc/reference/cpaintdc-class.md) 창, 호출의 공통 요소를 캡슐화 하는 개체는 `BeginPaint` 함수를 차례로 장치 컨텍스트에서 그리기 호출의 `EndPaint` 함수입니다. `CPaintDC` 생성자 호출 `BeginPaint` 와 소멸자 호출을 위한 `EndPaint`합니다. 간소화 된 프로세스를 만드는 것은 [CDC](../mfc/reference/cdc-class.md) 개체 그리고를 삭제 합니다는 `CDC` 개체입니다. 프레임 워크에서이 프로세스의 대부분 자동화 합니다. 특히, 프로그램 `OnDraw` 함수에 전달 되는 `CPaintDC` 이미 준비 (통해 `OnPrepareDC`), 단순히를 그립니다. 프레임 워크에 의해 삭제 될 기본 장치 컨텍스트를 눌렀다 창에 대 한 호출에서 반환 될 때 프로그램 `OnDraw` 함수입니다.  
  
 [CClientDC](../mfc/reference/cclientdc-class.md) 개체 장치 컨텍스트에 창의 클라이언트 영역을 나타내는 작업을 캡슐화 합니다. `CClientDC` 생성자 호출은 `GetDC` 함수와 소멸자 호출은 `ReleaseDC` 함수입니다. [CWindowDC](../mfc/reference/cwindowdc-class.md) 개체는 프레임을 포함 하 여 전체 창을 나타내는 장치 컨텍스트를 캡슐화 합니다.  
  
 [CMetaFileDC](../mfc/reference/cmetafiledc-class.md) 개체는 Windows 메타 파일으로 드로잉을 캡슐화 합니다. 달리는 `CPaintDC` 에 전달 된 `OnDraw`,이 경우에 호출 해야 [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) 직접 합니다.  
  
## <a name="mouse-drawing"></a>마우스 그리기  
 프레임 워크 프로그램에서 대부분의 그리기-, 따라서 대부분 디바이스 컨텍스트 작업-보기의에 의해 이루어진다는 `OnDraw` 멤버 함수입니다. 그러나 다른 용도 대 한 디바이스 컨텍스트 개체를 계속 사용할 수 있습니다. 예를 들어 뷰에서 마우스 움직임을 추적 피드백을 제공 하려면 필요한를 기다리지 않고 보기에 직접 그리는 `OnDraw` 를 호출할 수 있습니다.  
  
 이 경우 사용할 수 있습니다는 [CClientDC](../mfc/reference/cclientdc-class.md) 디바이스 컨텍스트 개체 보기 직접 그려야 합니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [장치 컨텍스트 (정의)](http://msdn.microsoft.com/library/windows/desktop/dd183553)  
  
-   [뷰에 그리기](../mfc/drawing-in-a-view.md)  
  
-   [뷰를 통해 사용자 입력 해석](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [선 및 곡선](http://msdn.microsoft.com/library/windows/desktop/dd145028)  
  
-   [채워진된 도형](http://msdn.microsoft.com/library/windows/desktop/dd162714)  
  
-   [글꼴 및 텍스트](http://msdn.microsoft.com/library/windows/desktop/dd144819)  
  
-   [색](http://msdn.microsoft.com/library/windows/desktop/dd183450)  
  
-   [좌표 공간 및 변환](http://msdn.microsoft.com/library/windows/desktop/dd183475)  
  
## <a name="see-also"></a>참고 항목  
 [창 개체](../mfc/window-objects.md)

