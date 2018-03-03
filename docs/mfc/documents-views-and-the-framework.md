---
title: "문서, 뷰 및 프레임 워크 | Microsoft Docs"
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
- document templates [MFC], template objects
- applications [MFC]
- MFC, application framework
- application objects [MFC], relation to other MFC objects
- documents [MFC]
- MFC, documents
- document objects [MFC], in relation to other MFC objects
- view objects [MFC], relation to other MFC objects
- MFC, views
- document/view architecture [MFC], about document/view architecture
- objects [MFC], MFC applications
- MFC object relationships
- thread objects [MFC]
ms.assetid: 409ddd9b-66ad-4625-84f7-bf55a41d697b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e48872907b07b0adf18cf17cca6ec6ecabe9e2de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="documents-views-and-the-framework"></a>문서, 뷰 및 프레임워크
MFC 프레임 워크의 핵심에는 문서 및 보기의 개념입니다. 문서에는 편집 세션에는 사용자가 데이터 개체입니다. 의해 만들어집니다는 `New` 또는 **열려** 명령을 **파일** 메뉴 일반적으로 파일에 저장 됩니다. (클래스에서 파생 되는 표준 MFC 문서 **CDocument**, 액티브 문서 및 OLE의 복합 문서와 다릅니다.) 뷰를 통해 사용자 상호 작용 하는 문서와 window 개체는.  
  
 실행 중인 응용 프로그램은 키 개체입니다.  
  
-   문서 또는 문서입니다.  
  
     문서 클래스 (에서 파생 된 [CDocument](../mfc/reference/cdocument-class.md)) 응용 프로그램의 데이터를 지정 합니다.  
  
     응용 프로그램에서 OLE 기능을 원하는 경우에서 문서 클래스를 파생 [COleDocument](../mfc/reference/coledocument-class.md) 또는 해당 파생된 클래스에서 필요한 기능을의 유형에 따라 중 하나입니다.  
  
-   보기 또는 뷰입니다.  
  
     뷰 클래스 (에서 파생 된 [CView](../mfc/reference/cview-class.md))가 사용자의 "창에서 데이터입니다." 뷰 클래스에는 사용자 문서의 데이터를 확인 하 고 상호 작용 하는 방법을 제어 합니다. 경우에 따라 문서를 데이터의 여러 뷰를 포함할 수도 있습니다.  
  
     파생 된 스크롤 필요한 경우 [CScrollView](../mfc/reference/cscrollview-class.md)합니다. 파생 된 보기에 대화 상자 템플릿 리소스에 배치 되는 사용자 인터페이스가 있는, [CFormView](../mfc/reference/cformview-class.md)합니다. 간단한 텍스트 데이터에 대 한 사용 하거나이 로부터 파생할 [CEditView](../mfc/reference/ceditview-class.md)합니다. 파생 되는 데이터 입력 프로그램 같은 폼 기반 데이터 액세스 응용 프로그램에 대 한 [CRecordView](../mfc/reference/crecordview-class.md) (ODBC)에 대 한 합니다. 또한 사용할 수는 클래스 [CTreeView](../mfc/reference/ctreeview-class.md), [CListView](../mfc/reference/clistview-class.md), 및 [CRichEditView](../mfc/reference/cricheditview-class.md)합니다.  
  
-   프레임 창  
  
     뷰 "문서 프레임 창" 내부에 표시 됩니다. SDI 응용 프로그램에서 문서 프레임 창도 응용 프로그램에 대 한 "주 프레임 창"입니다. MDI 응용 프로그램에서 문서 창을 자식 창을 주 프레임 창 안에 표시 됩니다. 파생 된 주 프레임 창 클래스 스타일 및 프레임 창의 뷰를 포함 하는 다른 특성을 지정 합니다. 파생 하는 프레임 창 사용자 지정 해야 할 경우 [CFrameWnd](../mfc/reference/cframewnd-class.md) SDI 응용 프로그램에 대 한 문서 프레임 창에 사용자 지정할 수 있습니다. 파생 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) MDI 응용 프로그램에 대 한 주 프레임 창을 사용자 지정할 수 있습니다. 클래스를 파생 시킵니다 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) 응용 프로그램이 지 원하는 MDI 문서 프레임 창의 각 고유 종류를 사용자 지정할 수 있습니다.  
  
-   문서 서식 파일 또는 서식 파일  
  
     문서 서식 파일의 문서, 뷰 및 프레임 창 만들기를 조정합니다. 특정 문서 템플릿 클래스는 클래스에서 파생 된 [CDocTemplate](../mfc/reference/cdoctemplate-class.md), 만들고 한 종류의 열려 있는 모든 문서를 관리 합니다. 문서의 둘 이상의 유형을 지 원하는 응용 프로그램에는 문서 템플릿이 여러 개 있습니다. 클래스를 사용 하 여 [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) SDI 응용 프로그램 또는 사용 하 여 클래스에 대 한 [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md) MDI 응용 프로그램에 대 한 합니다.  
  
-   Application 개체  
  
     응용 프로그램 클래스 (에서 파생 된 [CWinApp](../mfc/reference/cwinapp-class.md)) 위의 개체를 모두 제어 하 고 초기화 및 정리 같은 응용 프로그램 동작을 지정 합니다. 응용 프로그램의 1과만 응용 프로그램 개체를 만들고 모든 문서에서 응용 프로그램에서 지 원하는 형식에 대 한 문서 서식 파일을 관리 합니다.  
  
-   스레드 개체  
  
     응용 프로그램 실행의 별도 스레드를 만드는 경우-백그라운드에서 계산을 수행 하는 등-에서 파생 된 클래스를 사용 합니다 [CWinThread](../mfc/reference/cwinthread-class.md)합니다. [CWinApp](../mfc/reference/cwinapp-class.md) 자체에서 파생 된 `CWinThread` 응용 프로그램에서 실행 (또는 기본 프로세스)의 주 스레드를 나타냅니다. 또한 보조 스레드에서 MFC를 사용할 수 있습니다.  
  
 실행 중인 응용 프로그램에서 이러한 개체는 협조적 된 명령 및 기타 메시지의 사용자 동작에 응답 합니다. 단일 응용 프로그램 개체를 하나 이상의 문서 서식 파일을 관리합니다. 각 문서 서식 파일 만들고 (인지 여부에 따라 응용 프로그램 SDI MDI) 하나 이상의 문서를 관리 합니다. 사용자 표시 및 프레임 창 안에 포함 된 뷰를 통해 문서를 조작 합니다. 다음 그림에서는 SDI 응용 프로그램에 대 한이 개체 간의 관계를 보여 줍니다.  
  
 ![실행 중인 SDI 응용 프로그램의 개체](../mfc/media/vc386v1.gif "vc386v1")  
실행 중인 SDI 응용 프로그램의 개체  
  
 문서이에서는의 나머지 부분에는 프레임 워크 도구, MFC 응용 프로그램 마법사 및 리소스 편집기에서 이러한 개체를 만드는 방법, 함께 작동 방식 및 사용법을 프로그래밍에 설명 합니다. 문서, 뷰 및 프레임 창에서 더 자세하게에서 설명 [창 개체 소멸 시키기](../mfc/window-objects.md) 및 [문서/뷰 아키텍처](../mfc/document-view-architecture.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스를 사용하여 Windows 응용 프로그램 작성](../mfc/using-the-classes-to-write-applications-for-windows.md)
