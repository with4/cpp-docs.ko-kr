---
title: "CRichEditView Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRichEditView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditView class"
  - "document/view architecture, rich edit 컨트롤"
  - "OLE containers, rich edit"
  - "rich edit 컨트롤, OLE container"
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CRichEditView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

와  [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) 및  [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), MFC의 문서 뷰 아키텍처의 컨텍스트 내에서 풍부한 편집 컨트롤의 기능을 제공 합니다.  
  
## 구문  
  
```  
  
class CRichEditView : public CCtrlView  
  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CRichEditView::CRichEditView](../Topic/CRichEditView::CRichEditView.md)|`CRichEditView` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRichEditView::AdjustDialogPosition](../Topic/CRichEditView::AdjustDialogPosition.md)|현재 선택이 모호 하지 않도록 대화 상자를 이동 합니다.|  
|[CRichEditView::CanPaste](../Topic/CRichEditView::CanPaste.md)|클립보드 데이터 서식 있는 편집 보기에 붙여넣을 수 있는지 여부를 알려 줍니다.|  
|[CRichEditView::DoPaste](../Topic/CRichEditView::DoPaste.md)|이 풍부한 편집 보기에 OLE 항목을 붙여넣습니다.|  
|[CRichEditView::FindText](../Topic/CRichEditView::FindText.md)|대기 커서가 호출에서 지정한 텍스트를 찾습니다.|  
|[CRichEditView::FindTextSimple](../Topic/CRichEditView::FindTextSimple.md)|지정한 텍스트를 찾습니다.|  
|[CRichEditView::GetCharFormatSelection](../Topic/CRichEditView::GetCharFormatSelection.md)|문자 서식을 현재 선택 영역에 대 한 특성을 검색 합니다.|  
|[CRichEditView::GetDocument](../Topic/CRichEditView::GetDocument.md)|관련 항목에 대 한 포인터를 검색 합니다.  [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md).|  
|[CRichEditView::GetInPlaceActiveItem](../Topic/CRichEditView::GetInPlaceActiveItem.md)|Rich edit 뷰의 현재 위치에서 활성화 된 OLE 항목을 검색 합니다.|  
|[CRichEditView::GetMargins](../Topic/CRichEditView::GetMargins.md)|여백이 rich edit 뷰를 검색합니다.|  
|[CRichEditView::GetPageRect](../Topic/CRichEditView::GetPageRect.md)|이 rich edit 뷰의 페이지 사각형을 검색합니다.|  
|[CRichEditView::GetPaperSize](../Topic/CRichEditView::GetPaperSize.md)|이 풍부한 편집 보기에 대 한 용지 크기를 검색합니다.|  
|[CRichEditView::GetParaFormatSelection](../Topic/CRichEditView::GetParaFormatSelection.md)|단락 서식을 현재 선택 영역에 대 한 특성을 검색 합니다.|  
|[CRichEditView::GetPrintRect](../Topic/CRichEditView::GetPrintRect.md)|이 rich edit 뷰의 인쇄 사각형을 검색합니다.|  
|[CRichEditView::GetPrintWidth](../Topic/CRichEditView::GetPrintWidth.md)|인쇄 폭이 rich edit 뷰를 검색합니다.|  
|[CRichEditView::GetRichEditCtrl](../Topic/CRichEditView::GetRichEditCtrl.md)|Rich edit 컨트롤을 검색합니다.|  
|[CRichEditView::GetSelectedItem](../Topic/CRichEditView::GetSelectedItem.md)|서식 있는 편집 보기에서 선택한 항목을 검색합니다.|  
|[CRichEditView::GetTextLength](../Topic/CRichEditView::GetTextLength.md)|서식 있는 편집 보기에서 텍스트를 검색합니다.|  
|[CRichEditView::GetTextLengthEx](../Topic/CRichEditView::GetTextLengthEx.md)|Rich edit 뷰의 바이트 또는 문자 수를 검색합니다.  길이 결정 하는 방법에 대 한 확장 된 플래그 목록입니다.|  
|[CRichEditView::InsertFileAsObject](../Topic/CRichEditView::InsertFileAsObject.md)|OLE 항목으로 파일을 삽입합니다.|  
|[CRichEditView::InsertItem](../Topic/CRichEditView::InsertItem.md)|OLE 항목으로 새 항목을 삽입합니다.|  
|[CRichEditView::IsRichEditFormat](../Topic/CRichEditView::IsRichEditFormat.md)|클립보드 데이터를 서식 있는 텍스트나 텍스트 형식에 포함 되어 있는지 여부를 알려 줍니다.|  
|[CRichEditView::OnCharEffect](../Topic/CRichEditView::OnCharEffect.md)|문자 서식을 현재 선택 영역을 표시 하거나 숨깁니다.|  
|[CRichEditView::OnParaAlign](../Topic/CRichEditView::OnParaAlign.md)|단락 맞춤을 변경합니다.|  
|[CRichEditView::OnUpdateCharEffect](../Topic/CRichEditView::OnUpdateCharEffect.md)|명령 문자 공용 멤버 함수에 대 한 UI를 업데이트합니다.|  
|[CRichEditView::OnUpdateParaAlign](../Topic/CRichEditView::OnUpdateParaAlign.md)|단락 공용 멤버 함수에 대 한 명령 UI를 업데이트합니다.|  
|[CRichEditView::PrintInsideRect](../Topic/CRichEditView::PrintInsideRect.md)|지정 된 사각형에 지정 된 텍스트에 서식을 지정합니다.|  
|[CRichEditView::PrintPage](../Topic/CRichEditView::PrintPage.md)|지정 된 페이지에서 지정 된 텍스트에 서식을 지정합니다.|  
|[CRichEditView::SetCharFormat](../Topic/CRichEditView::SetCharFormat.md)|문자 서식을 현재 선택 영역에 대 한 특성을 설정 합니다.|  
|[CRichEditView::SetMargins](../Topic/CRichEditView::SetMargins.md)|이 풍부한 여백을 설정 보기를 편집합니다.|  
|[CRichEditView::SetPaperSize](../Topic/CRichEditView::SetPaperSize.md)|이 풍부한 편집 보기에 대 한 용지 크기를 설정합니다.|  
|[CRichEditView::SetParaFormat](../Topic/CRichEditView::SetParaFormat.md)|단락 서식을 현재 선택 영역에 대 한 특성을 설정 합니다.|  
|[CRichEditView::TextNotFound](../Topic/CRichEditView::TextNotFound.md)|컨트롤의 내부 검색 상태를 다시 설정합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRichEditView::GetClipboardData](../Topic/CRichEditView::GetClipboardData.md)|이 rich edit 뷰 범위에 클립보드 객체를 검색합니다.|  
|[CRichEditView::GetContextMenu](../Topic/CRichEditView::GetContextMenu.md)|상황에 맞는 메뉴에서 오른쪽 마우스 단추를 사용 하는 검색 합니다.|  
|[CRichEditView::IsSelected](../Topic/CRichEditView::IsSelected.md)|지정 된 OLE 항목 선택 하는 경우를 나타냅니다.|  
|[CRichEditView::OnFindNext](../Topic/CRichEditView::OnFindNext.md)|부분 문자열의 다음 항목을 찾습니다.|  
|[CRichEditView::OnInitialUpdate](../Topic/CRichEditView::OnInitialUpdate.md)|새로 고침 처음 보기는 문서에 연결 합니다.|  
|[CRichEditView::OnPasteNativeObject](../Topic/CRichEditView::OnPasteNativeObject.md)|OLE 항목에서 원시 데이터를 검색합니다.|  
|[CRichEditView::OnPrinterChanged](../Topic/CRichEditView::OnPrinterChanged.md)|인쇄 특성에 지정 된 장치를 설정합니다.|  
|[CRichEditView::OnReplaceAll](../Topic/CRichEditView::OnReplaceAll.md)|지정 된 문자열의 모든 항목을 새 문자열로 바꿉니다.|  
|[CRichEditView::OnReplaceSel](../Topic/CRichEditView::OnReplaceSel.md)|현재 선택 영역을 바꿉니다.|  
|[CRichEditView::OnTextNotFound](../Topic/CRichEditView::OnTextNotFound.md)|요청 된 텍스트를 찾을 수 없는 사용자가 알림을 처리 합니다.|  
|[CRichEditView::QueryAcceptData](../Topic/CRichEditView::QueryAcceptData.md)|에 대 한 데이터를 볼 수 있는 쿼리는 `IDataObject`.|  
|[CRichEditView::WrapChanged](../Topic/CRichEditView::WrapChanged.md)|이 서식 있는 값에 따라 보기, 편집에 대 한 대상 출력 장치 조정 `m_nWordWrap`.|  
  
### 공용 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CRichEditView::m\_nBulletIndent](../Topic/CRichEditView::m_nBulletIndent.md)|글머리 기호 목록 들여쓰기를 나타냅니다.|  
|[CRichEditView::m\_nWordWrap](../Topic/CRichEditView::m_nWordWrap.md)|단어 줄 바꿈 제약 조건을 나타냅니다.|  
  
## 설명  
 "Rich edit 컨트롤" 사용자를 입력 하 고 텍스트를 편집 하는 창입니다.  텍스트 문자 및 단락 서식을 지정할 수 있으며 포함 된 OLE 개체를 포함할 수 있습니다.  Rich edit 컨트롤 텍스트 서식에 대 한 프로그래밍 인터페이스를 제공 합니다.  그러나 응용 프로그램이 모든 사용자에 게 서식 지정 작업을 사용할 수 있도록 하는 데 필요한 사용자 인터페이스 구성 구현 해야 합니다.  
  
 `CRichEditView`텍스트와 텍스트의 서식 특성을 유지합니다.  `CRichEditDoc`보기에서 사용 하는 OLE 클라이언트 항목 목록을 유지 합니다.  `CRichEditCntrItem`OLE 클라이언트 항목 컨테이너 쪽 액세스를 제공합니다.  
  
 이 Windows 공용 컨트롤 \(즉는  [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) 및 관련 클래스\) Windows NT 및 Windows 95\/98 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.  
  
 MFC 응용 프로그램에 rich edit 뷰를 사용 하는 방법에 대 한 예제를 참조 하십시오의  [워드 패드](../../top/visual-cpp-samples.md) 샘플 응용 프로그램입니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CView](../../mfc/reference/cview-class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CRichEditView`  
  
## 요구 사항  
 **헤더:**  afxrich.h  
  
## 참고 항목  
 [MFC 샘플 워드 패드](../../top/visual-cpp-samples.md)   
 [CCtrlView Class](../../mfc/reference/cctrlview-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc Class](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditCntrItem Class](../../mfc/reference/cricheditcntritem-class.md)