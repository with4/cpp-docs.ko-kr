---
title: "COleServerDoc Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleServerDoc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleServerDoc class"
  - "container/server applications"
  - "OLE containers, server documents"
  - "OLE 서버 응용 프로그램, managing server documents"
  - "OLE server documents"
  - "server documents, OLE"
  - "서버, OLE"
ms.assetid: a9cdd96a-e0ac-43bb-9203-2c29237e965c
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# COleServerDoc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE 서버 문서에 대 한 기본 클래스입니다.  
  
## 구문  
  
```  
class AFX_NOVTABLE COleServerDoc : public COleLinkingDoc  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleServerDoc::COleServerDoc](../Topic/COleServerDoc::COleServerDoc.md)|`COleServerDoc` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleServerDoc::ActivateDocObject](../Topic/COleServerDoc::ActivateDocObject.md)|연결 된 DocObject 문서를 활성화합니다.|  
|[COleServerDoc::ActivateInPlace](../Topic/COleServerDoc::ActivateInPlace.md)|현재 위치에서 편집할 문서를 활성화합니다.|  
|[COleServerDoc::DeactivateAndUndo](../Topic/COleServerDoc::DeactivateAndUndo.md)|서버 사용자 인터페이스를 비활성화합니다.|  
|[COleServerDoc::DiscardUndoState](../Topic/COleServerDoc::DiscardUndoState.md)|실행 취소 상태 정보를 삭제합니다.|  
|[COleServerDoc::GetClientSite](../Topic/COleServerDoc::GetClientSite.md)|검색 하는 기본 포인터 `IOleClientSite` 인터페이스.|  
|[COleServerDoc::GetEmbeddedItem](../Topic/COleServerDoc::GetEmbeddedItem.md)|포인터가 문서 전체를 나타내는 항목을 반환 합니다.|  
|[COleServerDoc::GetItemClipRect](../Topic/COleServerDoc::GetItemClipRect.md)|현재 위치에서 편집 하기 위해 현재 클리핑 사각형을 반환합니다.|  
|[COleServerDoc::GetItemPosition](../Topic/COleServerDoc::GetItemPosition.md)|내부 편집 기능에 대 한 컨테이너 응용 프로그램의 클라이언트 영역을 기준으로 현재 위치 사각형을 반환합니다.|  
|[COleServerDoc::GetZoomFactor](../Topic/COleServerDoc::GetZoomFactor.md)|확대\/축소 비율을 픽셀 단위로 반환합니다.|  
|[COleServerDoc::IsDocObject](../Topic/COleServerDoc::IsDocObject.md)|문서는 DocObject 인지 여부를 확인 합니다.|  
|[COleServerDoc::IsEmbedded](../Topic/COleServerDoc::IsEmbedded.md)|문서 컨테이너 문서의 포함 된 또는 독립 실행형 실행 여부를 나타냅니다.|  
|[COleServerDoc::IsInPlaceActive](../Topic/COleServerDoc::IsInPlaceActive.md)|반환 `TRUE` 항목의 현재 위치에서 활성화 되어 있는 경우.|  
|[COleServerDoc::NotifyChanged](../Topic/COleServerDoc::NotifyChanged.md)|컨테이너 문서의 사용자 변경 되었음을 알립니다.|  
|[COleServerDoc::NotifyClosed](../Topic/COleServerDoc::NotifyClosed.md)|컨테이너 문서의 사용자 닫 혔 음을 알립니다.|  
|[COleServerDoc::NotifyRename](../Topic/COleServerDoc::NotifyRename.md)|사용자 문서를 이름이 있는 컨테이너에 알립니다.|  
|[COleServerDoc::NotifySaved](../Topic/COleServerDoc::NotifySaved.md)|사용자가 문서를 저장 한 컨테이너에 알립니다.|  
|[COleServerDoc::OnDeactivate](../Topic/COleServerDoc::OnDeactivate.md)|사용자가 현재 위치에서 활성화 된 항목을 비활성화 하면 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::OnDeactivateUI](../Topic/COleServerDoc::OnDeactivateUI.md)|컨트롤 및 기타 사용자 인터페이스 요소를 현재 위치에서 활성화를 위해 만든 파괴 하는 프레임 워크에서 호출 합니다.|  
|[COleServerDoc::OnDocWindowActivate](../Topic/COleServerDoc::OnDocWindowActivate.md)|컨테이너 문서 프레임 창의 활성화 또는 비활성화 되 면 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::OnResizeBorder](../Topic/COleServerDoc::OnResizeBorder.md)|컨테이너 응용 프로그램의 프레임 창 또는 문서 창의 크기를 조정할 때 프레임 워크에 의해 호출 됩니다.|  
|[COleServerDoc::OnShowControlBars](../Topic/COleServerDoc::OnShowControlBars.md)|현재 위치에서 편집 컨트롤 막대 표시 또는 숨기기 프레임 워크에서 호출 합니다.|  
|[COleServerDoc::OnUpdateDocument](../Topic/COleServerDoc::OnUpdateDocument.md)|항목 컨테이너의 복사본이 업데이트 서버 문서에 포함 된 항목을 저장할 때 프레임 워크에 의해 호출 됩니다.|  
|[COleServerDoc::RequestPositionChange](../Topic/COleServerDoc::RequestPositionChange.md)|내부 편집 프레임의 위치를 변경합니다.|  
|[COleServerDoc::SaveEmbedding](../Topic/COleServerDoc::SaveEmbedding.md)|문서를 저장 하는 컨테이너 응용 프로그램에 알려 줍니다.|  
|[COleServerDoc::ScrollContainerBy](../Topic/COleServerDoc::ScrollContainerBy.md)|컨테이너 문서를 스크롤합니다.|  
|[COleServerDoc::UpdateAllItems](../Topic/COleServerDoc::UpdateAllItems.md)|컨테이너 문서의 사용자 변경 되었음을 알립니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleServerDoc::CreateInPlaceFrame](../Topic/COleServerDoc::CreateInPlaceFrame.md)|내부 편집을 위해 프레임 창을 만들 수 있는 프레임 워크에서 호출 합니다.|  
|[COleServerDoc::DestroyInPlaceFrame](../Topic/COleServerDoc::DestroyInPlaceFrame.md)|내부 편집을 위해 프레임 창을 소멸 하는 프레임 워크에서 호출 합니다.|  
|[COleServerDoc::GetDocObjectServer](../Topic/COleServerDoc::GetDocObjectServer.md)|새로 만들려면이 함수를 재정의 `CDocObjectServer` 개체 및이 문서 DocObject 컨테이너 임을 나타냅니다.|  
|[COleServerDoc::OnClose](../Topic/COleServerDoc::OnClose.md)|컨테이너 문서를 닫으려면 요청 하면 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::OnExecOleCmd](../Topic/COleServerDoc::OnExecOleCmd.md)|지정 된 명령을 실행 하거나 명령 도움말을 표시 합니다.|  
|[COleServerDoc::OnFrameWindowActivate](../Topic/COleServerDoc::OnFrameWindowActivate.md)|컨테이너의 프레임 창이 활성화 또는 비활성화 되 면 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::OnGetEmbeddedItem](../Topic/COleServerDoc::OnGetEmbeddedItem.md)|가져오기 위해 호출 된 `COleServerItem` 나타내는 전체 문서. 포함 된 항목을 사용 합니다.  구현이 필요 합니다.|  
|[COleServerDoc::OnReactivateAndUndo](../Topic/COleServerDoc::OnReactivateAndUndo.md)|현재 위치에서 편집 하는 동안 변경한 내용을 실행 취소 하는 프레임 워크에서 호출 합니다.|  
|[COleServerDoc::OnSetHostNames](../Topic/COleServerDoc::OnSetHostNames.md)|창 제목에 포함 된 개체의 컨테이너를 설정 하면 프레임 워크에서 호출 됩니다.|  
|[COleServerDoc::OnSetItemRects](../Topic/COleServerDoc::OnSetItemRects.md)|컨테이너 응용 프로그램의 창 내에서 내부 편집 프레임 창의 위치를 프레임 워크에서 호출 합니다.|  
|[COleServerDoc::OnShowDocument](../Topic/COleServerDoc::OnShowDocument.md)|표시 또는 숨기기 문서를 프레임 워크에서 호출 됩니다.|  
  
## 설명  
 서버 문서를 포함할 수 있습니다  [COleServerItem](../../mfc/reference/coleserveritem-class.md) 서버 인터페이스에 포함 되거나 연결 된 항목을 나타내는 개체입니다.  컨테이너에서 포함 된 항목을 편집 하려면 서버 응용 프로그램을 시작할 때 항목 자체 서버 문서로 로드 됩니다. `COleServerDoc` 개체를 하나만 포함 `COleServerItem` 개체의 전체 문서를 구성 합니다.  컨테이너 연결된 항목을 편집 하 여 서버 응용 프로그램을 시작 하면 기존 문서는 디스크에서 로드 됩니다. 문서의 목차 부분에 연결 된 항목을 나타내기 위해 강조 표시 됩니다.  
  
 `COleServerDoc`개체의 항목이 포함 될 수 있습니다는  [활성화](../../mfc/reference/coleclientitem-class.md) 클래스입니다.  컨테이너 \/ 서버 응용 프로그램을 만들 수 있습니다.  함수를 올바르게 저장 하는 프레임 워크를 제공는 `COleClientItem` 처리 하는 동안 항목을 `COleServerItem` 개체.  
  
 서버 응용 프로그램이 연결을 지원 하지 않으면 서버 문서 문서가 포함 된 개체로 전체를 나타내는 하나의 서버 항목이 항상 포함 됩니다.  링크 서버 응용 프로그램을 지원 하지 않으면 서버 항목 선택 영역을 클립보드에 복사 될 때마다 만들어야 합니다.  
  
 사용 `COleServerDoc`, 클래스에서 파생 하 여 구현 된  [OnGetEmbeddedItem](../Topic/COleServerDoc::OnGetEmbeddedItem.md) 포함 된 항목을 지원 하도록 서버 허용 하는 멤버 함수.  파생 클래스에서 `COleServerItem` 문서에 항목을 구현 하 고 해당 클래스에서 개체를 반환 하려면 `OnGetEmbeddedItem`.  
  
 연결 된 항목을 지원 하도록 `COleServerDoc` 제공 된  [OnGetLinkedItem](../Topic/COleLinkingDoc::OnGetLinkedItem.md) 멤버 함수.  기본 구현을 사용 하거나 자신의 방식으로 관리 문서 항목의 경우 재정의할 수 있습니다.  
  
 필요한 `COleServerDoc`\-응용 프로그램에서 지 원하는 각 서버 유형의 문서에 대 한 클래스를 파생 합니다.  워크시트와 차트 서버 응용 프로그램을 지원 합니다. 예를 들어, 두 경우 `COleServerDoc`\-클래스를 파생 합니다.  
  
 서버에 대 한 자세한 내용은  [서버: 서버 구현](../../mfc/servers-implementing-a-server.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md)  
  
 `COleServerDoc`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [HIERSVR MFC 샘플](../../top/visual-cpp-samples.md)   
 [COleLinkingDoc Class](../../mfc/reference/colelinkingdoc-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDocument Class](../../mfc/reference/coledocument-class.md)   
 [COleLinkingDoc Class](../../mfc/reference/colelinkingdoc-class.md)   
 [COleTemplateServer Class](../../mfc/reference/coletemplateserver-class.md)