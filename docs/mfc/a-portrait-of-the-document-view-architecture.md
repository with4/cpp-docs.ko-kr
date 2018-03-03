---
title: "문서 뷰 아키텍처에 대 한 자세한 | Microsoft Docs"
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
- documents [MFC], views
- multiple views [MFC], updating from document
- document/view architecture [MFC]
- views [MFC], and user input
- documents [MFC], accessing data from view
- views [MFC], updating
- input [MFC], view class
- documents [MFC], multiple views
- document/view architecture [MFC], accessing data from view
- document/view architecture [MFC], about document/view architecture
- views [MFC], accessing document data from
ms.assetid: 4e7f65dc-b166-45d8-bcd5-9bb0d399b946
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9ceadc55945a31e4787287beb6943897784aeaad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="a-portrait-of-the-documentview-architecture"></a>문서/뷰 아키텍처에 대한 자세한 설명
일반 MFC 응용 프로그램에서 문서 및 뷰 페어링 되었습니다. 데이터는 문서에 저장 되어 있지만 보기에 특권 수준의 권한이 데이터에 대 한 액세스. 표시에서 저장소 및 데이터의 유지 관리를 구분 하는 보기에서 문서를 분리 합니다.  
  
## <a name="gaining-access-to-document-data-from-the-view"></a>문서 보기에서 데이터에 액세스  
 뷰 데이터에 액세스의 문서를는 [GetDocument](../mfc/reference/cview-class.md#getdocument) 작동 하거나 뷰 클래스를 c + +에는 문서에 대 한 포인터를 반환 하는 `friend` 문서 클래스의 합니다. 다음 보기는 데이터에 액세스를 사용 하 여 그리기 또는 다른 방법으로 조작할로 준비가 되 면 데이터를 가져오기 위해 합니다.  
  
 보기의 예를 들어에서 [OnDraw](../mfc/reference/cview-class.md#ondraw) 멤버 함수는 보기에 사용 **GetDocument** 문서 포인터를 가져올 수 있습니다. 해당 포인터를 사용 하 여 액세스 하는 `CString` 문서에서 데이터 멤버입니다. 보기에는 문자열에 전달 된 `TextOut` 함수입니다. 이 예제에 대 한 코드를 보려면 [뷰에 그리기](../mfc/drawing-in-a-view.md)합니다.  
  
## <a name="user-input-to-the-view"></a>보기에 대 한 사용자 입력  
 보기 선택 또는 데이터의 편집으로 자체 내에서 마우스 클릭을 해석할 수 있습니다. 마찬가지로 키 입력 데이터 입력 또는 편집으로 해석할 수 있습니다. 텍스트를 관리 하는 뷰에서 사용자가 입력 문자열을 가정 합니다. 보기 문서에 대 한 포인터를 가져오고 일부 데이터 구조에 저장 된 문서에 새 데이터를 전달 하려면 포인터를 사용 합니다.  
  
## <a name="updating-multiple-views-of-the-same-document"></a>동일한 문서의 여러 뷰 업데이트  
 동일한 문서의 여러 뷰가 포함 된 응용 프로그램에서-예: 텍스트 편집기에서 분할자 창-보기 먼저 문서에 새 데이터를 전달 합니다. 문서의 호출 [UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews) 업데이트 되므로, 새 데이터를 반영 하려면 문서의 모든 보기를 알려 주는 멤버 함수입니다. 뷰를 동기화 합니다.  
  
### <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [문서/뷰 아키텍처의 이점](../mfc/advantages-of-the-document-view-architecture.md)  
  
-   [문서/뷰 아키텍처의 대체](../mfc/alternatives-to-the-document-view-architecture.md)  
  
## <a name="see-also"></a>참고 항목  
 [문서/뷰 아키텍처](../mfc/document-view-architecture.md)

