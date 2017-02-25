---
title: "COleServerItem Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleServerItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleServerItem class"
  - "OLE 서버 응용 프로그램, managing server documents"
  - "OLE 서버 응용 프로그램, server interfaces"
  - "OLE server documents"
  - "서버, OLE"
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleServerItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE 항목을 서버 인터페이스를 제공합니다.  
  
## 구문  
  
```  
class COleServerItem : public CDocItem  
```  
  
## 멤버  
  
### Protected 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleServerItem::COleServerItem](../Topic/COleServerItem::COleServerItem.md)|`COleServerItem` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleServerItem::AddOtherClipboardData](../Topic/COleServerItem::AddOtherClipboardData.md)|변환 및 프레젠테이션 형식으로 저장 된 `COleDataSource` 개체입니다.|  
|[COleServerItem::CopyToClipboard](../Topic/COleServerItem::CopyToClipboard.md)|항목을 클립보드에 복사합니다.|  
|[COleServerItem::DoDragDrop](../Topic/COleServerItem::DoDragDrop.md)|끌어서 놓기 작업을 수행합니다.|  
|[COleServerItem::GetClipboardData](../Topic/COleServerItem::GetClipboardData.md)|\(끌어서 놓기 또는 클립보드\) 데이터 전송에 사용할 데이터 소스를 가져옵니다.|  
|[COleServerItem::GetDocument](../Topic/COleServerItem::GetDocument.md)|항목을 포함 하는 서버 문서를 반환 합니다.|  
|[COleServerItem::GetEmbedSourceData](../Topic/COleServerItem::GetEmbedSourceData.md)|가져옵니다의  **CF\_EMBEDSOURCE** OLE 항목 데이터입니다.|  
|[COleServerItem::GetItemName](../Topic/COleServerItem::GetItemName.md)|항목의 이름을 반환합니다.  연결 된 항목을 사용 합니다.|  
|[COleServerItem::GetLinkSourceData](../Topic/COleServerItem::GetLinkSourceData.md)|가져옵니다의 `CF_LINKSOURCE` OLE 항목 데이터입니다.|  
|[COleServerItem::GetObjectDescriptorData](../Topic/COleServerItem::GetObjectDescriptorData.md)|가져옵니다의  **CF\_OBJECTDESCRIPTOR** OLE 항목 데이터입니다.|  
|[COleServerItem::IsConnected](../Topic/COleServerItem::IsConnected.md)|항목은 현재 컨테이너에 현재 연결 되어 있는지 여부를 나타냅니다.|  
|[COleServerItem::IsLinkedItem](../Topic/COleServerItem::IsLinkedItem.md)|항목이 링크 된 OLE 항목을 나타내는지 여부를 나타냅니다.|  
|[COleServerItem::NotifyChanged](../Topic/COleServerItem::NotifyChanged.md)|모든 컨테이너와 자동 연결 업데이트를 업데이트합니다.|  
|[COleServerItem::OnDoVerb](../Topic/COleServerItem::OnDoVerb.md)|동사를 실행 하기 위해 호출 됩니다.|  
|[COleServerItem::OnDraw](../Topic/COleServerItem::OnDraw.md)|컨테이너 항목을 그릴 때 호출 됩니다. 구현이 필요 합니다.|  
|[COleServerItem::OnDrawEx](../Topic/COleServerItem::OnDrawEx.md)|특수 항목 그리기를 호출 합니다.|  
|[COleServerItem::OnGetClipboardData](../Topic/COleServerItem::OnGetClipboardData.md)|클립보드에 복사 되는 데이터를 가져올 수 있는 프레임 워크에서 호출 합니다.|  
|[COleServerItem::OnGetExtent](../Topic/COleServerItem::OnGetExtent.md)|OLE 항목의 크기를 검색 하는 프레임 워크에서 호출 됩니다.|  
|[COleServerItem::OnInitFromData](../Topic/COleServerItem::OnInitFromData.md)|지정 된 데이터 전송 개체의 내용을 사용 하 여 OLE 항목을 초기화 하는 프레임 워크에서 호출 됩니다.|  
|[COleServerItem::OnQueryUpdateItems](../Topic/COleServerItem::OnQueryUpdateItems.md)|연결 된 모든 항목을 업데이트 해야 하는지 여부를 확인 하기 위해 호출 됩니다.|  
|[COleServerItem::OnRenderData](../Topic/COleServerItem::OnRenderData.md)|지연된 렌더링의 일부로 데이터를 검색합니다.|  
|[COleServerItem::OnRenderFileData](../Topic/COleServerItem::OnRenderFileData.md)|검색 데이터에는 `CFile` 지연된 렌더링의 일부로 개체입니다.|  
|[COleServerItem::OnRenderGlobalData](../Topic/COleServerItem::OnRenderGlobalData.md)|검색 데이터에는 `HGLOBAL` 지연된 렌더링의 일부로.|  
|[COleServerItem::OnSetColorScheme](../Topic/COleServerItem::OnSetColorScheme.md)|항목의 색 구성표를 설정 하기 위해 호출 됩니다.|  
|[COleServerItem::OnSetData](../Topic/COleServerItem::OnSetData.md)|항목의 데이터를 설정 하기 위해 호출 됩니다.|  
|[COleServerItem::OnSetExtent](../Topic/COleServerItem::OnSetExtent.md)|OLE 항목의 크기를 설정 하는 프레임 워크에서 호출 됩니다.|  
|[COleServerItem::OnUpdate](../Topic/COleServerItem::OnUpdate.md)|호출할 때 문서 항목 중 일부 포함 변경 됩니다.|  
|[COleServerItem::OnUpdateItems](../Topic/COleServerItem::OnUpdateItems.md)|프레젠테이션 캐시 서버 문서의 모든 항목을 업데이트 하기 위해 호출 됩니다.|  
|[COleServerItem::SetItemName](../Topic/COleServerItem::SetItemName.md)|항목의 이름을 설정합니다.  연결 된 항목을 사용 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleServerItem::GetDataSource](../Topic/COleServerItem::GetDataSource.md)|변환 형식을 저장 하는 데 사용 되는 개체를 가져옵니다.|  
|[COleServerItem::OnHide](../Topic/COleServerItem::OnHide.md)|OLE 항목을 숨기기 위해 프레임 워크에서 호출 됩니다.|  
|[COleServerItem::OnOpen](../Topic/COleServerItem::OnOpen.md)|최상위 창에서 OLE 항목을 표시 하는 프레임 워크에서 호출 합니다.|  
|[COleServerItem::OnShow](../Topic/COleServerItem::OnShow.md)|컨테이너 항목을 표시 하도록 요청 하면 호출 됩니다.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[COleServerItem::m\_sizeExtent](../Topic/COleServerItem::m_sizeExtent.md)|OLE 항목의 표시 기능에 대해 알립니다.|  
  
