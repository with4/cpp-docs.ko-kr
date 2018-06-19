---
title: 문서 뷰 아키텍처의 이점 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- views [MFC], advantages
- document/view architecture [MFC], advantages of
ms.assetid: 0bc27071-e120-4889-939c-ce1e61fb9cb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45065b38128a2e3239b1fd10ded490fdcbcb3eac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33340850"
---
# <a name="advantages-of-the-documentview-architecture"></a>문서/뷰 아키텍처의 이점
MFC 문서/뷰 아키텍처를 사용 하 여 주요 이점은 아키텍처는 동일한 문서의 여러 뷰를 잘 지원입니다. (여러 뷰를 필요 하지 않습니다. 문서/보기의 작은 오버 헤드는 응용 프로그램에서 과도 한을 방지할 수 있습니다 아키텍처. [문서/뷰 아키텍처의 대체](../mfc/alternatives-to-the-document-view-architecture.md).)  
  
 응용 프로그램에 차트 형식 또는 스프레드시트 양식에서 숫자 데이터를 볼 수 있습니다를 가정 합니다. 사용자는 동시에 둘 다에서 원시 데이터를 스프레드시트 폼 및 데이터의 결과로 생성 되는 차트에서 확인 해야 할 수도 있습니다. 단일 창 내에서 분할자 창 또는 별도 프레임 창에서 이러한 별도 뷰를 표시합니다. 이제 사용자는 스프레드시트와 참조에 대 한 데이터를 편집할 수 있다고 가정 변경 내용을 즉시 차트에 반영 합니다.  
  
 Mfc에서 스프레드시트 보기 및 차트 보기를 CView에서 파생 된 다른 클래스에 기반 합니다. 두 보기는 단일 문서 개체에 연결 된 것입니다. 문서는 데이터를 저장 하거나 데이터베이스에서 가져옵니다. 두 보기 문서에 액세스 하 고 여기에서 검색 한 데이터를 표시 합니다.  
  
 사용자 개체 호출을 볼 뷰 중 하나를 업데이트할 때 `CDocument::UpdateAllViews`합니다. 해당 함수를에 알립니다 문서 보기의 모든 문서에서 최신 데이터를 사용 하 여 각 보기 업데이트 합니다. 에 대 한 단일 호출 `UpdateAllViews` 서로 다른 뷰를 동기화 합니다.  
  
 이 시나리오 어려울 것 데이터 분리 없는 코드 뷰에서 뷰 자체 데이터를 저장 하는 경우에 특히입니다. 문서/뷰를 사용 하기가 쉽습니다. 프레임 워크의 동기화 작업 대부분에서.  
  
## <a name="what-do-you-want-to-know-more-about"></a>자세히 알아보려는 항목  
  
-   [문서/뷰 대안](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [CDocument](../mfc/reference/cdocument-class.md)  
  
-   [CView](../mfc/reference/cview-class.md)  
  
-   [CDocument::UpdateAllViews](../mfc/reference/cdocument-class.md#updateallviews)  
  
-   [CView::GetDocument](../mfc/reference/cview-class.md#getdocument)  
  
## <a name="see-also"></a>참고 항목  
 [문서/뷰 아키텍처](../mfc/document-view-architecture.md)

