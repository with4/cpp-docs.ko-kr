---
title: "문서 뷰 아키텍처 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CView class [MFC], view architecture
- CDocument class [MFC]
- MFC, views
- views [MFC], MFC document/view model
- document objects [MFC]
- document objects [MFC], MFC document/view model
- MFC, documents
- documents [MFC], MFC document/view model
- document objects [MFC], document/view architecture
ms.assetid: 6127768a-553f-462a-b01b-a5ee6068c81e
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 45c595b78b17ed00691533369ec4837345fcce03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="documentview-architecture"></a>문서/뷰 아키텍처
기본적으로 MFC 응용 프로그램 마법사는 문서 클래스 뷰 클래스와 기초 응용 프로그램을 만듭니다. MFC는이 두 클래스에 대 한 데이터 관리를 구분합니다. 문서는 데이터를 저장 하 고 및 관리 데이터를 인쇄, 데이터의 여러 뷰 업데이트를 조정 합니다. 뷰는 데이터를 표시 하 고 작성기를 편집 및 선택 영역을 포함 하 여 사용자 상호 작용을 관리 합니다.  
  
 이 모델에는 MFC 문서 개체를 읽고 데이터를 영구 저장소에 기록 합니다. 문서 (예: 데이터베이스) 상주 하는 위치 데이터에 대 한 인터페이스를 제공할 수도 있습니다. 가 사용자 선택 하려는 창에 데이터를 렌더링 하 고 데이터의 편집 데이터 표시를 관리 하는 별도 뷰 개체입니다. 보기 문서에서 데이터 표시를 가져오고 데이터 변경 내용을 문서에 다시 통신 합니다.  
  
 재정의 하거나 무시 문서/뷰를 분리 하 여 쉽게를 다음과 같은 이유로 대부분의 경우에서이 모델에 따라 가지 있습니다. 가장 좋은 스프레드시트와 차트 보기와 같은 동일한 문서의 여러 뷰를 식별할 때. 문서/뷰 모델을 사용 하면 공통 코드를 뷰 (예: 계산 엔진) 문서에 있을 수 있습니다 하는 동안 데이터의 각 뷰를 나타내는 별도 뷰 개체가 있습니다. 또한 문서는 데이터가 변경 될 때마다 모든 보기를 업데이트 하는 작업에 사용 합니다.  
  
 MFC 문서/뷰 아키텍처를 사용 하면 여러 뷰, 여러 문서 형식, 분할 창 및 기타 중요 한 사용자 인터페이스 기능을 지원 하기 편리 합니다.  
  
 MFC 프레임 워크를 특정 사용자 및 사용자는 프로그래머에 게 가장 눈에 띄는 부분은 문서 및 보기입니다. 대부분의 응용 프로그램 프레임 워크를 개발 작업 문서 및 뷰 클래스 작성에 저장 합니다. 이 문서에서는 설명합니다.  
  
-   문서, 뷰 및 프레임 워크에 작용 하는 방법의 목적으로 합니다.  
  
