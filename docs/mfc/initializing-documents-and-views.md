---
title: "문서 및 뷰 초기화 | Microsoft Docs"
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
- initializing documents [MFC]
- documents [MFC], initializing
- views [MFC], initializing
- initializing objects [MFC], document objects
- initializing views [MFC]
ms.assetid: 33cb8643-8a16-478c-bc26-eccc734e3661
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f80d870f9804454dc652fdda00f34fcdb7a52062
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="initializing-documents-and-views"></a>문서 및 뷰 초기화
문서 클래스에는 두 가지 방법을 모두 지원 해야 하므로 문서는 두 가지 방법으로 생성 됩니다. 첫째, 새 파일 명령을 사용 하 여 새로 만든 빈 문서를 만들 수는 있습니다. 이 경우의 재정의에서 문서를 초기화는 [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) 클래스의 멤버 함수 [CDocument](../mfc/reference/cdocument-class.md)합니다. 둘째, 사용자 파일에서 읽은 내용을 새 문서를 만드는 데 파일 메뉴에서 열기 명령을 사용할 수 있습니다. 이 경우의 재정의에서 문서를 초기화는 [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) 클래스의 멤버 함수 **CDocument**합니다. 같으면 두 번의 초기화를 모두 재정의에서 공용 멤버 함수를 호출할 수 있습니다 또는 `OnOpenDocument` 호출할 수 `OnNewDocument` 새로 문서를 초기화 및 다음 열기 작업을 완료 합니다.  
  
 문서를 만든 후 뷰가 만들어집니다. 보기를 초기화할 수 있는 가장 좋은 시간은 문서, 프레임 창 및 보기를 만드는 프레임 워크 완료 된 후입니다. 재정의 하 여 보기를 초기화할 수 있습니다는 [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) 의 멤버 함수 [CView](../mfc/reference/cview-class.md)합니다. 다시 초기화 하거나 아무 것도 조정 해야 할 경우 문서 변경 될 때마다, 문자인 [OnUpdate](../mfc/reference/cview-class.md#onupdate)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [문서 및 뷰 초기화 및 정리](../mfc/initializing-and-cleaning-up-documents-and-views.md)

