---
title: "COleDocument Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDocument"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDocument class"
  - "문서, OLE"
  - "OLE containers, client items"
  - "OLE 문서"
  - "OLE 문서, 기본 클래스"
  - "visual editing, OLE document base class"
ms.assetid: dc2ecb99-03e1-44c7-bb69-48056dd1b672
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDocument Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비주얼 편집을 지 원하는 OLE 문서에 대 한 기본 클래스입니다.  
  
## 구문  
  
```  
class COleDocument : public CDocument  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleDocument::COleDocument](../Topic/COleDocument::COleDocument.md)|`COleDocument` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleDocument::AddItem](../Topic/COleDocument::AddItem.md)|문서에서 유지 되는 항목의 목록에 항목을 추가 합니다.|  
|[COleDocument::ApplyPrintDevice](../Topic/COleDocument::ApplyPrintDevice.md)|문서에서 모든 클라이언트 항목에 대 한 대상 인쇄 장치를 설정합니다.|  
|[COleDocument::EnableCompoundFile](../Topic/COleDocument::EnableCompoundFile.md)|문서에서 OLE 구조적 저장소 파일 형식을 사용 하 여 저장 됩니다.|  
|[COleDocument::GetInPlaceActiveItem](../Topic/COleDocument::GetInPlaceActiveItem.md)|현재 위치에서 활성화 된 OLE 항목을 반환 합니다.|  
|[COleDocument::GetNextClientItem](../Topic/COleDocument::GetNextClientItem.md)|반복에 대 한 클라이언트의 다음 항목을 가져옵니다.|  
|[COleDocument::GetNextItem](../Topic/COleDocument::GetNextItem.md)|반복에 대 한 문서는 다음 항목을 가져옵니다.|  
|[COleDocument::GetNextServerItem](../Topic/COleDocument::GetNextServerItem.md)|반복에 대 한 서버에서 다음 항목을 가져옵니다.|  
|[COleDocument::GetPrimarySelectedItem](../Topic/COleDocument::GetPrimarySelectedItem.md)|문서에서 기본 선택된 된 OLE 항목을 반환합니다.|  
|[COleDocument::GetStartPosition](../Topic/COleDocument::GetStartPosition.md)|반복을 시작할 초기 위치를 가져옵니다.|  
|[COleDocument::HasBlankItems](../Topic/COleDocument::HasBlankItems.md)|문서에 빈 항목을 검사 합니다.|  
|[COleDocument::OnShowViews](../Topic/COleDocument::OnShowViews.md)|문서 해지면 보이거나 보이지 않는 호출 됩니다.|  
|[COleDocument::RemoveItem](../Topic/COleDocument::RemoveItem.md)|문서에서 유지 되는 항목의 목록에서 항목을 제거 합니다.|  
|[COleDocument::UpdateModifiedFlag](../Topic/COleDocument::UpdateModifiedFlag.md)|포함 된 OLE 항목을 수정한 경우 수정 된 문서를 표시 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleDocument::OnEditChangeIcon](../Topic/COleDocument::OnEditChangeIcon.md)|아이콘 변경 메뉴 명령에 이벤트를 처리합니다.|  
|[COleDocument::OnEditConvert](../Topic/COleDocument::OnEditConvert.md)|유형이 다른 개체나 연결 개체의 변환을 처리합니다.|  
|[COleDocument::OnEditLinks](../Topic/COleDocument::OnEditLinks.md)|링크 명령 편집 메뉴에서 이벤트를 처리합니다.|  
|[COleDocument::OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md)|첨부 된 문서를 메일 메시지를 보냅니다.|  
|[COleDocument::OnUpdateEditChangeIcon](../Topic/COleDocument::OnUpdateEditChangeIcon.md)|업데이트 명령 UI 편집\/바꾸기 아이콘 메뉴 옵션에 대 한 프레임 워크에서 호출 합니다.|  
|[COleDocument::OnUpdateEditLinksMenu](../Topic/COleDocument::OnUpdateEditLinksMenu.md)|업데이트 명령 UI 편집\/링크 메뉴 옵션에 대 한 프레임 워크에서 호출 합니다.|  
|[COleDocument::OnUpdateObjectVerbMenu](../Topic/COleDocument::OnUpdateObjectVerbMenu.md)|편집 명령 UI를 업데이트 하는 프레임 워크에 의해 호출 \/*ObjectName* 메뉴 옵션 및 동사 하위 메뉴에서 편집 액세스 \/*ObjectName*.|  
|[COleDocument::OnUpdatePasteLinkMenu](../Topic/COleDocument::OnUpdatePasteLinkMenu.md)|업데이트 명령 UI 붙여넣기 메뉴 옵션에 대 한 프레임 워크에서 호출 합니다.|  
|[COleDocument::OnUpdatePasteMenu](../Topic/COleDocument::OnUpdatePasteMenu.md)|업데이트 명령 UI 붙여넣기 메뉴 옵션에 대 한 프레임 워크에서 호출 합니다.|  
  
## 설명  
 `COleDocument`파생 된  **CDocument**, Mfc 라이브러리에서 제공 하는 문서\/뷰 아키텍처를 사용 하 여 OLE 응용 프로그램은 있습니다.  
  
 `COleDocument`문서 컬렉션으로 취급  [CDocItem](../../mfc/reference/cdocitem-class.md) OLE 항목을 처리 하는 개체입니다.  문서는 OLE 항목이 있어야 하기 때문에 모두 컨테이너 및 서버 응용 프로그램은 이러한 아키텍처가 필요 합니다.  [COleServerItem](../../mfc/reference/coleserveritem-class.md) 및  [활성화](../../mfc/reference/coleclientitem-class.md) 클래스에서 파생 된 두 `CDocItem`, 응용 프로그램에서 OLE 항목 간의 상호 작용을 관리 합니다.  
  
 간단한 컨테이너 응용 프로그램을 작성 하는 경우 문서 클래스에서 파생 될 `COleDocument`.  해당 문서에 포함 된 포함 된 항목에 대 한 링크를 지 원하는 컨테이너 응용 프로그램을 작성 하는 경우 문서 클래스에서 파생 될  [COleLinkingDoc](../../mfc/reference/colelinkingdoc-class.md).  조합 또는 응용 프로그램 컨테이너\/서버 서버를 작성 하는 경우 문서 클래스에서 파생 될  [COleServerDoc](../../mfc/reference/coleserverdoc-class.md).  `COleLinkingDoc`및 `COleServerDoc` 에서 파생 된 `COleDocument`, 이러한 클래스에서 사용할 수 있는 모든 서비스 상속 `COleDocument` 및  **CDocument**.  
  
 사용 `COleDocument`, 클래스 파생 및 추가 기능 응용 프로그램의 비 OLE 데이터는 물론 포함 되거나 연결 된 항목을 관리할 수 있습니다.  사용자 정의 하는 경우 `CDocItem`\-응용 프로그램의 기본 데이터를 저장 하는 클래스를 파생 기본 구현에 의해 정의 사용할 수 있습니다 `COleDocument` OLE 및 비 OLE 데이터를 저장할 수.  OLE 항목을 별도로 비 OLE 데이터 저장에 대 한 자신의 데이터 구조를 디자인할 수도 있습니다.  자세한 내용은  [컨테이너: 복합 파일](../../mfc/containers-compound-files.md).  
  
 **CDocument** \(MAPI\) 전자 메일 서비스를 사용할 수 없는 경우 메일을 통해 문서를 보내기를 지원 합니다.  `COleDocument`업데이트 된  [OnFileSendMail](../Topic/COleDocument::OnFileSendMail.md) 복합 문서를 올바르게 처리할 수 있습니다.  자세한 내용은 문서를 참조 하십시오.  [MAPI](../../mfc/mapi.md) 및  [MFC의 MAPI 지원](../../mfc/mapi-support-in-mfc.md).  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 `COleDocument`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [MFC 컨테이너 예제](../../top/visual-cpp-samples.md)   
 [MFCBIND MFC 샘플](../../top/visual-cpp-samples.md)   
 [CDocument Class](../../mfc/reference/cdocument-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)