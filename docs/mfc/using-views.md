---
title: "뷰를 사용 하 여 | Microsoft Docs"
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
- interacting with users and role of view class [MFC]
- drawing [MFC], data
- rendering data
- view classes [MFC], role in managing user interaction
- CView class [MFC], view architecture
- MFC, views
- views [MFC], using
- painting data
- user input [MFC], interpreting through view class [MFC]
- view classes [MFC], role in displaying application data
ms.assetid: dc3de6ad-5c64-4317-8f10-8bdcc38cdbd5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 99493657313d480559d232bf9033dfb7a7a585c4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="using-views"></a>뷰 사용
뷰는 사용자에 게 문서의 데이터를 그래픽으로 표시 하를 수락 하 고 문서에 대 한 작업으로 사용자 입력 해석 합니다. 뷰 클래스를 작성할에서 작업에는 것입니다.  
  
-   뷰 클래스의 쓰기 [OnDraw](../mfc/reference/cview-class.md#ondraw) 문서의 데이터를 렌더링 하는 멤버 함수입니다.  
  
-   메시지 처리기 멤버 함수는 뷰 클래스에 적절 한 Windows 메시지 및 메뉴 항목과 같은 사용자 인터페이스 개체를 연결 합니다.  
  
-   사용자 입력 해석 하는 해당 처리기를 구현 합니다.  
  
 다른 재정의 해야 하는 또한 `CView` 파생 된 뷰 클래스의 멤버 함수입니다. 재정의 해야 하는 특히, [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) 뷰에 대 한 특별 한 초기화를 수행 하 고 [OnUpdate](../mfc/reference/cview-class.md#onupdate) 보기 자신을 다시 그리면 하기 바로 전에 필요한 특별 한 처리 작업을 수행할 합니다. 다중 페이지 문서에 대 한도 재정의 해야 [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting) 인쇄할 페이지 및 기타 정보의 번호로 인쇄 대화 상자를 초기화 합니다. 재정의 대 한 자세한 내용은 `CView` 멤버 함수는 클래스를 참조 하십시오. [CView](../mfc/reference/cview-class.md) 에 *MFC 참조*합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [MFC에서 사용할 수 있는 파생 된 뷰 클래스](../mfc/derived-view-classes-available-in-mfc.md)  
  
-   [뷰에 그리기](../mfc/drawing-in-a-view.md)  
  
-   [뷰를 통해 사용자 입력 해석](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [인쇄에서 뷰의 역할](../mfc/role-of-the-view-in-printing.md)  
  
-   [스크롤 및 뷰를 크기 조정](../mfc/scrolling-and-scaling-views.md)  
  
-   [초기화 및 문서 및 뷰 정리](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
## <a name="see-also"></a>참고 항목  
 [문서/뷰 아키텍처](../mfc/document-view-architecture.md)   
 [CFormView 클래스](../mfc/reference/cformview-class.md)   
 [레코드 뷰 (데이터 액세스)](../data/record-views-mfc-data-access.md)   
 [Serialization 메커니즘 건너뛰기](../mfc/bypassing-the-serialization-mechanism.md)

