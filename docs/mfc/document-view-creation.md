---
title: 문서 뷰 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- documents [MFC], creating
- views [MFC], and frame windows
- views [MFC], creating
- tables [MFC]
- MFC, views
- document/view architecture [MFC], creating document/view
- object creators
- MFC, documents
- tables [MFC], objects each MFC object creates
ms.assetid: bda14f41-ed50-439d-af9e-591174e7dd64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb89180db8e1a6cce2c40bbb4bae0965b972afa2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="documentview-creation"></a>문서/뷰 만들기
프레임 워크의 구현을 제공는 `New` 및 **열려** (등)에 있는 명령을 **파일** 메뉴. 만드는 새 문서와 관련 된 보기 및 프레임 창에는 application 개체, 문서 서식 파일, 새로 만든된 문서 및 새로 만든된 프레임 창 등 않습니다. 다음 표에서 개체를 만드는 기능을 요약 합니다.  
  
### <a name="object-creators"></a>개체 작성자  
  
|Creator|만듭니다.|  
|-------------|-------------|  
|Application 개체|문서 서식 파일|  
|문서 서식 파일|문서|  
|문서 서식 파일|프레임 창|  
|프레임 창|보기|  
  
## <a name="see-also"></a>참고 항목  
 [문서 템플릿 및 문서/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [문서 서식 파일 만들기](../mfc/document-template-creation.md)   
 [MFC 개체 간 관계](../mfc/relationships-among-mfc-objects.md)   
 [새 문서, 창 및 뷰 만들기](../mfc/creating-new-documents-windows-and-views.md)

