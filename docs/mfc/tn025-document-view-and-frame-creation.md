---
title: "TN025: 문서, 뷰 및 프레임 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.creation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "문서, 뷰 및 프레임 만들기"
  - "TN025"
ms.assetid: 09254d72-6e1d-43db-80e9-693887dbeda2
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN025: 문서, 뷰 및 프레임 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  다음 기술 노트는 온라인 설명서에 먼저 포함되어 있었으므로 업데이트되지 않았습니다.  따라서 일부 절차 및 항목은 만료되거나 올바르지 않을 수 있습니다.  최신 정보를 보려면 온라인 설명서 색인에서 관심 있는 항목을 검색하는 것이 좋습니다.  
  
 이 노트는 WinApps, DocTemplates, 문서, 프레임 및 뷰 생성 및 소유권 문제를 설명합니다.  
  
## WinApp  
 시스템에서 `CWinApp` 는 하나뿐입니다.  
  
 그것은 `WinMain` 의 프레임 워크의 내부 구현을 통해 생성되고 초기화됩니다.  어떤 작업을 유용하게 하려면 `CWinApp` 는 파생되어야 합니다. \(예외: 확장자 DLLs은 `CWinApp` 인스턴스를 가지지 않습니다\- 대신에 `DllMain` 에서 초기화가 완료됩니다\)  
  
 하나의 `CWinApp` 개체는 문서 템플릿의 목록을 가집니다\(`CPtrList`\)  응용 프로그램당 하나 이상의 문서 템플릿이 있습니다.  DocTemplates 는 `CWinApp::InitInstance` 내 리소스 파일\(문자열 배열\)에서 로드 됩니다.  
  
```  
pTemplate = new CDocTemplate(IDR_MYDOCUMENT, ...);  
AddDocTemplate(pTemplate);  
```  
  
 하나의 `CWinApp` 개체는 응용 프로그램에서 모든 프레임 창을 가집니다.  응용 프로그램에 대한 메인 프레임 창은 **CWinApp::m\_pMainWnd** 에 저장됩니다. 작업을 수행하는 응용 프로그램 마법사가 없는 경우 `InitInstance` 내에 `m_pMainWnd` 를 설정합니다.  단일 문서 인터페이스\(SDI\) 에 대해 문서 프레임 창뿐만 아니라 메인 응용 프로그램 프레임 창으로서 제공하는 `CFrameWnd` 는 하나 뿐입니다.  다중 문서 인터페이스\(MDI\)에 대해 모든 자식 `CFrameWnd` 들을 포함하는 메인 응용 프로그램 프레임 창으로서 제공하는 MDI 프레임\(`CMDIFrameWnd` 클래스\) 입니다.  각 자식 창은 `CMDIChildWnd` 클래스\(`CFrameWnd` 에서 파생된\) 중 하나 입니다. 이것은 잠재적인 많은 문서 프레임 창중 하나로서 제공됩니다.  
  
## DocTemplates  
 `CDocTemplate` 는 작성자와 관리자의 문서입니다.  생성 된 문서를 소유 하고 있습니다.  응용 프로그램이 아래에 설명된 것과 같이 리소스 기반의 접근방법을 사용하는 경우,`CDocTemplate` 에서 파생할 필요가 없습니다.  
  
 SDI 응용 프로그램에서 `CSingleDocTemplate` 클래스는 한 열린 문서를 추적 합니다.  MDI 응용 프로그램에서 `CMultiDocTemplate` 클래스는 템플릿으로 생성된 현재 열린 모든 파일의 목록을  `CPtrList` \) 보관합니다.   `CDocTemplate::AddDocument` 및 `CDocTemplate::RemoveDocument` 은 템플릿에서 문서를 추가하고 삭제하기 위해 가상 멤버 함수를 제공합니다.  `CDocTemplate` 는 **CDocument** 의 친구입니다. 따라서 보호되는 **CDocument::m\_pDocTemplate** 후방 포인터를 가르키기 위해 문서가 생성한 문서템플릿으로 설정할 수 있습니다.  
  
 `CWinApp` 는 모든 문서 템플릿을 다시 쿼리하는 기본 `OnFileOpen` 구현을 처리합니다.  구현은 이미 열려 있는 문서에서 새 문서를 열고 형식을 결정을 포함 합니다.  
  
 `CDocTemplate`는 문서 및 프레임에 대한 UI 바인딩을 관리합니다.  
  
 `CDocTemplate`는 명명 되지 않은 문서의 개수를 유지합니다.  
  
## CDocument  
 **CDocument** 는 `CDocTemplate` 가 소유합니다.  
  
 문서는 현재 보기 목록\(`CView`에서 파생된\) 을 가집니다. 이것은 문서를 보고 있습니다. \(`CPtrList`\)  
  
 문서는 보기를 생성하거나 파괴하지 않지만 생성된 후 서로 연결 됩니다.  문서를 닫을 때 \(파일\/닫기를 통해\), 연결 된 모든 뷰를 닫습니다.  \(즉, 창\/닫기를 통해\) 문서에서 마지막 보기가 닫힐 때 문서도 닫습니다.  
  
 `CDocument::AddView`, `RemoveView` 인터페이스는 목록 보기를 유지하기 위해 사용 됩니다.  **CDocument** 는 `CView` 는 친구입니다. 따라서 **CView::m\_pDocument** 후방 포인터를 설정할 수 있습니다.  
  
## CFrameWnd  
 `CFrameWnd` \(프레임으로 알려진\) 은 MFC 1.0에서 같은 역할을 하지만 현재 `CFrameWnd` 클래스는 새로운 클래스를 파생하지 않고 대부분에서 사용하기 위해 디자인 됩니다.  파생된 클래스 `CMDIFrameWnd` 및 `CMDIChildWnd` 은 향상되어 많은 표준 명령 대부분은 구현됩니다.  
  
 `CFrameWnd` 는 프레임의 클라이언트 영역에서 창을 생성해야 합니다.  일반적으로 프레임의 클라이언트 영역을 채우는 하나의 메인 창입니다.  
  
 MDI 프레임 창에 대해 클라이언트 영역은 모든 MDI 자식 프레임 창의 부모인 MDICLIENT 컨트롤로 차례로 채워집니다.  SDI 프레임 창 또는 MDI 자식 프레임 창에 대해, 클라이언트 영역은 대부분 창 개체에서 파생되는 `CView` 로 채워집니다.  `CSplitterWnd`의 경우, 보기의 클라이언트 영역은 `CSplitterWnd` 창 개체로 채워지고, 창 개체\(분할 창당 하나\)로 부터 파생된 `CView` 는 `CSplitterWnd` 의 자식창으로서 생성됩니다.  
  
## 참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)