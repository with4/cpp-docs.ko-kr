---
title: "문서/뷰 아키텍처의 이점 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "문서/뷰 아키텍처, 이점"
  - "뷰, 이점"
ms.assetid: 0bc27071-e120-4889-939c-ce1e61fb9cb3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 문서/뷰 아키텍처의 이점
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC 문서\/뷰 아키텍처를 사용하는 것의 주요 장점은 아키텍처가 같은 문서의 뷰가 여러 개여도 잘 지원 된다는 것입니다. \(다중 뷰가 필요하지 않고 문서\/뷰의 오버헤드가 응용 프로그램에서 너무 많은 경우, 이 아키텍처를 피할 수 있습니다.  [Alternatives to the Document\/View Architecture](../mfc/alternatives-to-the-document-view-architecture.md).\)  
  
 응용 프로그램 사용자가 스프레드시트 양식 또는 차트 형식으로 숫자 데이터를 볼 수 있다고 가정 합니다.  사용자는 동시에 모든 원시 데이터를 스프레드시트 형식과 결과 데이터를 표시 하는 차트를 볼 수도 있습니다.  개별 프레임 창 또는 분할자 창은 단일 창 내에서 개별 뷰를 표시합니다.  이제 참조 및 스프레드시트에서 데이터를 편집할 수 있다고 가정하고 변경 즉시 차트에 반영 됩니다.  
  
 MFC에서 스프레드시트 뷰와 차트 뷰는 CView에서 파생 된 다른 클래스에 기반 합니다.  모두 하나의 문서 개체와 연결 됩니다.  문서는 데이터를 저장 하거나 데이터베이스에서 가져옵니다.  모든 뷰는 문서에 액세스하고 검색한 데이터를 표시합니다.  
  
 뷰의 하나를 업데이트 할때, 뷰 개체는 `CDocument::UpdateAllViews` 를 호출합니다.  함수에 문서의 뷰를 모두 알리고 각 보기 문서에서 최신 데이터를 사용 하여 자체적으로 업데이트 합니다.  `UpdateAllViews` 에 대한 단일 호출은 다른 뷰를 동기화 합니다.  
  
 이 시나리오는 뷰에서 데이터의 분할 없이는 코딩하기 어렵습니다. 특히 뷰가 데이터를 스스로 저장하는 경우 그렇습니다.  문서\/뷰를 사용하는 경우는 쉽습니다.  조정 작업의 대부분을 수행 하는 프레임 워크입니다.  
  
## 추가 정보  
  
-   [문서\/뷰에 대한 대안](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [CDocument](../mfc/reference/cdocument-class.md)  
  
-   [CView](../mfc/reference/cview-class.md)  
  
-   [CDocument::UpdateAllViews](../Topic/CDocument::UpdateAllViews.md)  
  
-   [CView::GetDocument](../Topic/CView::GetDocument.md)  
  
## 참고 항목  
 [문서\/뷰 아키텍처](../mfc/document-view-architecture.md)