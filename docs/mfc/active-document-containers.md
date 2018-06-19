---
title: 액티브 문서 컨테이너 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- active documents [MFC], containers
- active document containers [MFC]
- containers [MFC], active document
- MFC COM, active document containment
ms.assetid: ba20183a-8b4c-440f-9031-e5fcc41d391b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a47db4f9715c539ecf9bcbfb78e48b7e8edbc94b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33339029"
---
# <a name="active-document-containers"></a>액티브 문서 컨테이너
Microsoft Office Binder 또는 Internet Explorer와 같은 액티브 문서 컨테이너를 사용 하면 여러 문서를 만들고 각각에 대해 여러 응용 프로그램 프레임을 사용 하도록 요구 하는 것 (대신 단일 프레임 내에서 다른 응용 프로그램 종류의 작업을 문서 유형)입니다.  
  
 MFC 완벽 하 게 지원 액티브 문서 컨테이너에 `COleDocObjectItem` 클래스입니다. MFC 응용 프로그램 마법사를 사용 하 여 선택 하 여 액티브 문서 컨테이너를 만들 수는 **액티브 문서 컨테이너** 확인란은 **복합 문서 지원** MFC 응용 프로그램 마법사의 페이지입니다. 자세한 내용은 참조 [액티브 문서 컨테이너 응용 프로그램 만들기](../mfc/creating-an-active-document-container-application.md)합니다.  
  
 액티브 문서 컨테이너에 대 한 자세한 내용은 다음을 참조 하세요.  
  
