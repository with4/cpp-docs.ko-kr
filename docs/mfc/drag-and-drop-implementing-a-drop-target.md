---
title: "끌어서 놓기: 놓기 대상 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE drag and drop [MFC], implementing drop targets
- OLE drag and drop [MFC], drop target
- drag and drop [MFC], drop target
ms.assetid: 0689f1ec-5326-4008-b226-4b373c881358
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9fc73eb6627e63b8013180b7608633a9ee424c92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="drag-and-drop-implementing-a-drop-target"></a>끌어서 놓기: 놓기 대상 구현
이 문서에서는 응용 프로그램 놓기 대상으로 지정 하는 방법에 설명 합니다. 놓기 대상 구현 놓기 소스 구현 보다 약간 더 많은 작업이 걸리지만 것은 여전히 비교적 간단 합니다. 이러한 기술은 비 OLE 응용 프로그램에도 적용 됩니다.  
  
#### <a name="to-implement-a-drop-target"></a>놓기 대상 구현 하려면  
  
1.  놓기 대상 이어야 응용 프로그램의 각 보기에 멤버 변수를 추가 합니다. 이 멤버 변수 형식 이어야 합니다 `COleDropTarget` 여기에서 파생 된 클래스 또는 합니다.  
  
2.  처리 하는 뷰 클래스의 함수는 `WM_CREATE` 메시지 (일반적으로 `OnCreate`), 새 멤버 변수를 호출 `Register` 멤버 함수입니다. `Revoke`이름은 자동으로 사용자에 대 한 보기 소멸 될 때입니다.  
  
3.  다음 함수를 재정의 합니다. 응용 프로그램에서 동일한 동작을 원하는 경우 뷰 클래스에서 이러한 함수를 재정의 합니다. 격리 된 경우에는 동작을 수정 하거나 삭제 비-사용 하도록 설정할 경우`CView` 창에서 이러한 함수를 재정의 하면 `COleDropTarget`-파생 클래스입니다.  
  
    |재정의|허용 하려면|  
    |--------------|--------------|  
    |`OnDragEnter`|창에서 발생 하는 작업을 삭제 합니다. 커서 창에 먼저 전달 될 때 호출 합니다.|  
    |`OnDragLeave`|끌기 작업이 지정된 된 창으로 나갈 때 특별 한 동작입니다.|  
    |`OnDragOver`|창에서 발생 하는 작업을 삭제 합니다. 커서는 창에 가로로 끌 때 호출 됩니다.|  
    |`OnDrop`|지정 된 창에 끌어 놓는 데이터의 처리를 제공 합니다.|  
    |`OnScrollBy`|스크롤이 필요할 때 대상 창에 대 한 특별 한 동작입니다.|  
  
 MAINVIEW를 참조 하십시오. CPP 파일을 MFC OLE 샘플의 일부 [OCLIENT](../visual-cpp-samples.md) 이러한 함수 함께 작동 하는 방법의 예입니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [놓기 소스 구현](../mfc/drag-and-drop-implementing-a-drop-source.md)  
  
-   [만들고 OLE 데이터 개체 및 데이터 소스 제거](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [OLE 데이터 개체 및 데이터 소스 조작](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="see-also"></a>참고 항목  
 [끌어서 놓기 (OLE)](../mfc/drag-and-drop-ole.md)   
 [COleDropTarget 클래스](../mfc/reference/coledroptarget-class.md)
