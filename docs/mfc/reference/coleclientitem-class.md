---
title: "COleClientItem Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleClientItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "client items and OLE containers"
  - "COleClientItem class"
  - "container interface class"
  - "OLE client item class"
  - "OLE containers, client items"
  - "OLE containers, interface 클래스"
ms.assetid: 7f571b7c-2758-4839-847a-0cf1ef643128
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleClientItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE 항목의 컨테이너 인터페이스를 정의합니다.  
  
## 구문  
  
```  
class COleClientItem : public CDocItem  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleClientItem::COleClientItem](../Topic/COleClientItem::COleClientItem.md)|`COleClientItem` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleClientItem::Activate](../Topic/COleClientItem::Activate.md)|작업에 대 한 OLE 항목 열고 지정 된 동사를 실행 합니다.|  
|[COleClientItem::ActivateAs](../Topic/COleClientItem::ActivateAs.md)|다른 형식으로 항목을 활성화합니다.|  
|[COleClientItem::AttachDataObject](../Topic/COleClientItem::AttachDataObject.md)|OLE 개체의 데이터에 액세스합니다.|  
|[COleClientItem::CanCreateFromData](../Topic/COleClientItem::CanCreateFromData.md)|컨테이너 응용 프로그램에서 포함 된 개체를 만들 수 있는지 여부를 나타냅니다.|  
|[COleClientItem::CanCreateLinkFromData](../Topic/COleClientItem::CanCreateLinkFromData.md)|컨테이너 응용 프로그램에서 연결 된 개체를 만들 수 있는지 여부를 나타냅니다.|  
|[COleClientItem::CanPaste](../Topic/COleClientItem::CanPaste.md)|클립보드 OLE 포함할 수 또는 정적 항목이 포함 되어 있는지 여부를 나타냅니다.|  
|[COleClientItem::CanPasteLink](../Topic/COleClientItem::CanPasteLink.md)|클립보드 linkable OLE 항목이 포함 되어 있는지 여부를 나타냅니다.|  
|[COleClientItem::Close](../Topic/COleClientItem::Close.md)|링크 서버를 닫고 OLE 항목을 삭제 하지 않습니다.|  
|[COleClientItem::ConvertTo](../Topic/COleClientItem::ConvertTo.md)|항목을 다른 형식으로 변환 합니다.|  
|[COleClientItem::CopyToClipboard](../Topic/COleClientItem::CopyToClipboard.md)|OLE 항목을 클립보드에 복사합니다.|  
|[COleClientItem::CreateCloneFrom](../Topic/COleClientItem::CreateCloneFrom.md)|기존 항목을 복제 합니다.|  
|[COleClientItem::CreateFromClipboard](../Topic/COleClientItem::CreateFromClipboard.md)|클립보드에서 포함 된 항목을 만듭니다.|  
|[COleClientItem::CreateFromData](../Topic/COleClientItem::CreateFromData.md)|데이터 개체에서 포함 된 항목을 만듭니다.|  
|[COleClientItem::CreateFromFile](../Topic/COleClientItem::CreateFromFile.md)|파일에서 포함 된 항목을 만듭니다.|  
|[COleClientItem::CreateLinkFromClipboard](../Topic/COleClientItem::CreateLinkFromClipboard.md)|클립보드의 연결된 항목을 만듭니다.|  
|[COleClientItem::CreateLinkFromData](../Topic/COleClientItem::CreateLinkFromData.md)|데이터 개체에서 연결 된 항목을 만듭니다.|  
|[COleClientItem::CreateLinkFromFile](../Topic/COleClientItem::CreateLinkFromFile.md)|파일에서 연결 된 항목을 만듭니다.|  
|[COleClientItem::CreateNewItem](../Topic/COleClientItem::CreateNewItem.md)|서버 응용 프로그램을 실행 하 여 포함 된 새 항목을 만듭니다.|  
|[COleClientItem::CreateStaticFromClipboard](../Topic/COleClientItem::CreateStaticFromClipboard.md)|클립보드에서 있는 정적 항목을 만듭니다.|  
|[COleClientItem::CreateStaticFromData](../Topic/COleClientItem::CreateStaticFromData.md)|정적 항목에 데이터 개체를 만듭니다.|  
|[COleClientItem::Deactivate](../Topic/COleClientItem::Deactivate.md)|항목을 비활성화합니다.|  
|[COleClientItem::DeactivateUI](../Topic/COleClientItem::DeactivateUI.md)|컨테이너 응용 프로그램의 사용자 인터페이스를 원래 상태로 복원합니다.|  
|[COleClientItem::Delete](../Topic/COleClientItem::Delete.md)|삭제 또는 연결 된 항목이 있는 경우 OLE 항목을 닫습니다.|  
|[COleClientItem::DoDragDrop](../Topic/COleClientItem::DoDragDrop.md)|끌어서 놓기 작업을 수행합니다.|  
|[COleClientItem::DoVerb](../Topic/COleClientItem::DoVerb.md)|지정 된 동사를 실행합니다.|  
|[COleClientItem::Draw](../Topic/COleClientItem::Draw.md)|OLE 항목을 그립니다.|  
|[COleClientItem::GetActiveView](../Topic/COleClientItem::GetActiveView.md)|보기를에 항목이 내부에서 활성화 될 가져옵니다.|  
|[COleClientItem::GetCachedExtent](../Topic/COleClientItem::GetCachedExtent.md)|OLE 항목의 사각형의 경계를 반환 합니다.|  
|[COleClientItem::GetClassID](../Topic/COleClientItem::GetClassID.md)|존재 하는 항목의 클래스 ID를 가져옵니다.|  
|[COleClientItem::GetClipboardData](../Topic/COleClientItem::GetClipboardData.md)|호출 하 여 클립보드에 넣을 수 있는 데이터를 가져옵니다는 `CopyToClipboard` 멤버 함수입니다.|  
|[COleClientItem::GetDocument](../Topic/COleClientItem::GetDocument.md)|반환 된 `COleDocument` 있는 항목을 포함 하는 개체입니다.|  
|[COleClientItem::GetDrawAspect](../Topic/COleClientItem::GetDrawAspect.md)|항목의 현재 보기를에 렌더링을 가져옵니다.|  
|[COleClientItem::GetExtent](../Topic/COleClientItem::GetExtent.md)|OLE 항목의 사각형의 경계를 반환 합니다.|  
|[COleClientItem::GetIconFromRegistry](../Topic/COleClientItem::GetIconFromRegistry.md)|특정 CLSID의 서버와 관련 된 아이콘에 대 한 핸들입니다.|  
|[COleClientItem::GetIconicMetafile](../Topic/COleClientItem::GetIconicMetafile.md)|항목의 아이콘을 그리는 데 사용 되는 메타 파일을 가져옵니다.|  
|[COleClientItem::GetInPlaceWindow](../Topic/COleClientItem::GetInPlaceWindow.md)|항목의 현재 위치에서 편집 창에 대 한 포인터를 반환합니다.|  
|[COleClientItem::GetItemState](../Topic/COleClientItem::GetItemState.md)|항목의 현재 상태를 가져옵니다.|  
|[COleClientItem::GetLastStatus](../Topic/COleClientItem::GetLastStatus.md)|마지막 OLE 작업의 상태를 반환합니다.|  
|[COleClientItem::GetLinkUpdateOptions](../Topic/COleClientItem::GetLinkUpdateOptions.md)|연결 된 항목 \(고급 기능\)에 대 한 업데이트 모드를 반환합니다.|  
|[COleClientItem::GetType](../Topic/COleClientItem::GetType.md)|OLE 항목의 형식 \(포함, 연결, 또는 정적\)을 반환합니다.|  
|[COleClientItem::GetUserType](../Topic/COleClientItem::GetUserType.md)|항목의 형식을 설명 하는 문자열을 가져옵니다.|  
|[COleClientItem::IsInPlaceActive](../Topic/COleClientItem::IsInPlaceActive.md)|반환 `TRUE` 항목의 경우 현재 위치에서 활성화 합니다.|  
|[COleClientItem::IsLinkUpToDate](../Topic/COleClientItem::IsLinkUpToDate.md)|반환  **TRUE** 연결 된 항목은 원본 문서와 최신 이면.|  
|[COleClientItem::IsModified](../Topic/COleClientItem::IsModified.md)|반환 `TRUE` 항목이 마지막으로 저장 된 이후 수정 되었으면 합니다.|  
|[COleClientItem::IsOpen](../Topic/COleClientItem::IsOpen.md)|반환 `TRUE` 항목은 서버 응용 프로그램에서 현재 열려 있는 경우.|  
|[COleClientItem::IsRunning](../Topic/COleClientItem::IsRunning.md)|반환 `TRUE` 항목의 서버 응용 프로그램을 실행 하는 경우.|  
|[COleClientItem::OnActivate](../Topic/COleClientItem::OnActivate.md)|프레임 워크에서 활성화 된 항목에 알리기 위해 호출 됩니다.|  
|[COleClientItem::OnActivateUI](../Topic/COleClientItem::OnActivateUI.md)|프레임 워크에서 활성화 되 고 해당 사용자 인터페이스를 표시 해야 하는 항목에 알리기 위해 호출 됩니다.|  
|[COleClientItem::OnChange](../Topic/COleClientItem::OnChange.md)|서버 OLE 항목이 변경 될 때 호출 됩니다.  구현이 필요 합니다.|  
|[COleClientItem::OnDeactivate](../Topic/COleClientItem::OnDeactivate.md)|항목 비활성화 될 때 프레임 워크에 의해 호출 됩니다.|  
|[COleClientItem::OnDeactivateUI](../Topic/COleClientItem::OnDeactivateUI.md)|서버는 전체 사용자 인터페이스를 제거 하면 프레임 워크에서 호출 됩니다.|  
|[COleClientItem::OnGetClipboardData](../Topic/COleClientItem::OnGetClipboardData.md)|클립보드에 복사할 데이터를 가져올 수 있는 프레임 워크에서 호출 합니다.|  
|[COleClientItem::OnInsertMenus](../Topic/COleClientItem::OnInsertMenus.md)|합성 메뉴를 만들 수 있는 프레임 워크에서 호출 됩니다.|  
|[COleClientItem::OnRemoveMenus](../Topic/COleClientItem::OnRemoveMenus.md)|컨테이너 메뉴 합성 메뉴에서 제거 하는 프레임 워크에서 호출 합니다.|  
|[COleClientItem::OnSetMenu](../Topic/COleClientItem::OnSetMenu.md)|설치는 합성 메뉴를 제거 하는 프레임 워크에서 호출 됩니다.|  
|[COleClientItem::OnShowControlBars](../Topic/COleClientItem::OnShowControlBars.md)|컨트롤 막대를 표시 하는 프레임 워크에서 호출 됩니다.|  
|[COleClientItem::OnUpdateFrameTitle](../Topic/COleClientItem::OnUpdateFrameTitle.md)|프레임 창의 제목 표시줄을 업데이트 하는 프레임 워크에서 호출 됩니다.|  
|[COleClientItem::ReactivateAndUndo](../Topic/COleClientItem::ReactivateAndUndo.md)|항목 다시 활성화 하 고 마지막 위치에서 편집 작업을 취소 합니다.|  
|[COleClientItem::Release](../Topic/COleClientItem::Release.md)|OLE 항목을 연결 하는 연결 해제 하 고 열린 상태를 닫습니다.  클라이언트 항목은 삭제 되지 않습니다.|  
|[COleClientItem::Reload](../Topic/COleClientItem::Reload.md)|항목에 대 한 호출 후 다시 로드 하는 `ActivateAs`.|  
|[COleClientItem::Run](../Topic/COleClientItem::Run.md)|항목과 연결 된 응용 프로그램을 실행 합니다.|  
|[COleClientItem::SetDrawAspect](../Topic/COleClientItem::SetDrawAspect.md)|항목의 현재 보기에 렌더링을 설정합니다.|  
|[COleClientItem::SetExtent](../Topic/COleClientItem::SetExtent.md)|OLE 항목의 경계 사각형을 설정합니다.|  
|[COleClientItem::SetHostNames](../Topic/COleClientItem::SetHostNames.md)|OLE 항목을 편집할 경우 서버는 표시 이름을 설정 합니다.|  
|[COleClientItem::SetIconicMetafile](../Topic/COleClientItem::SetIconicMetafile.md)|항목의 아이콘을 그리는 데 사용 되는 메타 파일을 캐시 합니다.|  
|[COleClientItem::SetItemRects](../Topic/COleClientItem::SetItemRects.md)|항목의 경계 사각형을 설정합니다.|  
|[COleClientItem::SetLinkUpdateOptions](../Topic/COleClientItem::SetLinkUpdateOptions.md)|연결 된 항목 \(고급 기능\)에 대 한 업데이트 모드를 설정합니다.|  
|[COleClientItem::SetPrintDevice](../Topic/COleClientItem::SetPrintDevice.md)|이 클라이언트 항목에 대 한 대상 인쇄 장치를 설정합니다.|  
|[COleClientItem::UpdateLink](../Topic/COleClientItem::UpdateLink.md)|프레젠테이션 캐시 항목을 업데이트합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleClientItem::CanActivate](../Topic/COleClientItem::CanActivate.md)|현재 위치에서 활성화를 허용 여부를 결정 하는 프레임 워크에서 호출 됩니다.|  
|[COleClientItem::OnChangeItemPosition](../Topic/COleClientItem::OnChangeItemPosition.md)|항목의 위치가 변경 되 면 프레임 워크에서 호출 됩니다.|  
|[COleClientItem::OnDeactivateAndUndo](../Topic/COleClientItem::OnDeactivateAndUndo.md)|활성화 후 취소 하는 프레임 워크에서 호출 합니다.|  
|[COleClientItem::OnDiscardUndoState](../Topic/COleClientItem::OnDiscardUndoState.md)|항목의 실행 취소 상태 정보를 삭제 하는 프레임 워크에서 호출 됩니다.|  
|[COleClientItem::OnGetClipRect](../Topic/COleClientItem::OnGetClipRect.md)|가져올 항목의 클리핑 사각형 좌표 프레임 워크에서 호출 됩니다.|  
|[COleClientItem::OnGetItemPosition](../Topic/COleClientItem::OnGetItemPosition.md)|보기 기준으로 항목의 위치를 가져오려면 프레임 워크에서 호출 합니다.|  
|[COleClientItem::OnGetWindowContext](../Topic/COleClientItem::OnGetWindowContext.md)|항목이 내부에서 활성화 될 때 프레임 워크에 의해 호출 됩니다.|  
|[COleClientItem::OnScrollBy](../Topic/COleClientItem::OnScrollBy.md)|항목을 스크롤 하는 프레임 워크에서 호출 합니다.|  
|[COleClientItem::OnShowItem](../Topic/COleClientItem::OnShowItem.md)|OLE 항목을 표시 하는 프레임 워크에서 호출 됩니다.|  
  
## 설명  
 OLE 항목을 만들고 관리 하는 단일 문서에 사용자에 게 나타나도록 "완벽 하 게" 문서에 포함 시킬 수 있습니다는 서버 응용 프로그램의 데이터를 나타냅니다.  결과 "복합 문서 OLE 항목 및 문서를 포함 하는 구성"입니다.  
  
 OLE 항목 포함 된 링크 또는 수 있습니다.  포함 된 경우 해당 데이터 복합 문서의 일부로 저장 됩니다.  연결 되어 있으면 해당 데이터는 별도 서버 응용 프로그램에서 만든 파일의 일부로 저장 됩니다 및 해당 파일 링크만 복합 문서에 저장 됩니다.  모든 OLE 항목 편집할 호출 해야 하는 서버 응용 프로그램을 지정 하는 정보가 들어 있습니다.  
  
 `COleClientItem`요청에 응답 하는 서버 응용 프로그램에서 호출 하는 재정의 가능한 함수 몇 가지를 정의 합니다. 이러한 함수는 대개 알림의 역할.  이 서버 응용 프로그램이 컨테이너에서 OLE 항목을 편집할 때 사용자가 변경 내용을 알리기 위해 또는 편집 하는 동안 필요한 정보를 검색할 수 있습니다.  
  
 `COleClientItem`과 함께 사용할 수 있는  [COleDocument](../../mfc/reference/coledocument-class.md),  [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md), 또는  [COleServerDoc](../../mfc/reference/coleserverdoc-class.md) 클래스.  사용할 `COleClientItem`, 클래스에서 파생 하 여 구현 된  [OnChange](../Topic/COleClientItem::OnChange.md) 컨테이너 항목에 변경 내용에 응답 하는 방법을 정의 하는 멤버 함수.  현재 위치에서 활성화를 지원 하려면 재정의  [OnGetItemPosition](../Topic/COleClientItem::OnGetItemPosition.md) 멤버 함수입니다.  이 함수가 OLE 항목을 표시 된 위치에 대 한 정보를 제공합니다.  
  
 컨테이너 인터페이스를 사용 하는 방법에 대 한 자세한 내용은 문서를 참조 하십시오.  [컨테이너: 컨테이너 구현](../../mfc/containers-implementing-a-container.md) 및  [정품](../../mfc/activation-cpp.md).  
  
> [!NOTE]
>  [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] "개체" 항목을 포함 하 고 연결 된 참조 하 고 형식으로 "클래스" 항목을 참조 이 참조 용어 "항목"를 사용 하 여 OLE 엔터티 해당 C\+\+ 개체 및 C\+\+ 클래스에서 OLE 항목을 구분 하기 위해 "형식" 이라는 용어를 구분 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleClientItem`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [MFC 샘플 MFCBIND](../../top/visual-cpp-samples.md)   
 [MFC OCLIENT 샘플](../../top/visual-cpp-samples.md)   
 [CDocItem Class](../../mfc/reference/cdocitem-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)