## 설명  
 연결 된 항목 일부 또는 모든 서버 문서를 나타낼 수 있습니다.  포함 된 항목은 항상 전체 서버 문서를 나타냅니다.  
  
 `COleServerItem` 클래스 정의 OLE 시스템 동적 연결 라이브러리 \(Dll\)를 호출 하는 재정의 가능한 멤버 함수 몇 가지 일반적으로 컨테이너 응용 프로그램에서 요청에 응답에서 합니다.  이러한 멤버 함수를 간접적으로 여러 가지 방법으로 항목 처럼 표시, 동사를 실행 하거나 다양 한 형식의 데이터를 검색 하 여 조작 하 여 컨테이너 응용 프로그램을 허용 합니다.  
  
 사용 `COleServerItem`, 클래스에서 파생 하 여 구현 된  [OnDraw](../Topic/COleServerItem::OnDraw.md) 및  [Serialize](../Topic/CObject::Serialize.md) 멤버 함수.  `OnDraw` 함수는 복합 문서 컨테이너 응용 프로그램을 열 때 표시할 수 있는 항목의 메타 파일 표시를 제공 합니다.  `Serialize` 의 `CObject` 포함된 항목 컨테이너 및 서버 응용 프로그램 간에 전송할 수 있도록 항목의 기본 표현을 제공 합니다.  [합니다.](../Topic/COleServerItem::OnGetExtent.md) 컨테이너, 컨테이너는 항목의 크기를 사용 하면 항목의 원래 크기를 제공 합니다.  
  
 서버 및 관련된 항목에 대 한 자세한 내용은  [서버: 서버 구현](../../mfc/servers-implementing-a-server.md) 및 "컨테이너\/서버 응용 만들기" 문서에서  [컨테이너: 고급 기능](../../mfc/containers-advanced-features.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleServerItem`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [HIERSVR MFC 샘플](../../top/visual-cpp-samples.md)   
 [CDocItem Class](../../mfc/reference/cdocitem-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [COleServerDoc Class](../../mfc/reference/coleserverdoc-class.md)   
 [COleTemplateServer Class](../../mfc/reference/coletemplateserver-class.md)