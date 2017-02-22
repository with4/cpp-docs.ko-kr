---
title: "CHtmlEditCtrlBase Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHtmlEditCtrlBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditCtrlBase class"
ms.assetid: e0cc74b4-8320-4570-b673-16c03d2ae266
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CHtmlEditCtrlBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

HTML 편집 구성 요소를 나타냅니다.  
  
## 구문  
  
```  
  
template < class   
T  
 > class CHtmlEditCtrlBase  
  
```  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CHtmlEditCtrlBase::AddToGlyphTable](../Topic/CHtmlEditCtrlBase::AddToGlyphTable.md)|디자인 모드에서 특정 태그에 대해 표시할 이미지를 지정 하는 문자 모양 테이블에 항목을 추가 합니다.|  
|[CHtmlEditCtrlBase::Bold](../Topic/CHtmlEditCtrlBase::Bold.md)|선택한 텍스트의 굵게 상태를 설정\/해제합니다.|  
|[CHtmlEditCtrlBase::Button](../Topic/CHtmlEditCtrlBase::Button.md)|단추 컨트롤의 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::CheckBox](../Topic/CHtmlEditCtrlBase::CheckBox.md)|확인란 컨트롤의 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::ClearSelection](../Topic/CHtmlEditCtrlBase::ClearSelection.md)|현재 선택 항목을 지웁니다.|  
|[CHtmlEditCtrlBase::Copy](../Topic/CHtmlEditCtrlBase::Copy.md)|현재 선택 영역을 클립보드에 복사합니다.|  
|[CHtmlEditCtrlBase::Cut](../Topic/CHtmlEditCtrlBase::Cut.md)|현재 선택 영역을 클립보드에 복사 하 고 삭제 하는 예제입니다.|  
|[CHtmlEditCtrlBase::Delete](../Topic/CHtmlEditCtrlBase::Delete.md)|현재 선택 영역을 삭제합니다.|  
|[CHtmlEditCtrlBase::DropDownBox](../Topic/CHtmlEditCtrlBase::DropDownBox.md)|드롭다운 선택 컨트롤에 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::EmptyGlyphTable](../Topic/CHtmlEditCtrlBase::EmptyGlyphTable.md)|태그 디자인 모드에 표시 되는 모든 이미지를 숨깁니다 기호 테이블에서 모든 항목을 제거 합니다.|  
|[CHtmlEditCtrlBase::ExecCommand](../Topic/CHtmlEditCtrlBase::ExecCommand.md)|명령을 실행합니다.|  
|[CHtmlEditCtrlBase::Font](../Topic/CHtmlEditCtrlBase::Font.md)|텍스트 색, 글꼴 및 현재 선택 영역의 글꼴 크기를 변경할 수 있도록 글꼴 대화 상자를 엽니다.|  
|[CHtmlEditCtrlBase::GetAbsolutePosition](../Topic/CHtmlEditCtrlBase::GetAbsolutePosition.md)|요소의 위치 속성을 "절대" 인지 여부를 반환 합니다.|  
|[CHtmlEditCtrlBase::GetBackColor](../Topic/CHtmlEditCtrlBase::GetBackColor.md)|현재 선택 영역의 배경색을 검색합니다.|  
|[CHtmlEditCtrlBase::GetBlockFormat](../Topic/CHtmlEditCtrlBase::GetBlockFormat.md)|현재 블록 서식 태그를 검색합니다.|  
|[CHtmlEditCtrlBase::GetBlockFormatNames](../Topic/CHtmlEditCtrlBase::GetBlockFormatNames.md)|사용 가능한 블록 형식 태그에 일치 하는 문자열을 검색 합니다.|  
|[CHtmlEditCtrlBase::GetBookMark](../Topic/CHtmlEditCtrlBase::GetBookMark.md)|책갈피 기준 위치 이름을 검색합니다.|  
|[CHtmlEditCtrlBase::GetDocument](../Topic/CHtmlEditCtrlBase::GetDocument.md)|문서 개체를 검색합니다.|  
|[CHtmlEditCtrlBase::GetDocumentHTML](../Topic/CHtmlEditCtrlBase::GetDocumentHTML.md)|현재 문서의 HTML을 검색합니다.|  
|[CHtmlEditCtrlBase::GetDocumentTitle](../Topic/CHtmlEditCtrlBase::GetDocumentTitle.md)|문서 제목을 검색합니다.|  
|[CHtmlEditCtrlBase::GetEvent](../Topic/CHtmlEditCtrlBase::GetEvent.md)|최신 이벤트와 관련 된 정보가 있는 이벤트 개체에 대 한 인터페이스 포인터를 검색 합니다.|  
|[CHtmlEditCtrlBase::GetEventSrcElement](../Topic/CHtmlEditCtrlBase::GetEventSrcElement.md)|이벤트를 발생 시킨 개체를 검색 합니다.|  
|[CHtmlEditCtrlBase::GetFontFace](../Topic/CHtmlEditCtrlBase::GetFontFace.md)|현재 선택 영역의 글꼴 이름을 검색합니다.|  
|[CHtmlEditCtrlBase::GetFontSize](../Topic/CHtmlEditCtrlBase::GetFontSize.md)|현재 선택 영역의 글꼴 크기를 검색합니다.|  
|[CHtmlEditCtrlBase::GetForeColor](../Topic/CHtmlEditCtrlBase::GetForeColor.md)|현재 선택 영역을 전경색 \(텍스트\)을 검색합니다.|  
|[CHtmlEditCtrlBase::GetFrameZone](../Topic/CHtmlEditCtrlBase::GetFrameZone.md)|웹 브라우저에서 현재 페이지의 보안 영역을 반환합니다.|  
|[CHtmlEditCtrlBase::GetIsDirty](../Topic/CHtmlEditCtrlBase::GetIsDirty.md)|HTML 문서를 변경 했는지 여부를 나타냅니다.|  
|[CHtmlEditCtrlBase::GetShowAlignedSiteTags](../Topic/CHtmlEditCtrlBase::GetShowAlignedSiteTags.md)|모든 요소에 대 한 문자 모양을 표시할지 여부를 반환 하는  **styleFloat** 속성.|  
|[CHtmlEditCtrlBase::GetShowAllTags](../Topic/CHtmlEditCtrlBase::GetShowAllTags.md)|WebBrowser 문서에서 모든 태그의 위치를 표시 하는 문자 모양을 표시할지 여부를 반환 합니다.|  
|[CHtmlEditCtrlBase::GetShowAreaTags](../Topic/CHtmlEditCtrlBase::GetShowAreaTags.md)|WebBrowser 영역 태그의 문자 모양을 표시할지 여부를 검색 합니다.|  
|[CHtmlEditCtrlBase::GetShowBRTags](../Topic/CHtmlEditCtrlBase::GetShowBRTags.md)|WebBrowser br 태그의 문자 모양을 표시할지 여부를 검색 합니다.|  
|[CHtmlEditCtrlBase::GetShowCommentTags](../Topic/CHtmlEditCtrlBase::GetShowCommentTags.md)|WebBrowser 주석 태그에 대 한 문자 모양을 표시할지 여부를 검색 합니다.|  
|[CHtmlEditCtrlBase::GetShowMiscTags](../Topic/CHtmlEditCtrlBase::GetShowMiscTags.md)|Webbrowser에서 Microsoft Internet Explorer 4.0 표시 된 모든 태그를 표시 하는지 여부를 검색 합니다.|  
|[CHtmlEditCtrlBase::GetShowScriptTags](../Topic/CHtmlEditCtrlBase::GetShowScriptTags.md)|Webbrowser의 스크립트 태그에 대 한 문자 모양을 표시할지 여부를 검색 합니다.|  
|[CHtmlEditCtrlBase::GetShowStyleTags](../Topic/CHtmlEditCtrlBase::GetShowStyleTags.md)|WebBrowser 모든 스타일 태그에 대 한 문자 모양을 표시할지 여부를 검색 합니다.|  
|[CHtmlEditCtrlBase::GetShowUnknownTags](../Topic/CHtmlEditCtrlBase::GetShowUnknownTags.md)|Webbrowser를 알 수 없는 모든 태그의 문자 모양을 표시할지 여부를 검색 합니다.|  
|[CHtmlEditCtrlBase::HorizontalLine](../Topic/CHtmlEditCtrlBase::HorizontalLine.md)|가로줄의 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::HyperLink](../Topic/CHtmlEditCtrlBase::HyperLink.md)|현재 선택 영역에 하이퍼링크를 삽입합니다.|  
|[CHtmlEditCtrlBase::IE50Paste](../Topic/CHtmlEditCtrlBase::IE50Paste.md)|Microsoft Internet Explorer 5와 호환 되는 붙여넣기 작업을 수행합니다.|  
|[CHtmlEditCtrlBase::Iframe](../Topic/CHtmlEditCtrlBase::Iframe.md)|인라인 프레임의 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::Image](../Topic/CHtmlEditCtrlBase::Image.md)|이미지에 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::Indent](../Topic/CHtmlEditCtrlBase::Indent.md)|한 들여쓰기 증가값으로 선택한 텍스트의 들여쓰기 간격을 늘립니다.|  
|[CHtmlEditCtrlBase::InsFieldSet](../Topic/CHtmlEditCtrlBase::InsFieldSet.md)|현재 선택 영역에 있는 상자를 덮어씁니다.|  
|[CHtmlEditCtrlBase::InsInputButton](../Topic/CHtmlEditCtrlBase::InsInputButton.md)|단추 컨트롤의 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::InsInputHidden](../Topic/CHtmlEditCtrlBase::InsInputHidden.md)|숨겨진된 컨트롤은 현재 선택 영역에 삽입합니다.|  
|[CHtmlEditCtrlBase::InsInputImage](../Topic/CHtmlEditCtrlBase::InsInputImage.md)|이미지 컨트롤의 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::InsInputPassword](../Topic/CHtmlEditCtrlBase::InsInputPassword.md)|암호 컨트롤의 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::InsInputReset](../Topic/CHtmlEditCtrlBase::InsInputReset.md)|Reset 컨트롤의 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::InsInputSubmit](../Topic/CHtmlEditCtrlBase::InsInputSubmit.md)|전송 컨트롤의 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::InsInputUpload](../Topic/CHtmlEditCtrlBase::InsInputUpload.md)|파일 업로드 컨트롤의 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::Is1DElement](../Topic/CHtmlEditCtrlBase::Is1DElement.md)|정적 요소가 경우 결정 합니다.|  
|[CHtmlEditCtrlBase::Is2DElement](../Topic/CHtmlEditCtrlBase::Is2DElement.md)|요소를 절대적으로 배치 된 경우 결정 합니다.|  
|[CHtmlEditCtrlBase::Italic](../Topic/CHtmlEditCtrlBase::Italic.md)|현재 선택 영역을 기울임꼴 이나 일반 글꼴로 전환합니다.|  
|[CHtmlEditCtrlBase::JustifyCenter](../Topic/CHtmlEditCtrlBase::JustifyCenter.md)|서식 블록 센터에 현재 선택 영역에 위치한.|  
|[CHtmlEditCtrlBase::JustifyLeft](../Topic/CHtmlEditCtrlBase::JustifyLeft.md)|왼쪽 정렬 형식 블록에는 현재 선택 영역에 위치한.|  
|[CHtmlEditCtrlBase::JustifyRight](../Topic/CHtmlEditCtrlBase::JustifyRight.md)|오른쪽 정렬 형식 블록에는 현재 선택 영역에 위치한.|  
|[CHtmlEditCtrlBase::ListBox](../Topic/CHtmlEditCtrlBase::ListBox.md)|목록 상자 선택 영역 컨트롤의 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::Marquee](../Topic/CHtmlEditCtrlBase::Marquee.md)|현재 선택 영역에 있는 빈 선택 윤곽을 덮어씁니다.|  
|[CHtmlEditCtrlBase::NewDocument](../Topic/CHtmlEditCtrlBase::NewDocument.md)|새 문서를 만듭니다.|  
|[CHtmlEditCtrlBase::OrderList](../Topic/CHtmlEditCtrlBase::OrderList.md)|현재 선택 영역을 정렬 된 목록과 일반 포맷 블록을 전환합니다.|  
|[CHtmlEditCtrlBase::Outdent](../Topic/CHtmlEditCtrlBase::Outdent.md)|들여쓰기 서식 블록 1 포인트씩 감소에 현재 선택 영역에 위치한.|  
|[CHtmlEditCtrlBase::Paragraph](../Topic/CHtmlEditCtrlBase::Paragraph.md)|줄 바꿈의 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::Paste](../Topic/CHtmlEditCtrlBase::Paste.md)|현재 선택 영역에 클립보드의 내용을 덮어씁니다.|  
|[CHtmlEditCtrlBase::PrintDocument](../Topic/CHtmlEditCtrlBase::PrintDocument.md)|현재 문서를 인쇄합니다.|  
|[CHtmlEditCtrlBase::PrintPreview](../Topic/CHtmlEditCtrlBase::PrintPreview.md)|기본 인쇄 미리 보기 템플릿 또는 사용자 지정 서식 파일을 사용 하 여 현재 문서를 인쇄 미리 보기 창을 엽니다.|  
|[CHtmlEditCtrlBase::QueryStatus](../Topic/CHtmlEditCtrlBase::QueryStatus.md)|명령 상태를 쿼리 하는이 메서드를 호출 합니다.|  
|[CHtmlEditCtrlBase::RadioButton](../Topic/CHtmlEditCtrlBase::RadioButton.md)|라디오 컨트롤의 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::RefreshDocument](../Topic/CHtmlEditCtrlBase::RefreshDocument.md)|현재 문서를 새로 고칩니다.|  
|[CHtmlEditCtrlBase::RemoveFormat](../Topic/CHtmlEditCtrlBase::RemoveFormat.md)|현재 선택 영역에서 서식 태그를 제거합니다.|  
|[CHtmlEditCtrlBase::SaveAs](../Topic/CHtmlEditCtrlBase::SaveAs.md)|현재 웹 페이지를 파일로 저장합니다.|  
|[CHtmlEditCtrlBase::SelectAll](../Topic/CHtmlEditCtrlBase::SelectAll.md)|전체 문서를 선택합니다.|  
|[CHtmlEditCtrlBase::Set2DPosition](../Topic/CHtmlEditCtrlBase::Set2DPosition.md)|절대 위치로 배치 된 요소를 끌어 이동할 수 있습니다.|  
|[CHtmlEditCtrlBase::SetAbsolutePosition](../Topic/CHtmlEditCtrlBase::SetAbsolutePosition.md)|"절대" 또는 "정적" 요소의 위치 속성 설정|  
|[CHtmlEditCtrlBase::SetAtomicSelection](../Topic/CHtmlEditCtrlBase::SetAtomicSelection.md)|원자 선택 모드를 설정 합니다.|  
|[CHtmlEditCtrlBase::SetAutoURLDetectMode](../Topic/CHtmlEditCtrlBase::SetAutoURLDetectMode.md)|자동 URL 검색을 켜고 끕니다.|  
|[CHtmlEditCtrlBase::SetBackColor](../Topic/CHtmlEditCtrlBase::SetBackColor.md)|현재 선택 영역의 배경색을 설정합니다.|  
|[CHtmlEditCtrlBase::SetBlockFormat](../Topic/CHtmlEditCtrlBase::SetBlockFormat.md)|현재 블록 서식 태그를 설정합니다.|  
|[CHtmlEditCtrlBase::SetBookMark](../Topic/CHtmlEditCtrlBase::SetBookMark.md)|현재 선택 영역 또는 삽입 지점에 대 한 책갈피 기준 위치를 만듭니다.|  
|[CHtmlEditCtrlBase::SetCSSEditingLevel](../Topic/CHtmlEditCtrlBase::SetCSSEditingLevel.md)|선택 어떤 CSS 수준 \(CSS1 또는 CSS2\) 편집기, 있는 경우 지원 됩니다.|  
|[CHtmlEditCtrlBase::SetDefaultComposeSettings](../Topic/CHtmlEditCtrlBase::SetDefaultComposeSettings.md)|작성 설정 기본값을 설정 하려면이 메서드를 호출 합니다.|  
|[CHtmlEditCtrlBase::SetDesignMode](../Topic/CHtmlEditCtrlBase::SetDesignMode.md)|디자인 모드를 설정 합니다.|  
|[CHtmlEditCtrlBase::SetDisableEditFocusUI](../Topic/CHtmlEditCtrlBase::SetDisableEditFocusUI.md)|사선된 테두리를 사용 하지 않도록 설정 하 고 포커스 편집 요소를 처리 합니다.|  
|[CHtmlEditCtrlBase::SetDocumentHTML](../Topic/CHtmlEditCtrlBase::SetDocumentHTML.md)|현재 문서의 HTML을 설정합니다.|  
|[CHtmlEditCtrlBase::SetFontFace](../Topic/CHtmlEditCtrlBase::SetFontFace.md)|현재 선택 영역의 글꼴을 설정합니다.|  
|[CHtmlEditCtrlBase::SetFontSize](../Topic/CHtmlEditCtrlBase::SetFontSize.md)|현재 선택 영역의 글꼴 크기를 설정합니다.|  
|[CHtmlEditCtrlBase::SetForeColor](../Topic/CHtmlEditCtrlBase::SetForeColor.md)|현재 선택 영역을 전경색 \(텍스트\)을 설정합니다.|  
|[CHtmlEditCtrlBase::SetIE5PasteMode](../Topic/CHtmlEditCtrlBase::SetIE5PasteMode.md)|붙여넣기 작업 Microsoft Internet Explorer 5와 호환 되도록 설정 합니다.|  
|[CHtmlEditCtrlBase::SetLiveResize](../Topic/CHtmlEditCtrlBase::SetLiveResize.md)|WebBrowser 요소의 모양 크기 조정 또는 이동 작업 중에 지속적으로 업데이트 됩니다.|  
|[CHtmlEditCtrlBase::SetMultiSelect](../Topic/CHtmlEditCtrlBase::SetMultiSelect.md)|다중 선택 영역이 있습니다.|  
|[CHtmlEditCtrlBase::SetOverrideCursor](../Topic/CHtmlEditCtrlBase::SetOverrideCursor.md)|WebBrowser 절대로 마우스 포인터를 변경 하는 명령입니다.|  
|[CHtmlEditCtrlBase::SetOverwriteMode](../Topic/CHtmlEditCtrlBase::SetOverwriteMode.md)|전환 합니다. 텍스트 입력 모드를 삽입 하 고 덮어쓸.|  
|[CHtmlEditCtrlBase::SetRespectVisInDesign](../Topic/CHtmlEditCtrlBase::SetRespectVisInDesign.md)|디자인 모드에서 보이지 않는 요소를 숨깁니다.|  
|[CHtmlEditCtrlBase::SetShowAlignedSiteTags](../Topic/CHtmlEditCtrlBase::SetShowAlignedSiteTags.md)|모든 요소에 대 한 문자 모양을 표시 한  **styleFloat** 속성.|  
|[CHtmlEditCtrlBase::SetShowAllTags](../Topic/CHtmlEditCtrlBase::SetShowAllTags.md)|문서에서 모든 태그의 위치를 표시 하는 문자를 표시 합니다.|  
|[CHtmlEditCtrlBase::SetShowAreaTags](../Topic/CHtmlEditCtrlBase::SetShowAreaTags.md)|모든 영역 태그의 문자 모양을 표시합니다.|  
|[CHtmlEditCtrlBase::SetShowBRTags](../Topic/CHtmlEditCtrlBase::SetShowBRTags.md)|모든 br 태그의 문자 모양을 표시합니다.|  
|[CHtmlEditCtrlBase::SetShowCommentTags](../Topic/CHtmlEditCtrlBase::SetShowCommentTags.md)|모든 주석 태그의 문자 모양을 표시합니다.|  
|[CHtmlEditCtrlBase::SetShowMiscTags](../Topic/CHtmlEditCtrlBase::SetShowMiscTags.md)|Microsoft Internet Explorer 4.0에서 표시 된 모든 태그를 표시 합니다.|  
|[CHtmlEditCtrlBase::SetShowScriptTags](../Topic/CHtmlEditCtrlBase::SetShowScriptTags.md)|모든 스크립트 태그의 문자 모양을 표시합니다.|  
|[CHtmlEditCtrlBase::SetShowStyleTags](../Topic/CHtmlEditCtrlBase::SetShowStyleTags.md)|모든 스타일 태그에 대 한 문자 모양을 표시합니다.|  
|[CHtmlEditCtrlBase::SetShowUnknownTags](../Topic/CHtmlEditCtrlBase::SetShowUnknownTags.md)|알 수 없는 모든 태그의 문자 모양을 표시합니다.|  
|[CHtmlEditCtrlBase::TextArea](../Topic/CHtmlEditCtrlBase::TextArea.md)|여러 줄 텍스트 입력된 컨트롤에 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::TextBox](../Topic/CHtmlEditCtrlBase::TextBox.md)|텍스트 컨트롤의 현재 선택 영역을 덮어씁니다.|  
|[CHtmlEditCtrlBase::UnBookmark](../Topic/CHtmlEditCtrlBase::UnBookmark.md)|현재 선택 영역에서 모든 책갈피를 제거합니다.|  
|[CHtmlEditCtrlBase::Underline](../Topic/CHtmlEditCtrlBase::Underline.md)|사이 밑줄이 및 밑줄이 없는 현재 선택을 전환 합니다.|  
|[CHtmlEditCtrlBase::Unlink](../Topic/CHtmlEditCtrlBase::Unlink.md)|현재 선택 영역에서 모든 하이퍼링크를 제거합니다.|  
|[CHtmlEditCtrlBase::UnorderList](../Topic/CHtmlEditCtrlBase::UnorderList.md)|현재 선택 영역을 정렬 된 목록과 일반 포맷 블록을 전환합니다.|  
  
#### 매개 변수  
 `T`  
 파생된 클래스의 이름입니다.  
  
## 설명  
 **CHtmlEditCtrlBase**  멤버 함수에 대 한 웹 브라우저의 HTML 편집 명령으로 제공  [굵게](../Topic/CHtmlEditCtrlBase::Bold.md).  \(또는 호출할 수 있는  [ExecCommand](../Topic/CHtmlEditCtrlBase::ExecCommand.md) 를 실행 하는  **IDM\_BOLD** 명령.\)  
  
 **CHtmlEditCtrlBase**  자체 스탠드는 없습니다.  HTML을 편집 하는 웹 브라우저의 기능을 노출 하는 파생된 클래스의 기본 클래스로 사용할 수 있습니다 \(참조  [CHtmlEditCtrl](../../mfc/reference/chtmleditctrl-class.md) 및  [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)\).  
  
## 상속 계층 구조  
 `CHtmlEditCtrlBase`  
  
## 요구 사항  
 **헤더:** afxhtml.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [HTMLEdit 샘플](../../top/visual-cpp-samples.md)