-   [컨테이너 요구 사항](#container_requirements)  
  
-   [문서 사이트 개체](#document_site_objects)  
  
-   [사이트 개체 보기](#view_site_objects)  
  
-   [프레임 개체](#frame_object)  
  
-   [도움말 메뉴 병합](../mfc/help-menu-merging.md)  
  
-   [프로그래밍 방식 인쇄](../mfc/programmatic-printing.md)  
  
-   [명령 대상](../mfc/message-handling-and-command-targets.md)  
  
##  <a name="container_requirements"></a> 컨테이너 요구 사항  
 액티브 문서 지원 액티브 문서 컨테이너에 둘 이상의 인터페이스 구현을 의미: 포함 된 개체의 인터페이스를 사용 하 여 한 지식이 필요 합니다. 컨테이너는 액티브 문서 자체에 확장 인터페이스를 사용 하는 방법을 알고도 있어야 하는 액티브 문서 확장에도 마찬가지입니다.  
  
 활성 문서를 통합 하는 액티브 문서 컨테이너 수행 해야 합니다.  
  
-   개체를 통해 저장소를 처리할 수는 **IPersistStorage** 인터페이스, 즉, 제공 해야는 `IStorage` 각 활성 문서 인스턴스입니다.  
  
-   (문서 또는 포함 당 하나)는 "사이트" 개체 있으므로 해야 OLE 문서의 기본 포함 기능을 지원 구현 하는 **IOleClientSite** 및 **IAdviseSink**합니다.  
  
-   포함 된 개체 또는 활성 문서에는 내부 활성화를 지원 합니다. 컨테이너의 사이트 개체를 구현 해야 `IOleInPlaceSite` 컨테이너의 프레임 개체를 제공 해야 하 고 **IOleInPlaceFrame**합니다.  
  
-   액티브 문서는 확장을 구현 하 여 지원 `IOleDocumentSite` 문서에 설명 하는 컨테이너에 대 한 메커니즘을 제공 합니다. 컨테이너는 액티브 문서 인터페이스를 구현할 수는 필요에 따라 `IOleCommandTarget` 및 `IContinueCallback` 인쇄 하거나 저장할 같은 간단한 명령을 선택 하도록 합니다.  
  
 프레임 개체, 보기 개체 및 컨테이너 개체 선택적으로 구현할 수 **IOleCommandTarget** 에 설명 된 대로 특정 명령 디스패치를 지원 하기 위해 [명령 대상](../mfc/message-handling-and-command-targets.md)합니다. 컨테이너 개체도 선택적으로 구현할 수 `IPrint` 및 `IContinueCallback`에 설명 된 대로 프로그래밍 방식 인쇄를 지원 하기 위해 [프로그래밍 방식 인쇄](../mfc/programmatic-printing.md)합니다.  
  
 다음 그림의 컨테이너 및 (왼쪽)에 해당 구성 요소와 액티브 문서 (오른쪽)에 뷰 간의 개념적 관계를 보여 줍니다. 현재 문서 저장소 및 데이터를 관리 하 고 보기를 표시 하거나 선택적으로 해당 데이터를 인쇄 합니다. 굵게 표시 된 인터페이스는 액티브 문서 참여;에 필요한 이러한 굵게 및 기울임꼴는 선택적입니다. 다른 모든 인터페이스는 필수입니다.  
  
 ![액티브 문서 컨테이너 인터페이스](../mfc/media/vc37gj1.gif "vc37gj1")  
  
 하나의 구체적 클래스에는 하나의 뷰만 지원 문서 보기와 문서 모두 구성 요소 (즉, 해당 인터페이스)를 구현할 수 있습니다. 또한 한 번에 하나의 뷰만 지원 하는 컨테이너 사이트 결합할 수 문서 사이트 및 사이트 보기는 단일 구체적인 사이트 클래스. 그러나 컨테이너의 프레임 개체 유지 distinct, 되 고 컨테이너의 문서 구성 요소는 단순히 여기에 포함 된 아키텍처;의 완전 한 설명을 제공 하려면 액티브 문서 포함 아키텍처에서 영향을 받지 않습니다.  
  
##  <a name="document_site_objects"></a> 문서 사이트 개체  
 액티브 문서 포함 아키텍처에서 문서 사이트는 클라이언트 사이트에 추가 하 여 OLE 문서에서 개체와 동일한는 `IOleDocument` 인터페이스:  
  
 `interface IOleDocumentSite : IUnknown`  
  
 `{`  
  
 `HRESULT ActivateMe(IOleDocumentView *pViewToActivate);`  
  
 `}`  
  
 문서 사이트는 개념적으로 하나 이상의 "보기 사이트" 개체에 대 한 컨테이너입니다. 각 보기 사이트 개체 문서 사이트에 의해 관리 되는 문서의 각 뷰 개체와 연결 됩니다. 컨테이너 문서 사이트 마다 단일 뷰만 지원, 문서 사이트와 보기 사이트는 하나의 구체적 클래스에 구현할 수 있습니다.  
  
##  <a name="view_site_objects"></a> 사이트 개체 보기  
 컨테이너의 보기 사이트 개체는 문서의 특정 보기에 표시 공간을 관리합니다. 표준을 지원할 뿐 아니라 `IOleInPlaceSite` 인터페이스를 구현 또한 일반적으로 사이트 보기 `IContinueCallback` 프로그래밍 방식 인쇄 컨트롤에 대 한 합니다. (View 개체를 되지에 대 한 쿼리는 `IContinueCallback` 에 실제로 구현할 수 있도록 모든 개체 컨테이너 필요 합니다.)  
  
 여러 뷰를 지원 하는 컨테이너 문서 사이트 내 사이트 개체에 여러 보기를 만들 수 있어야 합니다. 통해 제공 된 별도 활성화 및 비활성화 서비스와 각 보기를 제공이 `IOleInPlaceSite`합니다.  
  
##  <a name="frame_object"></a> 프레임 개체  
 컨테이너의 프레임 개체는 대부분의 경우 즉 OLE 문서에서 내부 활성화에 사용 되는 동일한 프레임, 메뉴 및 도구 모음 협상을 처리 하는 것입니다. View 개체를 통해이 프레임 개체에 대 한 액세스는 **IOleInPlaceSite::GetWindowContext**, 또한 (도구 모음 창 수준 협상을 처리할 수 있는 컨테이너 문서를 나타내는 컨테이너 개체에 대 한 액세스를 제공 하는 및 포함 된 개체를 열거)입니다.  
  
 액티브 문서 컨테이너를 추가 하 여 프레임을 강화할 수 `IOleCommandTarget`합니다. 이렇게 하면 현재 문서의 사용자 인터페이스에서이 인터페이스에서 동일한 명령을 보내도록 컨테이너를 허용할 수에 관계 없이 동일한 방식으로 발생 하는 명령을 받을 수 (같은 **새 파일**, **열려**,  **다른 이름으로 저장**, **인쇄**; **복사본 편집**, **붙여넣기**, **실행 취소**, 및 기타) 현재 문서에 있습니다. 자세한 내용은 참조 [명령 대상](../mfc/message-handling-and-command-targets.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [활성 문서 포함](../mfc/active-document-containment.md)

