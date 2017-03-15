---
title: "서버: 서버 항목 | Microsoft Docs"
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
  - "아키텍처[C++], 서버 항목"
  - "OLE 서버 응용 프로그램, 서버 항목"
  - "서버 항목"
  - "서버 항목, 구현"
  - "서버[C++], 서버 항목"
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 서버: 서버 항목
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용자가 포함 또는 연결된 OLE 항목을 편집 할 수 있도록 컨테이너가 서버를 시작하면 서버 응용 프로그램은 "서버 항목"을 만듭니다.  `COleServerItem` 에서 파생 된 클래스의 개체인 서버 항목은 서버 문서의 컨테이너 응용 프로그램 사이의 인터페이스를 제공합니다.  
  
 `COleServerItem`  클래스는 컨테이너에서 요청에 따라서 일반적으로 OLE에 의해 호출 된 여러 재정의 가능한 멤버 함수를 정의합니다.  서버 항목 서버 문서 또는 전체 문서를 나타낼 수 있습니다.  OLE 항목이 컨테이너 문서의 포함되면 서버 항목은 전체 서버 문서를 나타냅니다.  OLE 항목이 연결된 서버 항목은 링크가 일부 또는 전부인지에 따라 서버 문서 또는 문서 전체의 일부를 나타낼 수 있습니다.  
  
 [HIERSVR](../top/visual-cpp-samples.md)샘플에서, 예를 들어, 서버 항목 클래스  **CServerItem**는 **CServerNode**클래스 개체에 대한 포인터인 멤버를 갖습니다.   **CServerNode** 개체는 트리인 HIERSVR 응용 프로그램의 문서의 노드입니다.  **CServerNode** 개체가 루트 노드인 경우에,  **CServerItem** 개체는 문서 전체를 나타냅니다.  **CServerNode**개체가 자식 노드인 경우에,  **CServerItem** 개체는 문서의 부분을 나타냅니다.  이 상호 작용의 예제를 보려면 [HIERSVR](../top/visual-cpp-samples.md) MFC OLE 샘플을 참조하십시오.  
  
##  <a name="_core_implementing_server_items"></a> 서버 항목 구현  
 응용 프로그램은 "시작"코드를 생성하는 응용 프로그램 마법사를 사용하는 경우, 스타터 코드에서 서버의 항목이 포함되도록해야 할 모든 OLE 옵션 페이지에서 서버 옵션 중 하나를 선택해야합니다.  기존 응용 프로그램 서버 항목을 추가하는 경우 다음 단계를 수행합니다.  
  
#### 서버 항목을 구현 하려면  
  
1.  `COleServerItem`에서 클래스를 파생시킵니다.  
  
2.  파생된 클래스에서  `OnDraw`  멤버 함수를 재정의합니다.  
  
     프레임 워크는0  `OnDraw` 을 호출하여 OLE 항목을 메타 파일로 렌더링합니다.  컨테이너 응용 프로그램 항목을 렌더링 하려면 이 메타 파일을 사용합니다.  응용 프로그램의 뷰 클래스에는  `OnDraw`  멤버 함수를 가집니다. 이는 서버 응용 프로그램이 활성화 되어 있을 때 항목을 렌더링 하는 데 사용됩니다.  
  
3.  서버 문서 클래스에 대한  `OnGetEmbeddedItem` 의 재정의를 구현합니다.  자세한 내용은  [서버: 서버 문서 구현](../mfc/servers-implementing-server-documents.md) 문서와 [HIERSVR](../top/visual-cpp-samples.md)MFC OLE 샘플을 참조하십시오.  
  
4.  서버 항목 클래스의  `OnGetExtent`  멤버 함수를 구현합니다.  프레임 워크는 항목의 크기를 검색하기 위해 이 함수를 호출합니다.  기본적으로 구현해도 수행되는 작업은 없습니다.  
  
##  <a name="_core_a_tip_for_server.2d.item_architecture"></a> 서버 항목 아키텍처에 대한 팁  
 [서버 항목 구현](#_core_implementing_server_items)에서 설명한 것 처럼, 서버 응용 프로그램은 서버 보기 및 컨테이너 응용 프로그램에서 사용하는 메타 파일의 항목을 렌더링 해야 합니다.  Microsoft 기반 클래스 라이브러리 응용 프로그램 아키텍처에서 뷰 클래스의  `OnDraw`  멤버 함수는 수정할 때 항목을 렌더링합니다. \(*클래스 라이브러리 참조*의 [cview:: Ondraw](../Topic/CView::OnDraw.md)를 참조하십시오\).  서버 항목의  `OnDraw` 는 다른 모든 경우에  항목을 메타 파일로 렌더링합니다\([COleServerItem::OnDraw](../Topic/COleServerItem::OnDraw.md)를 참조하십시오\).  
  
 서버 문서 클래스의 도우미 함수를 작성하고 뷰와 서버 항목 클래스의  `OnDraw`  함수로부터 그들을 호출하여 코드의 중복을 방지할 수 있습니다.   MFC OLE 샘플  [HIERSVR](../top/visual-cpp-samples.md)은  이 전략을 사용합니다: 함수  **CServerView::OnDraw** 및  **CServerItem::OnDraw**은 모두  **CServerDoc::DrawTree**를 호출하여  항목을 렌더링합니다.  
  
 다양한 상황에서 그리기 때문에, 보기 및 항목은 모두  `OnDraw`  멤버 함수를 가집니다.  보기 확대\/축소, 선택 영역 크기 및 범위, 클리핑 및 스크롤 막대 같은 사용자 인터페이스 요소와 같은 요소를 고려해야 합니다.  반면에 서버 항목은 항상 전체 OLE 개체를 그립니다.  
  
 자세한 내용은  *클래스 라이브러리 참조*의  [cview:: Ondraw](../Topic/CView::OnDraw.md),  [COleServerItem](../mfc/reference/coleserveritem-class.md),  [COleServerItem::OnDraw](../Topic/COleServerItem::OnDraw.md), 및   [COleServerDoc::OnGetEmbeddedItem](../Topic/COleServerDoc::OnGetEmbeddedItem.md)를 참조하십시오.  
  
## 참고 항목  
 [서버](../mfc/servers.md)