-   해야 할 사항을 구현 하는 데 있습니다.  
  
 문서/뷰의 핵심은 네 가지 주요 클래스입니다.  
  
 [CDocument](../mfc/reference/cdocument-class.md) (또는 [COleDocument](../mfc/reference/coledocument-class.md)) 클래스 저장 또는 프로그램의 데이터를 제어 하는 데 사용 되는 개체를 지원 하며 프로그래머 정의 문서 클래스에 대 한 기본 기능을 제공 합니다. 문서는 사용자에서 일반적으로 파일 메뉴에서 열기 명령을 사용 하 여 열고 하 고 파일 메뉴에서 저장 명령을 사용 하 여 저장 하는 데이터의 단위를 나타냅니다.  
  
 [CView](../mfc/reference/cview-class.md) (또는 여러 파생된 클래스 중 하나) 프로그래머 정의 뷰 클래스에 대 한 기본 기능을 제공 합니다. 뷰는 문서에 연결 하 고 문서와 사용자 간의 중개자로 작동: 보기 문서 화면에 이미지를 렌더링 하 고 문서에 대 한 작업으로 사용자 입력 해석 합니다. 뷰는 또한 인쇄 및 인쇄 미리 보기 이미지를 렌더링합니다.  
  
 [CFrameWnd](../mfc/reference/cframewnd-class.md) (또는 해당 변형 중 하나)에 대 한 프레임을 하나 이상의 문서 뷰를 제공 하는 개체를 지원 합니다.  
  
 [CDocTemplate](../mfc/reference/cdoctemplate-class.md) (또는 [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) 또는 [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)) 지정 된 형식의 하나 이상의 기존 문서를 조정 하 고 올바른 만들기를 관리 하는 개체를 지원 합니다. 문서, 뷰 및 해당 형식에 대 한 프레임 창 개체를 선택 합니다.  
  
 다음 그림 문서와 해당 뷰 간의 관계를 보여 줍니다.  
  
 ![표시 되는 문서에 속하는 보기는](../mfc/media/vc379n1.gif "vc379n1")  
문서 및 보기  
  
 클래스 라이브러리의 문서/뷰 구현 데이터 자체의 디스플레이 데이터에 사용자 작업에서 분리합니다. 데이터의 모든 변경 내용은 문서 클래스를 통해 관리 됩니다. 보기에 액세스 하 고 데이터를 업데이트 하려면이 인터페이스를 호출 합니다.  
  
 문서, 연결 된 뷰, 및는 뷰에 프레임 창 문서 템플릿에 의해 생성 됩니다. 문서 서식 파일은 하나의 문서 종류의 모든 문서 만들기 및 관리 하는 일을 담당 합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>에 대 한 자세한 내용을 하 시겠습니까  
  
-   [문서/뷰 아키텍처의 개요](../mfc/a-portrait-of-the-document-view-architecture.md)  
  
-   [문서/뷰 아키텍처의 이점](../mfc/advantages-of-the-document-view-architecture.md)  
  
-   [응용 프로그램 마법사에서 만든 문서 및 뷰 클래스](../mfc/document-and-view-classes-created-by-the-mfc-application-wizard.md)  
  
-   [문서/뷰 아키텍처의 대체](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [단일 문서에 뷰 여러 개 추가](../mfc/adding-multiple-views-to-a-single-document.md)  
  
-   [문서 사용](../mfc/using-documents.md)  
  
-   [뷰 사용](../mfc/using-views.md)  
  
-   [여러 문서 형식, 뷰 및 프레임 창](../mfc/multiple-document-types-views-and-frame-windows.md)  
  
-   [초기화 및 문서 및 뷰 정리](../mfc/initializing-and-cleaning-up-documents-and-views.md)  
  
-   [문서 및 뷰 클래스에 직접 추가 된 초기화](../mfc/creating-new-documents-windows-and-views.md)  
  
-   [문서 및 뷰를 이용한 데이터베이스 클래스 사용](../data/mfc-using-database-classes-with-documents-and-views.md)  
  
-   [문서 및 뷰를 이용 하지 않는 데이터베이스 클래스를 사용 하 여](../data/mfc-using-database-classes-without-documents-and-views.md)  
  
-   [샘플](../visual-cpp-samples.md)  
  
## <a name="see-also"></a>참고 항목  
 [사용자 인터페이스 요소](../mfc/user-interface-elements-mfc.md)   
 [Windows](../mfc/windows.md)   
 [프레임 창](../mfc/frame-windows.md)   
 [문서 템플릿 및 문서/뷰 만들기 프로세스](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [문서/뷰 만들기](../mfc/document-view-creation.md)   
 [새 문서, 창 및 뷰 만들기](../mfc/creating-new-documents-windows-and-views.md)

