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
ms.openlocfilehash: 894bb5a0b3a4c86d764fc6f4a0e4b9ae18422669
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931855"
---
# <a name="documentview-creation"></a>문서/뷰 만들기
프레임 워크의 구현을 제공는 **새로** 및 **열려** (등)에 있는 명령을 **파일** 메뉴. 만드는 새 문서와 관련 된 보기 및 프레임 창에는 application 개체, 문서 서식 파일, 새로 만든된 문서 및 새로 만든된 프레임 창 등 않습니다. 다음 표에서 개체를 만드는 기능을 요약 합니다.  
  
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

