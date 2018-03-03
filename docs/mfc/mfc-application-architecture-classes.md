---
title: "MFC 응용 프로그램 아키텍처 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- MFC, classes
- MFC, application development
- classes [MFC], MFC
- application architecture classes [MFC]
ms.assetid: 71b2de54-b44d-407e-9c71-9baf954e18d9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 623775d6c3306ba4afdb01eb78ea70b05f7a3365
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-application-architecture-classes"></a>MFC 응용 프로그램 아키텍처 클래스
이 항목의 클래스는 프레임 워크 응용 프로그램의 아키텍처에 영향을 줍니다. 대부분의 응용 프로그램에 공통 기능을 제공합니다. 응용 프로그램 관련 기능을 추가 하기 위해 프레임 워크에 정보를 입력 합니다. 일반적으로 이렇게 하면 아키텍처 클래스에서 새 클래스를 파생 하 고 다음 새 멤버를 추가 하거나 기존 멤버 함수를 재정의 하 여 됩니다.  
  
 [응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md) 여러 유형의 응용 프로그램에는 모두 응용 프로그램 프레임 워크를 사용 하 여 서로 다른 방법으로 생성 합니다. SDI (단일 문서 인터페이스) 및 MDI (다중 문서 인터페이스) 응용 프로그램을 모두 사용할 문서/뷰 아키텍처를 호출 하는 프레임 워크의 일부입니다. 다른 유형의 응용 프로그램 대화 상자 기반 응용 프로그램, 폼 기반 응용 프로그램 및 Dll의 경우와 같은 문서/뷰 아키텍처 기능 중 일부만 사용 합니다.  
  
 문서/뷰 응용 프로그램 문서, 뷰 및 프레임 창은 하나 이상의 집합을 포함 합니다. 문서 템플릿 개체를 각 문서/뷰/프레임 집합에 대 한 클래스에 연결합니다.  
  
 MFC 응용 프로그램의 문서/뷰 아키텍처를 사용 해야 하지만 이렇게 장점 중 여러 가지가 있습니다. 인쇄 및 인쇄 미리 보기에 대 한 지원은 MFC OLE 컨테이너와 서버 지원 문서/뷰 아키텍처에 따라 됩니다.  
  
 MFC 응용 프로그램의 모든 개체를 두 개 이상 포함할: 응용 프로그램 개체에서 파생 된 [CWinApp](../mfc/reference/cwinapp-class.md), 및에서 종종 간접적으로 파생 되는 주 창의 개체의 일종 [CWnd](../mfc/reference/cwnd-class.md)합니다. (주 창에서 파생 되는 경우가 가장 많으며, [CFrameWnd](../mfc/reference/cframewnd-class.md), [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), 또는 [CDialog](../mfc/reference/cdialog-class.md)에서 파생 되는 모두 `CWnd`.)  
  
 문서/뷰 아키텍처를 사용 하는 응용 프로그램 추가 개체를 포함 합니다. 주 개체입니다.  
  
-   응용 프로그램 개체 클래스에서 파생 된 [CWinApp](../mfc/reference/cwinapp-class.md)앞서 언급 했 듯이, 합니다.  
  
-   클래스에서 파생 된 하나 이상의 문서 클래스 개체 [CDocument](../mfc/reference/cdocument-class.md)합니다. 문서 클래스 개체 보기에서 처리 하는 데이터의 내부 표현에 대 한 책임이 있습니다. 데이터 파일에 연결할 수 있습니다.  
  
-   클래스에서 파생 된 하나 이상의 보기 개체 [CView](../mfc/reference/cview-class.md)합니다. 각 보기에는 문서에 연결 되 고 프레임 창에 연결 하는 창입니다. 뷰를 표시 및 문서 클래스 개체에 포함 된 데이터를 조작 합니다.  
  
 문서/뷰 응용 프로그램 프레임 창에도 포함 (에서 파생 된 [CFrameWnd](../mfc/reference/cframewnd-class.md)) 문서 템플릿 및 (에서 파생 된 [CDocTemplate](../mfc/reference/cdoctemplate-class.md)).  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)

