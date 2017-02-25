---
title: "CRichEditCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRichEditCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditCtrl class"
  - "CRichEditCtrl class, 공용 컨트롤"
  - "formatted text [C++]"
ms.assetid: 2be52788-822c-4c27-aafd-2471231e74eb
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CRichEditCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Rich edit 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CRichEditCtrl : public CWnd  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CRichEditCtrl::CRichEditCtrl](../Topic/CRichEditCtrl::CRichEditCtrl.md)|`CRichEditCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CRichEditCtrl::CanPaste](../Topic/CRichEditCtrl::CanPaste.md)|클립보드의 내용을이 rich edit 컨트롤에 붙여넣을 수 있을 경우 결정 합니다.|  
|[CRichEditCtrl::CanRedo](../Topic/CRichEditCtrl::CanRedo.md)|컨트롤의 다시 실행 큐에서 있는지 여부를 결정 합니다.|  
|[CRichEditCtrl::CanUndo](../Topic/CRichEditCtrl::CanUndo.md)|편집 작업을 취소할 수 경우 결정 합니다.|  
|[CRichEditCtrl::CharFromPos](../Topic/CRichEditCtrl::CharFromPos.md)|지정 된 위치로 편집 컨트롤의 클라이언트 영역에 가장 가까운 문자에 대 한 정보를 검색합니다.|  
|[CRichEditCtrl::Clear](../Topic/CRichEditCtrl::Clear.md)|현재 선택 항목을 지웁니다.|  
|[CRichEditCtrl::Copy](../Topic/CRichEditCtrl::Copy.md)|현재 선택 영역을 클립보드에 복사합니다.|  
|[CRichEditCtrl::Create](../Topic/CRichEditCtrl::Create.md)|Windows rich edit 컨트롤이 만들어지고이 연결 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::CreateEx](../Topic/CRichEditCtrl::CreateEx.md)|Windows rich edit 컨트롤에 지정 된 확장 창 스타일 만들어지고이 연결 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::Cut](../Topic/CRichEditCtrl::Cut.md)|현재 선택 영역을 클립보드로 잘라냅니다.|  
|[CRichEditCtrl::DisplayBand](../Topic/CRichEditCtrl::DisplayBand.md)|이 내용의 일부를 표시 합니다. `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::EmptyUndoBuffer](../Topic/CRichEditCtrl::EmptyUndoBuffer.md)|\(취소\)이 실행 취소 플래그를 다시 설정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::FindText](../Topic/CRichEditCtrl::FindText.md)|이 텍스트를 찾는 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::FindWordBreak](../Topic/CRichEditCtrl::FindWordBreak.md)|다음 단어 구분 앞 이나 뒤에 지정 된 문자 위치를 찾거나 해당 위치에 있는 문자에 대 한 정보를 검색 합니다.|  
|[CRichEditCtrl::FormatRange](../Topic/CRichEditCtrl::FormatRange.md)|대상 출력 장치에 대 한 텍스트 서식을 지정합니다.|  
|[CRichEditCtrl::GetCharPos](../Topic/CRichEditCtrl::GetCharPos.md)|이 내의 지정 된 문자의 위치를 결정 합니다. `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetDefaultCharFormat](../Topic/CRichEditCtrl::GetDefaultCharFormat.md)|이 속성에서 현재 기본 문자 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetEventMask](../Topic/CRichEditCtrl::GetEventMask.md)|이벤트 마스크에 대 한이 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetFirstVisibleLine](../Topic/CRichEditCtrl::GetFirstVisibleLine.md)|확인 표시 된 맨 위에 있는 줄이 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetIRichEditOle](../Topic/CRichEditCtrl::GetIRichEditOle.md)|검색에 대 한 포인터는 `IRichEditOle` 이 서식 있는 편집 컨트롤에 대 한 인터페이스.|  
|[CRichEditCtrl::GetLimitText](../Topic/CRichEditCtrl::GetLimitText.md)|사용자 입력으로 텍스트의 양에 제한을 가져옵니다 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetLine](../Topic/CRichEditCtrl::GetLine.md)|텍스트 줄에서 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetLineCount](../Topic/CRichEditCtrl::GetLineCount.md)|이 줄의 수를 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetModify](../Topic/CRichEditCtrl::GetModify.md)|결정 하는 경우이 내용의 `CRichEditCtrl` 개체를 마지막으로 저장 한 이후 변경 되었습니다.|  
|[CRichEditCtrl::GetOptions](../Topic/CRichEditCtrl::GetOptions.md)|Rich edit 컨트롤 옵션을 검색합니다.|  
|[CRichEditCtrl::GetParaFormat](../Topic/CRichEditCtrl::GetParaFormat.md)|단락 서식 특성의 현재 선택 영역에서이 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetPunctuation](../Topic/CRichEditCtrl::GetPunctuation.md)|Rich edit 컨트롤에 대 한 현재 문장 부호 문자를 검색합니다.  이 메시지는 운영 체제의 한국어 버전에만 사용할 수 있습니다.|  
|[CRichEditCtrl::GetRect](../Topic/CRichEditCtrl::GetRect.md)|서식 지정 영역에 대 한이 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetRedoName](../Topic/CRichEditCtrl::GetRedoName.md)|컨트롤의 모든 큐를 다시 실행 하는 경우는 다음 작업 유형을 검색 합니다.|  
|[CRichEditCtrl::GetSel](../Topic/CRichEditCtrl::GetSel.md)|시작 및 끝 위치를 현재 선택 영역에서이 가져옵니다 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetSelectionCharFormat](../Topic/CRichEditCtrl::GetSelectionCharFormat.md)|문자 서식을 현재 선택 영역에이 특성이 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetSelectionType](../Topic/CRichEditCtrl::GetSelectionType.md)|검색 내용 현재 선택 영역에이 형식의 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetSelText](../Topic/CRichEditCtrl::GetSelText.md)|이 작업은 현재 선택 영역의 텍스트를 가져옵니다 `CRichEditCtrl` 개체|  
|[CRichEditCtrl::GetTextLength](../Topic/CRichEditCtrl::GetTextLength.md)|이 문자는 텍스트의 길이 검색 `CRichEditCtrl` 개체입니다.  종료 null 문자를 포함 하지 않습니다.|  
|[CRichEditCtrl::GetTextLengthEx](../Topic/CRichEditCtrl::GetTextLengthEx.md)|Rich edit 뷰의 바이트 또는 문자 수를 검색합니다.  Rich edit 컨트롤의 텍스트 길이 결정 하는 방법을 지정 하는 플래그의 사용|  
|[CRichEditCtrl::GetTextMode](../Topic/CRichEditCtrl::GetTextMode.md)|현재 텍스트 모드 및 실행 취소 수준 rich edit 컨트롤을 검색합니다.|  
|[CRichEditCtrl::GetTextRange](../Topic/CRichEditCtrl::GetTextRange.md)|지정한 텍스트 범위를 검색합니다.|  
|[CRichEditCtrl::GetUndoName](../Topic/CRichEditCtrl::GetUndoName.md)|유형을 다음 실행 취소 작업을 모든 경우를 검색 합니다.|  
|[CRichEditCtrl::GetWordWrapMode](../Topic/CRichEditCtrl::GetWordWrapMode.md)|현재 줄 바꿈 및 단어 바꿈 옵션 rich edit 컨트롤을 검색합니다.  이 메시지는 운영 체제의 한국어 버전에만 사용할 수 있습니다.|  
|[CRichEditCtrl::HideSelection](../Topic/CRichEditCtrl::HideSelection.md)|표시 하거나 현재 선택 영역을 숨깁니다.|  
|[CRichEditCtrl::LimitText](../Topic/CRichEditCtrl::LimitText.md)|텍스트를 입력할 수에 제한 된 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::LineFromChar](../Topic/CRichEditCtrl::LineFromChar.md)|지정 된 문자가 있는 줄을 결정 합니다.|  
|[CRichEditCtrl::LineIndex](../Topic/CRichEditCtrl::LineIndex.md)|이 해당된 줄의 문자 인덱스 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::LineLength](../Topic/CRichEditCtrl::LineLength.md)|이 지정 된 줄의 길이 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::LineScroll](../Topic/CRichEditCtrl::LineScroll.md)|이 텍스트가 스크롤되는 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::Paste](../Topic/CRichEditCtrl::Paste.md)|클립보드의 내용을이 rich edit 컨트롤에 삽입합니다.|  
|[CRichEditCtrl::PasteSpecial](../Topic/CRichEditCtrl::PasteSpecial.md)|이 rich edit 컨트롤에 지정 된 데이터 형식이 클립보드의 내용을 삽입합니다.|  
|[CRichEditCtrl::PosFromChar](../Topic/CRichEditCtrl::PosFromChar.md)|클라이언트 영역 좌표는 편집 컨트롤에 지정 된 문자를 검색합니다.|  
|[CRichEditCtrl::Redo](../Topic/CRichEditCtrl::Redo.md)|컨트롤의 다시 실행 큐에서 다음 작업을 다시 실행합니다.|  
|[CRichEditCtrl::ReplaceSel](../Topic/CRichEditCtrl::ReplaceSel.md)|현재 선택 영역에서이 대체 `CRichEditCtrl` 개체와 지정 된 텍스트입니다.|  
|[CRichEditCtrl::RequestResize](../Topic/CRichEditCtrl::RequestResize.md)|이렇게 하면 `CRichEditCtrl` 개체 크기 조정 알림을 요청을 보낼 수 있습니다.|  
|[CRichEditCtrl::SetAutoURLDetect](../Topic/CRichEditCtrl::SetAutoURLDetect.md)|자동 URL 검색 rich edit 컨트롤에서 활성화 되어 있는지를 나타냅니다.|  
|[CRichEditCtrl::SetBackgroundColor](../Topic/CRichEditCtrl::SetBackgroundColor.md)|배경색 설정 하에이 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetDefaultCharFormat](../Topic/CRichEditCtrl::SetDefaultCharFormat.md)|이 속성에서 현재 기본 문자 설정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetEventMask](../Topic/CRichEditCtrl::SetEventMask.md)|설정 이벤트 마스크에 대 한 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetModify](../Topic/CRichEditCtrl::SetModify.md)|설정 또는 수정 플래그를 지웁니다 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetOLECallback](../Topic/CRichEditCtrl::SetOLECallback.md)|집합의 `IRichEditOleCallback` 이 rich edit 컨트롤에 대 한 COM 개체입니다.|  
|[CRichEditCtrl::SetOptions](../Topic/CRichEditCtrl::SetOptions.md)|이 옵션을 설정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetParaFormat](../Topic/CRichEditCtrl::SetParaFormat.md)|단락 서식을 현재 선택 영역에이 특성을 설정 합니다. `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetPunctuation](../Topic/CRichEditCtrl::SetPunctuation.md)|Rich edit 컨트롤에 대 한 문장 부호 문자를 설정합니다.  이 메시지는 운영 체제의 한국어 버전에만 사용할 수 있습니다.|  
|[CRichEditCtrl::SetReadOnly](../Topic/CRichEditCtrl::SetReadOnly.md)|이 읽기 전용 옵션 설정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetRect](../Topic/CRichEditCtrl::SetRect.md)|서식 지정 영역을 설정 하는 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetSel](../Topic/CRichEditCtrl::SetSel.md)|선택 영역에서이 설정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetSelectionCharFormat](../Topic/CRichEditCtrl::SetSelectionCharFormat.md)|문자 서식을 현재 선택 영역에이 특성을 설정 합니다. `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetTargetDevice](../Topic/CRichEditCtrl::SetTargetDevice.md)|대상 출력 장치를 설정 하는 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetTextMode](../Topic/CRichEditCtrl::SetTextMode.md)|Rich edit 컨트롤의 텍스트 모드 또는 실행 취소 수준으로 설정합니다.  컨트롤에 텍스트가 포함 되어 있으면 메시지에 오류가 발생 합니다.|  
|[CRichEditCtrl::SetUndoLimit](../Topic/CRichEditCtrl::SetUndoLimit.md)|실행 취소 대기열에 저장 된 수 있는 작업의 최대 수를 설정 합니다.|  
|[CRichEditCtrl::SetWordCharFormat](../Topic/CRichEditCtrl::SetWordCharFormat.md)|문자 서식을 현재 word에서이 특성을 설정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetWordWrapMode](../Topic/CRichEditCtrl::SetWordWrapMode.md)|자동 줄 바꿈 및 단어 분리에 대 한 풍부한 옵션 설정 제어를 편집합니다.  이 메시지는 운영 체제의 한국어 버전에만 사용할 수 있습니다.|  
|[CRichEditCtrl::StopGroupTyping](../Topic/CRichEditCtrl::StopGroupTyping.md)|수집에서 현재 실행 취소 작업으로 작업을 입력 하 고 추가 제어를 중지 합니다.  컨트롤 다음 입력 작업을 원하는 경우 새 동작에 따라 실행 취소 대기열에 저장 됩니다.|  
|[CRichEditCtrl::StreamIn](../Topic/CRichEditCtrl::StreamIn.md)|입력된 스트림에서에이 텍스트를 삽입 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::StreamOut](../Topic/CRichEditCtrl::StreamOut.md)|저장 된 텍스트에서이 `CRichEditCtrl` 개체를 출력 스트림으로.|  
|[CRichEditCtrl::Undo](../Topic/CRichEditCtrl::Undo.md)|마지막 편집 작업을 취소합니다.|  
  
## 설명  
 "Rich edit 컨트롤" 사용자를 입력 하 고 텍스트를 편집 하는 창입니다.  텍스트 문자 및 단락 서식을 지정할 수 있으며 포함 된 OLE 개체를 포함할 수 있습니다.  Rich edit 컨트롤 텍스트 서식에 대 한 프로그래밍 인터페이스를 제공 합니다.  그러나 응용 프로그램이 모든 사용자에 게 서식 지정 작업을 사용할 수 있도록 하는 데 필요한 사용자 인터페이스 구성 구현 해야 합니다.  
  
 이 Windows 공용 컨트롤 \(즉의 `CRichEditCtrl` 클래스\) Windows NT 및 Windows 95\/98 버전 3.51에서 실행 되는 프로그램에만 사용할 수 있습니다.  `CRichEditCtrl` 클래스 버전 2.0 및 3.0의 지원의 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] rich edit 컨트롤입니다.  
  
> [!CAUTION]
>  Rich edit 컨트롤을 대화 상자에 사용 중인 경우 \(SDI, MDI 응용 프로그램 인지 여부에 관계 없이 또는 대화 상자 기반\)를 호출 해야  [AfxInitRichEdit](../Topic/AfxInitRichEdit.md) 대화 하기 전에 일단.  프로그램에서이 함수를 호출 하는 일반적인 위치입니다 `InitInstance` 멤버 함수입니다.  처음만 대화 상자를 표시할 때마다 호출할 필요가 없습니다.  호출할 필요가 `AfxInitRichEdit` 작업 하는 경우 `CRichEditView`.  
  
 사용에 대 한 자세한 내용은 `CRichEditCtrl`을 참조 하십시오.  
  
-   [컨트롤](../../mfc/controls-mfc.md)  
  
-   [CRichEditCtrl 사용](../../mfc/using-cricheditctrl.md)  
  
-   기술 자료 문서 Q259949: INFO: Setcaretpos\(\)는 적합 하지 않은 CEdit 또는 CRichEditCtrl 컨트롤  
  
 MFC 응용 프로그램에 rich edit 컨트롤을 사용 하는 방법에 대 한 예제를 참조 하십시오의  [워드 패드](../../top/visual-cpp-samples.md) 샘플 응용 프로그램입니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CRichEditCtrl`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [MFC 샘플 워드 패드](../../top/visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CRichEditView Class](../../mfc/reference/cricheditview-class.md)