---
title: "CRichEditCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditCtrl
- AFXCMN/CRichEditCtrl
- AFXCMN/CRichEditCtrl::CRichEditCtrl
- AFXCMN/CRichEditCtrl::CanPaste
- AFXCMN/CRichEditCtrl::CanRedo
- AFXCMN/CRichEditCtrl::CanUndo
- AFXCMN/CRichEditCtrl::CharFromPos
- AFXCMN/CRichEditCtrl::Clear
- AFXCMN/CRichEditCtrl::Copy
- AFXCMN/CRichEditCtrl::Create
- AFXCMN/CRichEditCtrl::CreateEx
- AFXCMN/CRichEditCtrl::Cut
- AFXCMN/CRichEditCtrl::DisplayBand
- AFXCMN/CRichEditCtrl::EmptyUndoBuffer
- AFXCMN/CRichEditCtrl::FindText
- AFXCMN/CRichEditCtrl::FindWordBreak
- AFXCMN/CRichEditCtrl::FormatRange
- AFXCMN/CRichEditCtrl::GetCharPos
- AFXCMN/CRichEditCtrl::GetDefaultCharFormat
- AFXCMN/CRichEditCtrl::GetEventMask
- AFXCMN/CRichEditCtrl::GetFirstVisibleLine
- AFXCMN/CRichEditCtrl::GetIRichEditOle
- AFXCMN/CRichEditCtrl::GetLimitText
- AFXCMN/CRichEditCtrl::GetLine
- AFXCMN/CRichEditCtrl::GetLineCount
- AFXCMN/CRichEditCtrl::GetModify
- AFXCMN/CRichEditCtrl::GetOptions
- AFXCMN/CRichEditCtrl::GetParaFormat
- AFXCMN/CRichEditCtrl::GetPunctuation
- AFXCMN/CRichEditCtrl::GetRect
- AFXCMN/CRichEditCtrl::GetRedoName
- AFXCMN/CRichEditCtrl::GetSel
- AFXCMN/CRichEditCtrl::GetSelectionCharFormat
- AFXCMN/CRichEditCtrl::GetSelectionType
- AFXCMN/CRichEditCtrl::GetSelText
- AFXCMN/CRichEditCtrl::GetTextLength
- AFXCMN/CRichEditCtrl::GetTextLengthEx
- AFXCMN/CRichEditCtrl::GetTextMode
- AFXCMN/CRichEditCtrl::GetTextRange
- AFXCMN/CRichEditCtrl::GetUndoName
- AFXCMN/CRichEditCtrl::GetWordWrapMode
- AFXCMN/CRichEditCtrl::HideSelection
- AFXCMN/CRichEditCtrl::LimitText
- AFXCMN/CRichEditCtrl::LineFromChar
- AFXCMN/CRichEditCtrl::LineIndex
- AFXCMN/CRichEditCtrl::LineLength
- AFXCMN/CRichEditCtrl::LineScroll
- AFXCMN/CRichEditCtrl::Paste
- AFXCMN/CRichEditCtrl::PasteSpecial
- AFXCMN/CRichEditCtrl::PosFromChar
- AFXCMN/CRichEditCtrl::Redo
- AFXCMN/CRichEditCtrl::ReplaceSel
- AFXCMN/CRichEditCtrl::RequestResize
- AFXCMN/CRichEditCtrl::SetAutoURLDetect
- AFXCMN/CRichEditCtrl::SetBackgroundColor
- AFXCMN/CRichEditCtrl::SetDefaultCharFormat
- AFXCMN/CRichEditCtrl::SetEventMask
- AFXCMN/CRichEditCtrl::SetModify
- AFXCMN/CRichEditCtrl::SetOLECallback
- AFXCMN/CRichEditCtrl::SetOptions
- AFXCMN/CRichEditCtrl::SetParaFormat
- AFXCMN/CRichEditCtrl::SetPunctuation
- AFXCMN/CRichEditCtrl::SetReadOnly
- AFXCMN/CRichEditCtrl::SetRect
- AFXCMN/CRichEditCtrl::SetSel
- AFXCMN/CRichEditCtrl::SetSelectionCharFormat
- AFXCMN/CRichEditCtrl::SetTargetDevice
- AFXCMN/CRichEditCtrl::SetTextMode
- AFXCMN/CRichEditCtrl::SetUndoLimit
- AFXCMN/CRichEditCtrl::SetWordCharFormat
- AFXCMN/CRichEditCtrl::SetWordWrapMode
- AFXCMN/CRichEditCtrl::StopGroupTyping
- AFXCMN/CRichEditCtrl::StreamIn
- AFXCMN/CRichEditCtrl::StreamOut
- AFXCMN/CRichEditCtrl::Undo
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCtrl class, common controls
- CRichEditCtrl class
- formatted text [C++]
ms.assetid: 2be52788-822c-4c27-aafd-2471231e74eb
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 77b8dfb6011831f4e4300096a127f70b26bcc603
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditctrl-class"></a>CRichEditCtrl 클래스
Rich Edit 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CRichEditCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CRichEditCtrl::CRichEditCtrl](#cricheditctrl)|`CRichEditCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CRichEditCtrl::CanPaste](#canpaste)|이 서식 있는 편집 컨트롤로 클립보드의 내용을 붙여 넣을 수 하는 경우를 결정 합니다.|  
|[CRichEditCtrl::CanRedo](#canredo)|컨트롤의 redo queue의 작업이 있는지 여부를 결정 합니다.|  
|[CRichEditCtrl::CanUndo](#canundo)|편집 작업을 수 있는 경우를 결정 합니다.|  
|[CRichEditCtrl::CharFromPos](#charfrompos)|편집 컨트롤의 클라이언트 영역에서 지정된 된 지점에 가장 가까운 문자에 대 한 정보를 검색합니다.|  
|[CRichEditCtrl::Clear](#clear)|현재 선택을 해제합니다.|  
|[CRichEditCtrl::Copy](#copy)|현재 선택 영역을 클립보드에 복사합니다.|  
|[CRichEditCtrl::Create](#create)|Windows 서식 있는 편집 컨트롤을 만들고이 연결 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::CreateEx](#createex)|Windows rich edit 컨트롤 지정 된 확장 창 스타일을 만들고이 연결 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::Cut](#cut)|클립보드에 현재 선택 영역을 잘라냅니다.|  
|[CRichEditCtrl::DisplayBand](#displayband)|이 내용에 대 한 부분을 표시 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::EmptyUndoBuffer](#emptyundobuffer)|다시 설정 (해제)이 작업의 취소 플래그 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::FindText](#findtext)|이 텍스트를 찾습니다 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::FindWordBreak](#findwordbreak)|다음 단어 구분 하기 전이나 후 지정 된 문자 위치를 찾거나 해당 위치에 있는 문자에 대 한 정보를 검색 합니다.|  
|[CRichEditCtrl::FormatRange](#formatrange)|대상 출력 장치에 대 한 텍스트의 범위를 서식을 지정 합니다.|  
|[CRichEditCtrl::GetCharPos](#getcharpos)|이 지정 된 문자 위치를 결정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetDefaultCharFormat](#getdefaultcharformat)|현재 기본 문자 형식 지정이 특성을 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetEventMask](#geteventmask)|이 대 한 이벤트 마스크 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetFirstVisibleLine](#getfirstvisibleline)|이 표시 되는 맨 위 줄 결정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetIRichEditOle](#getiricheditole)|검색에 대 한 포인터는 `IRichEditOle` 이 rich edit 컨트롤에 대 한 인터페이스입니다.|  
|[CRichEditCtrl::GetLimitText](#getlimittext)|여기에 입력할 수 있는 텍스트의 양에 제한을 가져옵니다 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetLine](#getline)|텍스트 줄이 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetLineCount](#getlinecount)|이 줄의 수를 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetModify](#getmodify)|있는지 여부를 확인이 내용의 `CRichEditCtrl` 개체 마지막 저장 이후 변경 합니다.|  
|[CRichEditCtrl::GetOptions](#getoptions)|서식 있는 편집 컨트롤 옵션을 검색합니다.|  
|[CRichEditCtrl::GetParaFormat](#getparaformat)|단락 서식이 현재 선택한 항목의 특성을 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetPunctuation](#getpunctuation)|Rich edit 컨트롤에 대 한 현재 문장 부호 문자를 검색합니다. 이 메시지는 아시아 언어 버전의 운영 체제 에서만 사용할 수 있습니다.|  
|[CRichEditCtrl::GetRect](#getrect)|이 대 한 서식 지정 영역 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetRedoName](#getredoname)|컨트롤의 모든 큐를 다시 실행 하는 경우에 다음 동작의 종류를 검색 합니다.|  
|[CRichEditCtrl::GetSel](#getsel)|시작과 끝이 현재 선택 항목의 위치를 가져옵니다 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetSelectionCharFormat](#getselectioncharformat)|이 현재 선택한 항목의 특성 서식 문자 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetSelectionType](#getselectiontype)|이 현재 선택한 항목의 콘텐츠 형식을 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::GetSelText](#getseltext)|이 현재 선택 된 텍스트를 가져옵니다 `CRichEditCtrl` 개체|  
|[CRichEditCtrl::GetTextLength](#gettextlength)|이 문자에 있는 텍스트의 길이 검색 `CRichEditCtrl` 개체입니다. Null 종결 문자를 포함 하지 않습니다.|  
|[CRichEditCtrl::GetTextLengthEx](#gettextlengthex)|문자 또는 서식 있는 편집 뷰에 바이트 수를 가져옵니다. Rich edit 컨트롤에서 텍스트의 길이 결정 하는 방법을 지정 하는 플래그의 목록을 허용합니다|  
|[CRichEditCtrl::GetTextMode](#gettextmode)|Rich edit 컨트롤의 현재 텍스트 모드와 실행 취소 수준을 검색합니다.|  
|[CRichEditCtrl::GetTextRange](#gettextrange)|지정한 텍스트 범위를 검색합니다.|  
|[CRichEditCtrl::GetUndoName](#getundoname)|있는 경우 다음 실행 취소 작업의 종류를 검색 합니다.|  
|[CRichEditCtrl::GetWordWrapMode](#getwordwrapmode)|현재 줄 바꿈 및 단어 분리 옵션 rich edit 컨트롤을 검색합니다. 이 메시지는 아시아 언어 버전의 운영 체제 에서만 사용할 수 있습니다.|  
|[CRichEditCtrl::HideSelection](#hideselection)|표시 하거나 현재 선택 영역을 숨깁니다.|  
|[CRichEditCtrl::LimitText](#limittext)|에 입력할 수 있는 텍스트의 양을 제한 하는 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::LineFromChar](#linefromchar)|지정 된 문자를 포함 하는 줄을 결정 합니다.|  
|[CRichEditCtrl::LineIndex](#lineindex)|이 지정된 된 줄의 문자 인덱스를 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::LineLength](#linelength)|이 지정된 된 줄의 길이 검색 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::LineScroll](#linescroll)|이 텍스트가 스크롤됩니다 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::Paste](#paste)|이 서식 있는 편집 컨트롤로 클립보드의 내용을 삽입합니다.|  
|[CRichEditCtrl::PasteSpecial](#pastespecial)|클립보드의 내용이 지정된 된 데이터 형식에서이 서식 있는 편집 컨트롤에 삽입합니다.|  
|[CRichEditCtrl::PosFromChar](#posfromchar)|클라이언트 영역 좌표로 편집 컨트롤에서 지정 된 문자를 검색합니다.|  
|[CRichEditCtrl::Redo](#redo)|컨트롤의 다시 실행 큐에서 다음 작업을 다시 실행합니다.|  
|[CRichEditCtrl::ReplaceSel](#replacesel)|이 현재 선택한 바꿉니다 `CRichEditCtrl` 지정 된 텍스트는 개체입니다.|  
|[CRichEditCtrl::RequestResize](#requestresize)|이 강제로 `CRichEditCtrl` 알림을 크기 조정 요청을 보낼 개체입니다.|  
|[CRichEditCtrl::SetAutoURLDetect](#setautourldetect)|자동 URL을 검색 하는 서식 있는 편집 컨트롤의 활성 인지 여부를 나타냅니다.|  
|[CRichEditCtrl::SetBackgroundColor](#setbackgroundcolor)|배경 색이 설정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetDefaultCharFormat](#setdefaultcharformat)|현재 기본 문자 형식 지정이 특성을 설정 하는 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetEventMask](#seteventmask)|이 대 한 이벤트 마스크 설정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetModify](#setmodify)|설정 하거나이 대 한 수정 플래그를 지웁니다 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetOLECallback](#setolecallback)|설정의 `IRichEditOleCallback` 이 rich edit 컨트롤에 대 한 COM 개체입니다.|  
|[CRichEditCtrl::SetOptions](#setoptions)|이 옵션을 설정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetParaFormat](#setparaformat)|단락 형식 지정이 현재 선택한 항목의 특성을 설정 하는 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetPunctuation](#setpunctuation)|Rich edit 컨트롤에 대 한 문장 부호 문자를 설정합니다. 이 메시지는 아시아 언어 버전의 운영 체제 에서만 사용할 수 있습니다.|  
|[CRichEditCtrl::SetReadOnly](#setreadonly)|이 대 한 읽기 전용 옵션이 설정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetRect](#setrect)|이 대 한 서식 지정 영역 설정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetSel](#setsel)|선택이 설정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetSelectionCharFormat](#setselectioncharformat)|이 현재 선택한 항목의 특성 서식 문자 설정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetTargetDevice](#settargetdevice)|이 대 한 대상 출력 장치 설정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetTextMode](#settextmode)|Rich edit 컨트롤의 텍스트 모드 또는 실행 취소 수준을 설정합니다. 메시지에는 컨트롤에 텍스트를 포함 하는 경우 실패 합니다.|  
|[CRichEditCtrl::SetUndoLimit](#setundolimit)|실행 취소 큐에 저장할 수 있는 작업의 최대 수를 설정 합니다.|  
|[CRichEditCtrl::SetWordCharFormat](#setwordcharformat)|이 현재 단어의 특성 서식 문자 설정 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::SetWordWrapMode](#setwordwrapmode)|컨트롤을 편집 하는 풍부한에 대 한 자동 줄 바꿈 및 단어 분리 옵션을 설정 합니다. 이 메시지는 아시아 언어 버전의 운영 체제 에서만 사용할 수 있습니다.|  
|[CRichEditCtrl::StopGroupTyping](#stopgrouptyping)|컨트롤에서 수집 현재 실행 취소 작업에 작업을 입력 하 고 추가 중지 합니다. 컨트롤 실행 취소 큐에서 새 작업에 있는 경우 다음 입력 작업을 저장 합니다.|  
|[CRichEditCtrl::StreamIn](#streamin)|여기에 입력 스트림에서 텍스트 삽입 `CRichEditCtrl` 개체입니다.|  
|[CRichEditCtrl::StreamOut](#streamout)|이 텍스트를 저장 `CRichEditCtrl` 출력 스트림으로 개체입니다.|  
|[CRichEditCtrl::Undo](#undo)|마지막 편집 작업을 취소합니다.|  
  
## <a name="remarks"></a>주의  
 "Rich edit 컨트롤"에 사용자 입력 하 고 텍스트를 편집 창입니다. 텍스트 문자와 단락 서식이 할당할 수 있으며 포함 된 OLE 개체를 포함할 수 있습니다. Rich edit 컨트롤 텍스트의 서식을 지정 하는 프로그래밍 인터페이스를 제공 합니다. 그러나 응용 프로그램 사용자에 게 서식 지정 작업을 제공 하는 데 필요한 사용자 인터페이스 구성 요소를 구현 해야 합니다.  
  
 이 Windows 공용 컨트롤 (및 따라서는 `CRichEditCtrl` 클래스)은 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수 있습니다. `CRichEditCtrl` 클래스의 버전 2.0 및 3.0 지원는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] rich edit 컨트롤입니다.  
  
> [!CAUTION]
>  Rich edit 컨트롤을 사용 하는 대화 상자에서 하는 경우 (응용 프로그램은 MDI SDI 여부에 관계 없이 또는 대화 상자 기반)를 호출 해야 [AfxInitRichEdit](application-information-and-management.md#afxinitrichedit) 대화 상자가 표시 되 면 합니다. 이 함수를 호출 하는 일반적인 곳은 프로그램의 `InitInstance` 멤버 함수입니다. 처음에만 대화 상자를 표시할 때마다를 호출할 필요가 없습니다. 호출할 필요가 없습니다 `AfxInitRichEdit` 사용 하는 경우 `CRichEditView`합니다.  
  
 사용 하 여 대 한 자세한 내용은 `CRichEditCtrl`를 참조 하십시오.  
  
- [컨트롤](../../mfc/controls-mfc.md)  
  
- [CRichEditCtrl 사용](../../mfc/using-cricheditctrl.md)  
  
-   기술 자료 문서 Q259949: 정보: SetCaretPos()는 적합 하지 않은 CEdit 또는 CRichEditCtrl 컨트롤  
  
 Rich edit 컨트롤을 사용 하 여 MFC 응용 프로그램의 예를 들어 참조는 [워드 패드](../../visual-cpp-samples.md) 샘플 응용 프로그램입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CRichEditCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="canpaste"></a>CRichEditCtrl::CanPaste  
 Rich edit 컨트롤 경우 지정 된 클립보드 형식을 붙여넣을 수를 결정 합니다.  
  
```  
BOOL CanPaste(UINT nFormat = 0) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nFormat`  
 쿼리를 클립보드 데이터 형식입니다. 이 매개 변수는 미리 정의 된 클립보드 형식 또는 반환 값 중 하나일 수 있습니다 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049)합니다.  
  
### <a name="return-value"></a>반환 값  
 클립보드 형식을 붙여넣을 수 있습니다. 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 경우 `nFormat` 가 0 이면 `CanPaste` 현재 클립보드에 모든 형식을 시도 합니다.  
  
 자세한 내용은 참조 [EM_CANPASTE](http://msdn.microsoft.com/library/windows/desktop/bb787993) 메시지 및 [됩니다](http://msdn.microsoft.com/library/windows/desktop/ms649049) 함수는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&1;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_1.cpp)]  
  
##  <a name="canredo"></a>CRichEditCtrl::CanRedo  
 Redo queue 모든 동작을 포함 하는 경우를 결정 합니다.  
  
```  
BOOL CanRedo() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 속성을 0이 아닌 redo queue 동작, 그렇지 않으면 0을 포함 합니다.  
  
### <a name="remarks"></a>주의  
 Redo queue에 있는 작업의 이름을 검색 하려면 호출 [CRichEditCtrl::GetRedoName](#getredoname)합니다. 가장 최근 실행 취소 작업을 다시 실행 하려면 호출 [다시 실행](#redo)합니다.  
  
 자세한 내용은 참조 [EM_CANREDO](http://msdn.microsoft.com/library/windows/desktop/bb787995) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="canundo"></a>CRichEditCtrl::CanUndo  
 마지막 편집 작업을 취소할 수는 경우를 결정 합니다.  
  
```  
BOOL CanUndo() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 호출 마지막 편집 작업을 취소 하면 0이 아니고는 [취소](#undo) 멤버 함수, 실행 취소할 수 없는 경우 0입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [EM_CANUNDO](http://msdn.microsoft.com/library/windows/desktop/bb775468) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&2;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_2.cpp)]  
  
##  <a name="charfrompos"></a>CRichEditCtrl::CharFromPos  
 매개 변수에 의해 지정 된 지점에 있는 문자에 대 한 정보를 검색 `pt`합니다.  
  
```  
int CharFromPos(CPoint pt) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 지정 된 지점의 좌표를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 지정된 된 지점에 가장 가까운 문자의&0;부터 시작 문자 인덱스입니다. 지정된 된 점이 컨트롤의 마지막 문자 뒤에 있는 경우 반환 값은 컨트롤의 마지막 문자를 나타냅니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 서식 있는 편집 컨트롤 작동합니다. 편집 컨트롤에 대 한 정보를 가져오려면 호출 [CEdit::CharFromPos](../../mfc/reference/cedit-class.md#charfrompos)합니다.  
  
 자세한 내용은 참조 [EM_CHARFROMPOS](http://msdn.microsoft.com/library/windows/desktop/bb761566) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="clear"></a>CRichEditCtrl::Clear  
 (취소)를 삭제 합니다. 현재 선택 영역 (있는 경우)는 서식 있는 편집 컨트롤입니다.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>주의  
 수행한 삭제 **지우기** 를 호출 하 여 실행 취소 될 수는 [취소](#undo) 멤버 함수입니다.  
  
 현재 선택 영역을 삭제 하 고 삭제 된 내용을 클립보드에 배치 하려면 호출는 [잘라내기](#cut) 멤버 함수입니다.  
  
 자세한 내용은 참조 [WM_CLEAR](http://msdn.microsoft.com/library/windows/desktop/ms649020) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&3;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_3.cpp)]  
  
##  <a name="copy"></a>CRichEditCtrl::Copy  
 현재 선택 영역 (있는 경우) rich edit 컨트롤에서 클립보드에 복사 합니다.  
  
```  
void Copy();
```  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [WM_COPY](http://msdn.microsoft.com/library/windows/desktop/ms649022) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&4;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_4.cpp)]  
  
##  <a name="create"></a>CRichEditCtrl::Create  
 Windows 서식 있는 편집 컨트롤을 만들고이 연결 `CRichEditCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 편집 컨트롤의 스타일을 지정합니다. 에 나열 된 창 스타일의 조합을 적용할는 **주의** 아래의 섹션 및 [편집 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775464)에서 설명의 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `rect`  
 편집 컨트롤의 크기와 위치를 지정합니다. 수는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](../../mfc/reference/rect-structure1.md) 구조입니다.  
  
 `pParentWnd`  
 편집 컨트롤의 부모 창 지정 (대개는 [CDialog](../../mfc/reference/cdialog-class.md)). 않아야 **NULL**합니다.  
  
 `nID`  
 편집 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 초기화에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 생성 한 `CRichEditCtrl` 두 단계에서는 개체입니다. 먼저를 호출 하는 [CRichEditCtrl](#cricheditctrl) 생성자 호출 **만들기**, Windows 편집 컨트롤을 만들고 연결 하는 `CRichEditCtrl` 개체입니다.  
  
 이 함수를 서식 있는 편집 컨트롤을 만들 때 필요한 공용 컨트롤 라이브러리를 로드 해야 먼저. 라이브러리를 로드 하려면 전역 함수를 호출 [AfxInitRichEdit](application-information-and-management.md#afxinitrichedit), 공용 컨트롤 라이브러리를 다시 초기화입니다. 호출 해야 `AfxInitRichEdit` 프로세스에서 한 번만 합니다.  
  
 때 **만들기** Windows 보냅니다 실행 되는 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), 및 [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 편집 컨트롤에 메시지를 합니다.  
  
 에서는 기본적으로 이러한 메시지의 처리는 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), 및 [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 에서 멤버 함수는 `CWnd` 기본 클래스입니다. 기본 메시지 처리를 확장 하려면에서 클래스를 파생 `CRichEditCtrl`, 새 클래스에 메시지 맵에 추가 하 고 위의 메시지-처리기 멤버 함수를 재정의 합니다. 재정의 `OnCreate`예를 들어, 새 클래스에 대 한 필요한 초기화를 수행 하도록 합니다.  
  
 다음 적용 [창 스타일](../../mfc/reference/window-styles.md) 를 편집 컨트롤입니다.  
  
- **WS_CHILD** 항상 있습니다.  
  
- **WS_VISIBLE** 대개.  
  
- **WS_DISABLED** 거의 없습니다.  
  
- **WS_GROUP** 컨트롤을 그룹화 합니다.  
  
- **WS_TABSTOP** 탭 이동 순서에 편집 컨트롤을 포함 합니다.  
  
 창 스타일에 대 한 자세한 내용은 참조 [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&5;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_5.cpp)]  
  
##  <a name="createex"></a>CRichEditCtrl::CreateEx  
 컨트롤 (자식 창)와 연결 된 `CRichEditCtrl` 개체입니다.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwExStyle`  
 생성 되는 컨트롤의 확장된 스타일을 지정 합니다. 확장된 창 스타일의 목록에 대 한 참조는 `dwExStyle` 에 대 한 매개 변수 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `dwStyle`  
 편집 컨트롤의 스타일을 지정합니다. 에 나열 된 창 스타일의 조합을 적용할는 **주의** 의 섹션 [만들기](#create) 및 [편집 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775464)에서 설명의 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와의 클라이언트 좌표에서 만든 창 위치를 설명 하는 구조 `pParentWnd`합니다.  
  
 `pParentWnd`  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 컨트롤의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 `CreateEx` 대신 **만들기** Windows 확장된 스타일 앞에 지정 된 Windows 확장된 스타일을 적용 하려면 **WS_EX_**합니다.  
  
##  <a name="cricheditctrl"></a>CRichEditCtrl::CRichEditCtrl  
 `CRichEditCtrl` 개체를 생성합니다.  
  
```  
CRichEditCtrl();
```  
  
### <a name="remarks"></a>주의  
 사용 하 여 [만들기](#create) rich edit 컨트롤 Windows를 만들려고 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&6;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_6.cpp)]  
  
##  <a name="cut"></a>CRichEditCtrl::Cut  
 (사용)를 삭제 합니다. 현재 선택 영역 (있는 경우)는 풍부한 컨트롤을 편집 하 고 삭제 된 텍스트를 클립보드에 복사 합니다.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>주의  
 수행한 삭제 **잘라내기** 를 호출 하 여 실행 취소 될 수는 [취소](#undo) 멤버 함수입니다.  
  
 삭제 된 텍스트를 클립보드에 배치 하지 않고 현재 선택 영역을 삭제 하려면 호출의 [지우기](#clear) 멤버 함수입니다.  
  
 자세한 내용은 참조 [WM_CUT](http://msdn.microsoft.com/library/windows/desktop/ms649023) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&7;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_7.cpp)]  
  
##  <a name="displayband"></a>CRichEditCtrl::DisplayBand  
 앞에서 설명한 대로 서식 지정 (텍스트 및 OLE 항목) rich edit 컨트롤의 내용의 부분을 표시 [FormatRange](#formatrange)합니다.  
  
```  
BOOL DisplayBand(LPRECT pDisplayRect);
```  
  
### <a name="parameters"></a>매개 변수  
 `pDisplayRect`  
 에 대 한 포인터는 [RECT](../../mfc/reference/rect-structure1.md) 또는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 텍스트를 표시 하는 장치의 영역을 지정 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이 속성을 0이 아닌 서식 있는 텍스트의 표시에 성공 하면, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 OLE 항목와 텍스트 포인터에 의해 지정 된 영역을 자르는 `pDisplayRect`합니다.  
  
 자세한 내용은 참조 [EM_DISPLAYBAND](http://msdn.microsoft.com/library/windows/desktop/bb787997) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CRichEditCtrl::FormatRange](#formatrange)합니다.  
  
##  <a name="emptyundobuffer"></a>CRichEditCtrl::EmptyUndoBuffer  
 (Clear)이 rich edit 컨트롤의 실행 취소 플래그를 다시 설정합니다.  
  
```  
void EmptyUndoBuffer();
```  
  
### <a name="remarks"></a>주의  
 컨트롤 이제 없게 됩니다 마지막 편집 작업을 취소할 수 있습니다. Rich edit 컨트롤 내에서 작업을 취소할 수 때마다 실행 취소 플래그가 설정 됩니다.  
  
 호출할 때마다 자동으로 실행 취소 플래그가 지워 졌다 고 [CWnd](../../mfc/reference/cwnd-class.md) 멤버 함수 [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext)합니다.  
  
 자세한 내용은 참조 [EM_EMPTYUNDOBUFFER](http://msdn.microsoft.com/library/windows/desktop/bb761568) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&8;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_8.cpp)]  
  
##  <a name="findtext"></a>CRichEditCtrl::FindText  
 서식 있는 편집 컨트롤에서 텍스트를 찾습니다.  
  
```  
long FindText(
    DWORD dwFlags,  
    FINDTEXTEX* pFindText) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `dwFlags`  
 가능한 값 목록은 참조 하십시오. `wParam` 에서 [EM_FINDTEXTEXT](http://msdn.microsoft.com/library/windows/desktop/bb788011) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 *pFindText*  
 에 대 한 포인터는 [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) 구조 검색에 대 한 매개 변수를 제공 하 고 일치 항목이 발견 된 범위를 반환 합니다.  
  
### <a name="return-value"></a>반환 값  
 일치 하는 다음;의 0부터 시작 문자 위치 -더 이상 일치 하는 경우에 1입니다.  
  
### <a name="remarks"></a>주의  
 에 적절 한 범위 매개 변수 설정 중 하나를 위로 또는 아래로 검색할 수 있습니다는 [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) 내에서 구조체는 **FINDTEXTEX** 구조입니다.  
  
 자세한 내용은 참조 [EM_FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb788011) 메시지 및 [FINDTEXTEX](http://msdn.microsoft.com/library/windows/desktop/bb787909) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&9;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_9.cpp)]  
  
##  <a name="findwordbreak"></a>CRichEditCtrl::FindWordBreak  
 앞 이나 뒤에 지정 된 위치에 다음 단어 구분을 찾습니다 `nStart`합니다.  
  
```  
DWORD FindWordBreak(
    UINT nCode,  
    DWORD nStart) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nCode`  
 수행할 동작을 나타냅니다. 가능한 값 목록은 매개 변수에 대 한 설명을 참조 `code` 에서 **EM_FINDWORDBREAK** 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `nStart`  
 시작할&0;부터 시작 문자 위치입니다.  
  
### <a name="return-value"></a>반환 값  
 매개 변수에 따라 `nCode`합니다. 자세한 내용은 참조 [EM_FINDWORDBREAK](http://msdn.microsoft.com/library/windows/desktop/bb788018) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 지정된 된 위치에 있는 문자에 대 한 정보를 검색 하려면이 멤버 함수를 사용할 수 있습니다.  
  
##  <a name="formatrange"></a>CRichEditCtrl::FormatRange  
 특정 장치에 대 한 서식 있는 편집 컨트롤에서 텍스트 범위의 서식을 지정 합니다.  
  
```  
long FormatRange(
    FORMATRANGE* pfr,  
    BOOL bDisplay = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *pfr*  
 에 대 한 포인터는 [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911) 구조 출력 장치에 대 한 정보를 포함 합니다. **NULL** 나타내는 서식 있는 편집 컨트롤 내에서 캐시 된 정보를 해제할 수 있습니다.  
  
 *bDisplay*  
 텍스트를 렌더링할지 여부를 나타냅니다. 경우 **FALSE**, 텍스트 바로 측정 됩니다.  
  
### <a name="return-value"></a>반환 값  
 1을 더한 지역 내에 포함 된 마지막 문자 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 호출 하 여이 호출 뒤에 일반적으로 [DisplayBand](#displayband)합니다.  
  
 자세한 내용은 참조 [EM_FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb788020) 메시지 및 [FORMATRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787911) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&10;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_10.cpp)]  
  
##  <a name="getcharpos"></a>CRichEditCtrl::GetCharPos  
 이 지정 된 문자 위치 (왼쪽 위 모퉁이)를 가져옵니다 `CRichEditCtrl` 개체입니다.  
  
```  
CPoint GetCharPos(long lChar) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lChar`  
 문자의&0;부터 시작 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 로 지정 된 문자의 왼쪽 위 모퉁이 위치 `lChar`합니다.  
  
### <a name="remarks"></a>주의  
 문자는&0;부터 시작 인덱스 값을 지정 하 여 지정 됩니다. 경우 `lChar` 이 마지막 문자의 인덱스 보다 크면 `CRichEditCtrl` 개체를 반환 값이 마지막 문자 바로 다음에 오는 문자 위치 좌표를 지정 `CRichEditCtrl` 개체입니다.  
  
 자세한 내용은 참조 [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getdefaultcharformat"></a>CRichEditCtrl::GetDefaultCharFormat  
 이 특성을 서식 지정 하는 기본 문자를 가져옵니다 `CRichEditCtrl` 개체입니다.  
  
```  
DWORD GetDefaultCharFormat(CHARFORMAT& cf) const;  DWORD GetDefaultCharFormat(CHARFORMAT2& cf) const;  ```  
  
### Parameters  
 `cf`  
 In the first version, a pointer to a **CHARFORMAT** structure holding the default character formatting attributes.  
  
 In the second version, a pointer to a **CHARFORMAT2** structure, which is a Rich Edit 2.0 extension to the **CHARFORMAT** structure, holding the default character formatting attributes.  
  
### Return Value  
 The **dwMask** data member of `cf`. It specified the default character formatting attributes.  
  
### Remarks  
 For more information, see the **EM_GETCHARFORMAT** message and the **CHARFORMAT** and **CHARFORMAT2** structures in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [SetDefaultCharFormat](#setdefaultcharformat).  
  
##  <a name="geteventmask"></a>  CRichEditCtrl::GetEventMask  
 Gets the event mask for this `CRichEditCtrl` object.  
  
```  
긴 GetEventMask() const;  
```  
  
### Return Value  
 The event mask for this `CRichEditCtrl` object.  
  
### Remarks  
 The event mask specifies which notification messages the `CRichEditCtrl` object sends to its parent window.  
  
 For more information, see [EM_GETEVENTMASK](http://msdn.microsoft.com/library/windows/desktop/bb788032) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [CRichEditCtrl::SetEventMask](#seteventmask).  
  
##  <a name="getfirstvisibleline"></a>  CRichEditCtrl::GetFirstVisibleLine  
 Determines the topmost visible line in this `CRichEditCtrl` object.  
  
```  
int GetFirstVisibleLine() const;  
```  
  
### Return Value  
 Zero-based index of the uppermost visible line in this `CRichEditCtrl` object.  
  
### Remarks  
 For more information, see [EM_GETFIRSTVISIBLELINE](http://msdn.microsoft.com/library/windows/desktop/bb761574) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#11](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_11.cpp)]  
  
##  <a name="getiricheditole"></a>  CRichEditCtrl::GetIRichEditOle  
 Accesses the **IRichEditOle** interface for this `CRichEditCtrl` object.  
  
```  
IRichEditOle * GetIRichEditOle() const;  
```  
  
### Return Value  
 Pointer to the [IRichEditOle](http://msdn.microsoft.com/library/windows/desktop/bb774306) interface that can be used to access this `CRichEditCtrl` object's OLE functionality; **NULL** if the interface is not accessible.  
  
### Remarks  
 Use this interface to access this `CRichEditCtrl` object's OLE functionality.  
  
 For more information, see [EM_GETOLEINTERFACE](http://msdn.microsoft.com/library/windows/desktop/bb788041) message and [IRichEditOle](http://msdn.microsoft.com/library/windows/desktop/bb774306) interface in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getlimittext"></a>  CRichEditCtrl::GetLimitText  
 Gets the text limit for this `CRichEditCtrl` object.  
  
```  
긴 GetLimitText() const;  
```  
  
### Return Value  
 The current text limit, in bytes, for this `CRichEditCtrl` object.  
  
### Remarks  
 The text limit is the maximum amount of text, in bytes, the rich edit control can accept.  
  
 For more information, see [EM_GETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761582) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#12](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_12.cpp)]  
  
##  <a name="getline"></a>  CRichEditCtrl::GetLine  
 Retrieves a line of text from this `CRichEditCtrl` object.  
  
```  
GetLine (int nIndex, int  
    LPTSTR lpszBuffer) const;  
  
GetLine (int nIndex, int  
    LPTSTR lpszBuffer  
    int nMaxLength) const;  
```  
  
### Parameters  
 `nIndex`  
 Zero-based index of the line to retrieve.  
  
 `lpszBuffer`  
 Points to the buffer to receive the text. The first word of the buffer must specify the maximum number of bytes that can be copied into the buffer.  
  
 `nMaxLength`  
 Maximum number of characters that can be copied into `lpszBuffer`. The second form of `GetLine` places this value into the first word of the buffer specified by `lpszBuffer`.  
  
### Return Value  
 The number of characters copied into `lpszBuffer`.  
  
### Remarks  
 The copied line does not contain a terminating null character.  
  
> [!NOTE]
>  Because the first word of the buffer stores the number of characters to be copied, make sure that your buffer is at least 4 bytes long.  
  
 For more information, see [EM_GETLINE](http://msdn.microsoft.com/library/windows/desktop/bb761584) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [GetLineCount](#getlinecount).  
  
##  <a name="getlinecount"></a>  CRichEditCtrl::GetLineCount  
 Retrieves the number of lines in the `CRichEditCtrl` object.  
  
```  
int GetLineCount() const;  
```  
  
### Return Value  
 The number of lines in this `CRichEditCtrl` object.  
  
### Remarks  
 For more information, see [EM_GETLINECOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761586) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#13](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_13.cpp)]  
  
##  <a name="getmodify"></a>  CRichEditCtrl::GetModify  
 Determines if the contents of this `CRichEditCtrl` object have been modified.  
  
```  
BOOL GetModify() const;  
```  
  
### Return Value  
 Nonzero if the text in this `CRichEditCtrl` object has been modified; otherwise 0.  
  
### Remarks  
 Windows maintains an internal flag indicating whether the contents of the rich edit control have been changed. This flag is cleared when the edit control is first created and can also be cleared by calling the [SetModify](#setmodify) member function.  
  
 For more information, see [EM_GETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761592) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#14](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_14.cpp)]  
  
##  <a name="getoptions"></a>  CRichEditCtrl::GetOptions  
 Retrieves the options currently set for the rich edit control.  
  
```  
UINT GetOptions() const;  
```  
  
### Return Value  
 A combination of the current option flag values. For a list of these values, see the *fOptions* parameter in the [EM_SETOPTIONS](http://msdn.microsoft.com/library/windows/desktop/bb774254) message, as described in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getparaformat"></a>  CRichEditCtrl::GetParaFormat  
 Gets the paragraph formatting attributes of the current selection.  
  
```  
DWORD GetParaFormat(PARAFORMAT& pf) const;  DWORD GetParaFormat(PARAFORMAT2& pf) const;  ```  
  
### <a name="parameters"></a>매개 변수  
 `pf`  
 첫 번째 버전에 대 한 포인터는 [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940) 단락 서식 현재 선택 된 특성을 보유 하는 구조입니다.  
  
 두 번째 버전에 대 한 포인터는 [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) 서식 있는 편집 2.0 확장인 구조에는 **PARAFORMAT** 구조를 서식 특성의 기본 문자를 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 **dwMask** 데이터 멤버의 `pf`합니다. 단락 서식 현재 선택 영역 전체에 걸쳐 일관적인 특성을 지정 합니다.  
  
### <a name="remarks"></a>주의  
 여러 단락을 선택 하면 `pf` 선택한 첫 번째 단락의 특성을 받습니다. 반환 값은 선택 영역 전체에 걸쳐 일관성 있는 특성을 지정 합니다.  
  
 자세한 내용은 참조는 [EM_GETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774182) 메시지 및 **PARAFORMAT** 및 **PARAFORMAT2** 구조체에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CRichEditCtrl::SetParaFormat](#setparaformat)합니다.  
  
##  <a name="getpunctuation"></a>CRichEditCtrl::GetPunctuation  
 Rich edit 컨트롤의 현재 문장 부호 문자를 가져옵니다.  
  
```  
BOOL GetPunctuation(
    UINT fType,  
    PUNCTUATION* lpPunc) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `fType`  
 에 설명 된 대로 문장 부호 형식 플래그는 `fType` 의 매개 변수 [EM_GETPUNCTUATION](http://msdn.microsoft.com/library/windows/desktop/bb774184) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `lpPunc`  
 에 대 한 포인터는 [문장 부호](http://msdn.microsoft.com/library/windows/desktop/bb787944) 구조체에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 이 속성을 0이 아닌 작업에 성공한 경우, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 운영 체제의 아시아 언어 버전에만 사용할 수 있습니다.  
  
##  <a name="getrect"></a>CRichEditCtrl::GetRect  
 이 대 한 서식 지정 영역 검색 `CRichEditCtrl` 개체입니다.  
  
```  
void GetRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect`  
 [CRect](../../atl-mfc-shared/reference/crect-class.md) 또는에 대 한 포인터는 [RECT](../../mfc/reference/rect-structure1.md) 이 서식 지정 영역을 받을 `CRichEditCtrl` 개체입니다.  
  
### <a name="remarks"></a>주의  
 서식 지정 영역 텍스트에 대 한 경계 사각형을입니다. 이 값은의 크기에 관계 없이 `CRichEditCtrl` 개체입니다.  
  
 자세한 내용은 참조 [EM_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761596) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [LimitText](#limittext)합니다.  
  
##  <a name="getredoname"></a>CRichEditCtrl::GetRedoName  
 있는 경우 redo queue에 다음 사용 가능한 동작의 유형을 검색 합니다.  
  
```  
UNDONAMEID GetRedoName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 `GetRedoName` 반환 된 [UNDONAMEID](http://msdn.microsoft.com/library/windows/desktop/bb774365) 컨트롤의 다시 실행 큐에서 다음 작업의 형식을 나타내는 열거형입니다. Redo queue 비어 있으면 또는 큐에 다시 실행 동작을 알 수 없는 유형의 경우 `GetRedoName` 0을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 실행 취소 하거나 다시 실행할 수 있는 작업의 종류에는 입력, 삭제, 끌어서 놓기, 잘라내기 및 붙여넣기 작업. 이 정보는 redoable 작업의 드롭다운 목록 상자 등의 실행 취소 및 다시 실행 작업을 위한 확장된 된 사용자 인터페이스를 제공 하는 응용 프로그램에 유용할 수 있습니다.  
  
##  <a name="getsel"></a>CRichEditCtrl::GetSel  
 이 현재 선택 항목의 범위 검색 `CRichEditCtrl` 개체입니다.  
  
```  
void GetSel(CHARRANGE& cr) const;  
  
void GetSel(
    long& nStartChar,  
    long& nEndChar) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `cr`  
 에 대 한 참조는 [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) 구조 현재 선택 항목의 범위를 받을 수 있습니다.  
  
 `nStartChar`  
 현재 선택한 항목의 첫 번째 문자의&0;부터 시작 인덱스입니다.  
  
 `nEndChar`  
 현재 선택한 항목의 마지막 문자 인덱스&0;부터 시작 합니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 두 가지 형태의 선택 영역에 대 한 경계를 가져올 수 있는 다른 방법을 제공 합니다. 이 폼의 간략 한 설명을 따르십시오.  
  
- **GetSel (** `cr` **)** 이 폼에서 사용 하는 **CHARRANGE** 구조체를 해당 **cpMin** 및 **cpMax** 범위를 반환 하는 멤버입니다.  
  
- **GetSel (** `nStartChar` **,** `nEndChar` **)** 매개 변수에서 경계를 반환 하는이 양식을 `nStartChar` 및 `nEndChar`합니다.  
  
 선택 영역 모든 포함 된 경우 시작 부분 ( **cpMin** 또는 `nStartChar`)은 0 이며 마지막 ( **cpMax** 또는 `nEndChar`)는-1입니다.  
  
 자세한 내용은 참조 [EM_EXGETSEL](http://msdn.microsoft.com/library/windows/desktop/bb788001) 메시지 및 [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&15;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_15.cpp)]  
  
##  <a name="getselectioncharformat"></a>CRichEditCtrl::GetSelectionCharFormat  
 문자에 현재 선택 된 특성 서식 가져옵니다.  
  
```  
DWORD GetSelectionCharFormat(CHARFORMAT& cf) const;  DWORD GetSelectionCharFormat(CHARFORMAT2& cf) const;  ```  
  
### Parameters  
 `cf`  
 In the first version, a pointer to a [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) structure to receive the character formatting attributes of the current selection.  
  
 In the second version, a pointer to a [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) structure, which is a Rich Edit 2.0 extension to the **CHARFORMAT** structure to receive the character formatting attributes of the current selection.  
  
### Return Value  
 The **dwMask** data member of `cf`. It specifies the character formatting attributes that are consistent throughout the current selection.  
  
### Remarks  
 The `cf` parameter receives the attributes of the first character in the current selection. The return value specifies which attributes are consistent throughout the selection.  
  
 For more information, see the [EM_GETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb788026) message and the **CHARFORMAT** and **CHARFORMAT2** structures in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
  See the example for [SetSelectionCharFormat](#setselectioncharformat).  
  
##  <a name="getselectiontype"></a>  CRichEditCtrl::GetSelectionType  
 Determines the selection type in this `CRichEditCtrl` object.  
  
```  
WORD GetSelectionType() const;  
```  
  
### Return Value  
 Flags indicating the contents of the current selection. A combination of the following flags:  
  
- `SEL_EMPTY` Indicates that there is no current selection.  
  
- `SEL_TEXT` Indicates that the current selection contains text.  
  
- `SEL_OBJECT` Indicates that the current selection contains at least one OLE item.  
  
- `SEL_MULTICHAR` Indicates that the current selection contains more than one character of text.  
  
- `SEL_MULTIOBJECT` Indicates that the current selection contains more than one OLE object.  
  
### Remarks  
 For more information, see [EM_SELECTIONTYPE](http://msdn.microsoft.com/library/windows/desktop/bb774223) in the [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### Example  
 [!code-cpp[NVC_MFC_CRichEditCtrl#16](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_16.cpp)]  
  
##  <a name="getseltext"></a>  CRichEditCtrl::GetSelText  
 Retrieves the text from the current selection in this `CRichEditCtrl` object.  
  
```  
긴 GetSelText(LPSTR lpBuf) const;  CString GetSelText() const;  ```  
  
### <a name="parameters"></a>매개 변수  
 `lpBuf`  
 현재 선택한 항목의 텍스트를 수신 하는 버퍼에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 폼에 따라 달라 집니다.  
  
- **GetSelText (** `lpBuf` **)** 복사할 문자의 수 `lpBuf`, null 종료를 제외 합니다.  
  
- **GetSelText ()** 현재 선택 영역을 포함 하는 문자열입니다.  
  
### <a name="remarks"></a>주의  
 첫 번째 폼을 사용 하는 경우 **GetSelText (** `lpBuf` **)**, 버퍼 받습니다 텍스트에 충분히 큰지 확인 해야 합니다. 호출 [GetSel](#getsel) 현재 선택 영역에 있는 문자의 수를 결정 합니다.  
  
 자세한 내용은 참조 [EM_GETSELTEXT](http://msdn.microsoft.com/library/windows/desktop/bb774190) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CRichEditCtrl::GetSelectionType](#getselectiontype)합니다.  
  
##  <a name="gettextlength"></a>CRichEditCtrl::GetTextLength  
 이 문자에 있는 텍스트의 길이 검색 `CRichEditCtrl` 개체를 null 종결 문자를 포함 하지 않습니다.  
  
```  
long GetTextLength() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 텍스트의 길이 `CRichEditCtrl` 개체입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [WM_GETTEXTLENGTH](http://msdn.microsoft.com/library/windows/desktop/ms632628) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&17;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_17.cpp)]  
  
##  <a name="gettextlengthex"></a>CRichEditCtrl::GetTextLengthEx  
 Rich edit 컨트롤에서 텍스트의 길이 계산합니다.  
  
```  
long GetTextLengthEx(
    DWORD dwFlags,  
    UINT uCodePage = -1) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `dwFlags`  
 텍스트 길이 결정 하는 데 사용할 방법을 지정 하는 값입니다. 이 멤버 하나 이거나 플래그 소속에 나열 된 값 [GETTEXTLENGTHEX](http://msdn.microsoft.com/library/windows/desktop/bb787915) 에 설명 된는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `uCodePage`  
 번역 (1200 유니코드에 대 한 ANSI 코드 페이지에 대 한 CP_ACP)에 대 한 코드 페이지입니다.  
  
### <a name="return-value"></a>반환 값  
 문자 또는 edit 컨트롤의 바이트 수입니다. 호환 되지 않는 플래그 설정 된 경우 `dwFlags`,이 멤버 함수 반환 `E_INVALIDARG`합니다.  
  
### <a name="remarks"></a>주의  
 `GetTextLengthEx`텍스트의 길이 결정 하는 추가 방법을 제공 합니다. 서식 있는 편집 2.0 기능을 지원합니다. 참조 [서식 있는 편집 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb787873) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]자세한 내용은 합니다.  
  
##  <a name="gettextmode"></a>CRichEditCtrl::GetTextMode  
 Rich edit 컨트롤의 현재 텍스트 모드와 실행 취소 수준을 검색합니다.  
  
```  
UINT GetTextMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 집합의 비트 플래그는 [TEXTMODE](http://msdn.microsoft.com/library/windows/desktop/bb774364) 열거형 형식에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 플래그는 현재 텍스트 모드를 나타내며 컨트롤 수준 실행 취소 합니다.  
  
##  <a name="gettextrange"></a>CRichEditCtrl::GetTextRange  
 지정 된 범위의 문자를 가져옵니다.  
  
```  
int GetTextRange(
    int nFirst,  
    int nLast,  
    CString& refString) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nFirst`  
 범위의 첫 번째 문자 바로 앞의 문자 위치 인덱스입니다.  
  
 `nLast`  
 범위에서 마지막 문자 바로 다음의 문자 위치입니다.  
  
 `refString`  
 에 대 한 참조는 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 텍스트를 받게 될 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 Null 종결 문자를 포함 하지 않고 복사 된 문자 수입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [EM_GETTEXTRANGE](http://msdn.microsoft.com/library/windows/desktop/bb774199) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `GetTextRange`서식 있는 편집 2.0 기능을 지원합니다. 참조 [서식 있는 편집 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb787873) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]자세한 내용은 합니다.  
  
##  <a name="getundoname"></a>CRichEditCtrl::GetUndoName  
 있는 경우 실행 취소 큐에 다음 사용 가능한 동작의 유형을 검색 합니다.  
  
```  
UNDONAMEID GetUndoName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 실행 취소 작업은 컨트롤의 실행 취소 큐에 있는 경우 `GetUndoName` 반환 된 [UNDONAMEID](http://msdn.microsoft.com/library/windows/desktop/bb774365) 큐에서 다음 작업의 형식을 나타내는 열거형입니다. 실행 취소 대기열이 비어 있으면 또는 큐의 실행 취소 동작을 알 수 없는 유형의 경우 `GetUndoName` 0을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 실행 취소 하거나 다시 실행할 수 있는 작업의 종류에는 입력, 삭제, 끌어서 놓기, 잘라내기 및 붙여넣기 작업. 이 정보는 실행 취소할 수 있는 작업의 드롭다운 목록 상자와 같은 실행 취소 및 다시 실행 작업에 대 한 확장된 된 사용자 인터페이스를 제공 하는 응용 프로그램에 유용할 수 있습니다.  
  
##  <a name="getwordwrapmode"></a>CRichEditCtrl::GetWordWrapMode  
 현재 줄 바꿈 및 단어 분리 옵션 rich edit 컨트롤을 검색합니다.  
  
```  
UINT GetWordWrapMode() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 줄 바꿈 및 단어 분리 옵션입니다. 이러한 옵션에 설명 되어 [EM_SETWORDWRAPMODE](http://msdn.microsoft.com/library/windows/desktop/bb774294) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 아시아 언어 버전의 운영 체제에만 사용할 수 있습니다.  
  
##  <a name="hideselection"></a>CRichEditCtrl::HideSelection  
 선택 항목의 표시 유형을 변경합니다.  
  
```  
void HideSelection(
    BOOL bHide,  
    BOOL bPerm);
```  
  
### <a name="parameters"></a>매개 변수  
 `bHide`  
 선택 영역을 표시 하거나 숨길 경우 나타냅니다 **TRUE** 를 숨기려면 선택 합니다.  
  
 `bPerm`  
 선택 영역에 대 한 표시 유형이 변경 영구 되어야 나타냅니다.  
  
### <a name="remarks"></a>주의  
 때 `bPerm` 는 **TRUE**, 변경의 `ECO_NOHIDESEL` 이 대 한 옵션 `CRichEditCtrl` 개체입니다. 이 옵션의 간략 한 설명을 참조 하십시오. [SetOptions](#setoptions)합니다. 이 함수를 사용 하 여이 대 한 모든 옵션을 설정 하려면 `CRichEditCtrl` 개체입니다.  
  
 자세한 내용은 참조 [EM_HIDESELECTION](http://msdn.microsoft.com/library/windows/desktop/bb774210) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&18;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_18.cpp)]  
  
##  <a name="limittext"></a>CRichEditCtrl::LimitText  
 편집 컨트롤에 입력할 수 있는 텍스트의 길이 제한 합니다.  
  
```  
void LimitText(long nChars = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `nChars`  
 길이 (바이트)를 입력할 수 있는 텍스트를 지정 합니다. 이 매개 변수 0 (기본값) 이면 텍스트 길이 64, 000 바이트로 설정 됩니다.  
  
### <a name="remarks"></a>주의  
 입력할 수 있는 텍스트에만 제한 텍스트 제한을 변경 합니다. 편집 컨트롤에 이미 모든 텍스트에 영향을 주지 것도 복사 하 여 편집 컨트롤에 텍스트의 길이 영향을 주지는 [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) 멤버 함수에 `CWnd`합니다. 응용 프로그램을 사용 하는 경우는 `SetWindowText` 함수에 대 한 호출에서 지정 된 편집 컨트롤에 많은 텍스트를 배치할 `LimitText`, 사용자에 편집 컨트롤에서 텍스트를 삭제할 수 있습니다. 그러나 텍스트 제한 사용자는 새 텍스트도 기존 텍스트를 대체 하면, 현재 선택 영역을 삭제 하지 않는 한 하면 텍스트 제한 이하로 텍스트.  
  
> [!NOTE]
>  문자 제한에 대 한 각 OLE 항목을 단일 문자로 계산합니다.  
  
 자세한 내용은 참조 [EM_EXLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb788003) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&19;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_19.cpp)]  
  
##  <a name="linefromchar"></a>CRichEditCtrl::LineFromChar  
 지정된 된 문자 인덱스를 포함 하는 줄의 줄 번호를 검색 합니다.  
  
```  
long LineFromChar(long nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 편집 컨트롤의 텍스트에 원하는 문자에 대 한 인덱스 값을 포함 하거나-1을 포함 합니다. 경우 `nIndex` 은-1, 캐럿을 포함 하는 줄 즉, 현재 줄을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 문자 인덱스를 포함 하는 줄의&0;부터 시작 줄 번호 `nIndex`합니다. 경우 `nIndex` –&1;이 선택의 첫 번째 문자를 포함 하는 줄의 수가 반환 됩니다. 영역이 없는 경우 현재 줄 번호 반환 됩니다.  
  
### <a name="remarks"></a>주의  
 문자 인덱스가부터 rich edit 컨트롤의 문자 수입니다. 문자 계산 된 OLE 항목을 단일 문자로 계산 됩니다.  
  
 자세한 내용은 참조 [EM_EXLINEFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb788005) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&20;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_20.cpp)]  
  
##  <a name="lineindex"></a>CRichEditCtrl::LineIndex  
 이 줄의 문자 인덱스를 검색 `CRichEditCtrl` 개체입니다.  
  
```  
int LineIndex(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nLine`  
 원하는 줄 편집 컨트롤의 텍스트에 대 한 인덱스 값을 포함 하거나-1을 포함 합니다. 경우 `nLine` 은-1, 캐럿을 포함 하는 줄 즉, 현재 줄을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 에 지정 된 줄의 문자 인덱스 `nLine` 하거나 지정한 줄 번호 큰 경우-1 다음 편집 컨트롤의 줄 수 있습니다.  
  
### <a name="remarks"></a>주의  
 문자 인덱스가 지정된 된 줄에 서식 있는 편집 컨트롤의 시작 부분에서 문자 수입니다.  
  
 자세한 내용은 참조 [EM_LINEINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761611) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&21;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_21.cpp)]  
  
##  <a name="linelength"></a>CRichEditCtrl::LineLength  
 Rich edit 컨트롤에서 줄 길이 검색 합니다.  
  
```  
int LineLength(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nLine`  
 검색할 길이가 줄의 문자는 문자 인덱스를 지정 합니다. 이 매개 변수가-1 인 경우 문자열의 길이 포함 하지 않고 선택한 텍스트의 줄 내에서 현재 줄 (캐럿을 포함 하는 줄)의 길이가 반환 됩니다. 때 `LineLength` 라고 한 줄 편집 컨트롤의 경우이 매개 변수가 무시 됩니다.  
  
### <a name="return-value"></a>반환 값  
 때 `LineLength` 라고는 여러 줄 편집 컨트롤에 대 한 반환 값은 길이 (바이트)로 지정 된 줄의 `nLine`합니다. 때 `LineLength` 호출 되는 한 줄 편집 컨트롤에 대 한 반환 값은 길이 (바이트) 편집 컨트롤의 텍스트입니다.  
  
### <a name="remarks"></a>주의  
 사용 된 [LineIndex](#lineindex) 이 내의 지정 된 줄 번호에 대 한 문자 인덱스를 검색 하려면 멤버 함수 `CRichEditCtrl` 개체입니다.  
  
 자세한 내용은 참조 [EM_LINELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb761613) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [LineIndex](#lineindex)합니다.  
  
##  <a name="linescroll"></a>CRichEditCtrl::LineScroll  
 여러 줄 편집 컨트롤의 텍스트가 스크롤됩니다.  
  
```  
void LineScroll(
    int nLines,  
    int nChars = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `nLines`  
 세로로 스크롤할 줄 수를 지정 합니다.  
  
 `nChars`  
 가 가로로 스크롤하도록 문자 위치의 수를 지정 합니다. Rich edit 컨트롤 중 하나에 있으면이 값은 무시 됩니다는 **ES_RIGHT** 또는 **ES_CENTER** 스타일입니다. [편집 스타일](../../mfc/reference/edit-styles.md) 에 지정 된 [만들기](#create)합니다.  
  
### <a name="remarks"></a>주의  
 편집 컨트롤에서 텍스트의 마지막 줄을 지 나 편집 컨트롤이 세로로 스크롤되지 않습니다. 현재 줄에 지정 된 줄 수를 더한 경우 `nLines` 편집 컨트롤에 있는 줄의 총 수를 초과 하면, edit 컨트롤의 마지막 줄 편집 컨트롤 창의 위쪽 스크롤할 수 있도록 조정 되는 값입니다.  
  
 `LineScroll`모든 줄의 마지막 문자를 가로로 넘어가면를 사용할 수 있습니다.  
  
 자세한 내용은 참조 [EM_LINESCROLL](http://msdn.microsoft.com/library/windows/desktop/bb761615) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [GetFirstVisibleLine](#getfirstvisibleline)합니다.  
  
##  <a name="paste"></a>CRichEditCtrl::Paste  
 클립보드에 데이터를 삽입은 `CRichEditCtrl` 삽입 지점에 표시 되는 캐럿의 위치입니다.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>주의  
 데이터가는 클립보드 형식 인식할된에 데이터를 포함 하는 경우에 삽입 됩니다.  
  
 자세한 내용은 참조 [WM_PASTE](http://msdn.microsoft.com/library/windows/desktop/ms649028) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&22;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_22.cpp)]  
  
##  <a name="pastespecial"></a>CRichEditCtrl::PasteSpecial  
 특정 클립보드 형식을이 데이터를 붙여 넣습니다 `CRichEditCtrl` 개체입니다.  
  
```  
void PasteSpecial(
    UINT nClipFormat,  
    DWORD dvAspect = 0,  
    HMETAFILE hMF = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 *nClipFormat*  
 이 붙여 클립보드 형식을 `CRichEditCtrl` 개체입니다.  
  
 *dvAspect*  
 클립보드에서 검색할 데이터에 대 한 장치 측면입니다.  
  
 *hMF*  
 붙여 넣을 개체의 아이콘 뷰를 포함 하 여 메타 파일에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 새로운 자료가 삽입점 캐럿의 위치에 삽입 됩니다.  
  
 자세한 내용은 참조 [EM_PASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/bb774214) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl&23;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_23.cpp)]  
  
##  <a name="posfromchar"></a>CRichEditCtrl::PosFromChar  
 클라이언트 영역 좌표로 편집 컨트롤에서 지정 된 문자를 검색합니다.  
  
```  
CPoint PosFromChar(UINT nChar) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nChar`  
 문자의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 문자, (x, y)의 위치입니다. 한 줄 편집 컨트롤에 대 한 y-좌표는 항상&0;입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="redo"></a>CRichEditCtrl::Redo  
 컨트롤의 다시 실행 큐에서 다음 작업을 다시 실행합니다.  
  
```  
BOOL Redo();
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 자세한 내용은 참조 [EM_REDO](http://msdn.microsoft.com/library/windows/desktop/bb774218) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="replacesel"></a>CRichEditCtrl::ReplaceSel  
 이 현재 선택한 바꿉니다 `CRichEditCtrl` 지정 된 텍스트는 개체입니다.  
  
```  
void ReplaceSel(
    LPCTSTR lpszNewText,  
    BOOL bCanUndo = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszNewText`  
 대체 텍스트를 포함 하는 null로 끝나는 문자열에 대 한 포인터입니다.  
  
 `bCanUndo`  
 이 함수를 실행 취소할 수 있는지를 지정 하려면이 매개 변수의 값을 설정 **TRUE**합니다. 기본값은 **FALSE**합니다.  
  
### <a name="remarks"></a>주의  
 이 모든 텍스트를 바꾸려면 `CRichEditCtrl` 개체를 사용 하 여 [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext)합니다.  
  
 현재 선택 없으면 대체 텍스트 삽입 지점, 즉, 현재 캐럿 위치에 삽입 됩니다.  
  
 이 함수는 기존 문자 서식으로 삽입 된 텍스트를 포맷 합니다. 텍스트의 전체 범위를 바꿀 때 (호출 하 여 `SetSel`(0,-1) 호출 하기 전에 `ReplaceSel`)에 새로 삽입 된 텍스트에 의해 상속 되는 이전 단락 서식 지정을 유지 하는 단락 문자의 끝에 있습니다.  
  
 자세한 내용은 참조 [EM_REPLACESEL](http://msdn.microsoft.com/library/windows/desktop/bb761633) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [LineIndex](#lineindex)합니다.  
  
##  <a name="requestresize"></a>CRichEditCtrl::RequestResize  
 이 강제로 `CRichEditCtrl` 보낼 개체 **EN_REQUESTRESIZE** 알림 메시지를 해당 부모 창입니다.  
  
```  
void RequestResize();
```  
  
### <a name="remarks"></a>주의  
 이 함수는이 옵션이 유용 [CWnd::OnSize](../../mfc/reference/cwnd-class.md#onsize) 는 바닥 없음에 대 한 처리 `CRichEditCtrl` 개체입니다.  
  
 자세한 내용은 참조는 [EM_REQUESTRESIZE](http://msdn.microsoft.com/library/windows/desktop/bb774220) 메시지 및 **바닥 없음 Rich 편집 컨트롤** 섹션 [서식 있는 편집 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb787873) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="setautourldetect"></a>CRichEditCtrl::SetAutoURLDetect  
 Rich edit 컨트롤 URL을 자동으로 검색을 설정 합니다.  
  
```  
BOOL SetAutoURLDetect(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bEnable`  
 컨트롤이 URL을 자동으로 검색 하도록 설정 되어 있는지 여부를 지정 합니다. 경우 **TRUE**, 활성화 됩니다. 경우 **FALSE**, 사용이 불가능 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공적이 고 그렇지 않으면&0;이 아닌 경우&0;입니다. 예를 들어 메시지는 메모리 부족으로 인해 실패할 수 있습니다.  
  
### <a name="remarks"></a>주의  
 설정 된 경우 rich edit 컨트롤은 표준 URL 형식이 일치 하는지 확인 하려면 텍스트를 검사 합니다. 이러한 URL 형식 목록은 참조 하십시오. [EM_AUTOURLDETECT](http://msdn.microsoft.com/library/windows/desktop/bb787991) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
> [!NOTE]
>  설정 하지 마십시오 `SetAutoURLDetect` 를 **TRUE** 편집 컨트롤을 사용 하는 경우는 **CFE_LINK** Url 이외의 텍스트에 적용 합니다. `SetAutoURLDetect`Url에 대 한이 효과 있으며 다른 모든 텍스트에 사용 하지 않도록 설정 합니다. 참조 [EN_LINK](http://msdn.microsoft.com/library/windows/desktop/bb787970) 에 대 한 자세한 내용은 **CFE_LINK** 효과입니다.  
  
##  <a name="setbackgroundcolor"></a>CRichEditCtrl::SetBackgroundColor  
 이 대 한 배경색을 설정 `CRichEditCtrl` 개체입니다.  
  
```  
COLORREF SetBackgroundColor(
    BOOL bSysColor,  
    COLORREF cr);
```  
  
### <a name="parameters"></a>매개 변수  
 `bSysColor`  
 시스템 값을 배경색을 설정 해야 하는 경우를 나타냅니다. 이 값이 **TRUE**, `cr` 는 무시 됩니다.  
  
 `cr`  
 요청 된 배경색입니다. 사용 되는 경우에만 `bSysColor` 는 **FALSE**합니다.  
  
### <a name="return-value"></a>반환 값  
 이 대 한 이전 배경색 `CRichEditCtrl` 개체입니다.  
  
### <a name="remarks"></a>주의  
 시스템 값 또는 지정 된 배경색을 설정할 수 있습니다 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 값입니다.  
  
 자세한 내용은 참조 [EM_SETBKGNDCOLOR](http://msdn.microsoft.com/library/windows/desktop/bb774228) 메시지 및 [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&24;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_24.cpp)]  
  
##  <a name="setdefaultcharformat"></a>CRichEditCtrl::SetDefaultCharFormat  
 이 새 텍스트에 대 한 특성을 형식 지정 문자 설정 `CRichEditCtrl` 개체입니다.  
  
```  
BOOL SetDefaultCharFormat(CHARFORMAT& cf);  
BOOL SetDefaultCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>매개 변수  
 `cf`  
 첫 번째 버전에 대 한 포인터는 [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) 서식 특성 새 기본 문자를 포함 하는 구조입니다.  
  
 두 번째 버전에 대 한 포인터는 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) 구조를 서식 있는 편집 2.0 확장에는 **CHARFORMAT** 서식 특성의 기본 문자를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 로 지정 된 특성에만 **dwMask** 소속 `cf` 이 함수에 의해 변경 됩니다.  
  
 자세한 내용은 참조는 [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) 메시지 및 **CHARFORMAT** 및 **CHARFORMAT2** 구조체에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&25;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_25.cpp)]  
  
##  <a name="seteventmask"></a>CRichEditCtrl::SetEventMask  
 이 대 한 이벤트 마스크 설정 `CRichEditCtrl` 개체입니다.  
  
```  
DWORD SetEventMask(DWORD dwEventMask);
```  
  
### <a name="parameters"></a>매개 변수  
 *dwEventMask*  
 이 대 한 새 이벤트 마스크 `CRichEditCtrl` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 이벤트 마스크입니다.  
  
### <a name="remarks"></a>주의  
 알림 메시지를 지정 하는 이벤트 마스크는 `CRichEditCtrl` 개체를 해당 부모 창에 보냅니다.  
  
 자세한 내용은 참조 [EM_SETEVENTMASK](http://msdn.microsoft.com/library/windows/desktop/bb774238) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&26;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_26.cpp)]  
  
##  <a name="setmodify"></a>CRichEditCtrl::SetModify  
 설정 하거나 편집 컨트롤에 대 한 수정된 된 플래그를 지웁니다.  
  
```  
void SetModify(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bModified`  
 값이 **TRUE** 이면 텍스트 수정 된 값을 **FALSE** 나타냅니다은 변경 되지 않습니다. 수정된 된 플래그는 기본적으로 설정 됩니다.  
  
### <a name="remarks"></a>주의  
 수정된 된 플래그 편집 컨트롤에서 텍스트 수정 되었는지 여부를 나타냅니다. 사용자는 텍스트를 변경할 때마다 자동으로 설정 됩니다. 와 해당 값을 검색할 수는 [GetModify](#getmodify) 멤버 함수입니다.  
  
 자세한 내용은 참조 [EM_SETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761651) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [GetModify](#getmodify)합니다.  
  
##  <a name="setolecallback"></a>CRichEditCtrl::SetOLECallback  
 이 통해 `CRichEditCtrl` 개체는 **IRichEditOleCallback** OLE 관련 리소스 및 정보에 액세스 하는 데는 개체입니다.  
  
```  
BOOL SetOLECallback(IRichEditOleCallback* pCallback);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCallback`  
 에 대 한 포인터는 [IRichEditOleCallback](http://msdn.microsoft.com/library/windows/desktop/bb774308) 개체가이 `CRichEditCtrl` OLE 관련 리소스 및 정보를 가져올 개체를 사용 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 `CRichEditCtrl` 개체를 호출 합니다 [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379) 로 지정 된 COM 개체에 대 한 사용 횟수를 증가 시킬 `pCallback`합니다.  
  
 자세한 내용은 참조 [EM_SETOLECALLBACK](http://msdn.microsoft.com/library/windows/desktop/bb774252) 메시지 및 [IRichEditOleCallback](http://msdn.microsoft.com/library/windows/desktop/bb774308) 인터페이스에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="setoptions"></a>CRichEditCtrl::SetOptions  
 이 옵션을 설정 `CRichEditCtrl` 개체입니다.  
  
```  
void SetOptions(
    WORD wOp,  
    DWORD dwFlags);
```  
  
### <a name="parameters"></a>매개 변수  
 *wOp*  
 작업의 유형을 나타냅니다. 다음 값 중 하나입니다.  
  
- `ECOOP_SET`지정 된 옵션을 설정 `dwFlags`합니다.  
  
- `ECOOP_OR`현재 옵션으로 지정 된 결합 `dwFlags`합니다.  
  
- `ECOOP_AND`또한 지정 된 현재 옵션만 유지 `dwFlags`합니다.  
  
- `ECOOP_XOR`유지 되는 현재 이러한 옵션만 *하지* 에 지정 된 `dwFlags`합니다.  
  
 `dwFlags`  
 풍부한 편집 옵션입니다. 플래그 값은 주의 섹션에 나열 됩니다.  
  
### <a name="remarks"></a>주의  
 옵션은 다음 값의 조합 될 수 있습니다.  
  
- `ECO_AUTOWORDSELECTION`단어 단위로 선택에는 다음 작업을 두 번 클릭 합니다.  
  
- `ECO_AUTOVSCROLL`줄의 끝에 문자를 입력 하는 경우 오른쪽 텍스트를 10 자도 자동 스크롤됩니다. 사용자가 ENTER 키를 누를 때&0;이 위치로 복원 하는 모든 텍스트를 스크롤 하는 컨트롤입니다.  
  
- `ECO_AUTOHSCROLL`마지막 줄에서 ENTER 키를 누를 때 한 페이지 위로 텍스트를 자동으로 스크롤됩니다.  
  
- `ECO_NOHIDESEL`편집 컨트롤에 대 한 기본 동작을 부정합니다. 컨트롤이 입력된 포커스를 잃고 컨트롤이 입력된 포커스를 받을 때 선택한 표시 하는 경우 기본 동작 선택 영역을 숨깁니다. 지정 하는 경우 `ECO_NOHIDESEL`, 컨트롤에 포커스가 없는 경우에 선택한 텍스트 반전 됩니다.  
  
- `ECO_READONLY`사용자를가 입력 하거나 편집 컨트롤의 텍스트를 편집할 수 없습니다.  
  
- `ECO_WANTRETURN`대화 상자에서 여러 줄 rich edit 컨트롤에 텍스트를 입력 하는 동안 사용자가 ENTER 키를 누를 때 캐리지 리턴 삽입할 수를 지정 합니다. 이 스타일을 지정 하지 않으면 ENTER 키를 부모 창 기본 단추 (예를 들어 대화 상자에서 확인 단추)를 클릭 하면 유사 rich edit 컨트롤의 부모 창에 명령을 보냅니다. 이 스타일 편집 컨트롤을 한 줄에 영향을 주지 합니다.  
  
- `ECO_SAVESEL`컨트롤이 포커스를 잃었을 때 선택 항목을 유지 합니다. 기본적으로 포커스를 회복 될 때 컨트롤의 전체 내용은 선택 됩니다.  
  
- `ECO_VERTICAL`세로 방향으로 텍스트 및 개체를 그립니다. 아시아 언어에만 사용할 수 있습니다.  
  
 자세한 내용은 참조 [EM_SETOPTIONS](http://msdn.microsoft.com/library/windows/desktop/bb774254) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&27;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_27.cpp)]  
  
##  <a name="setparaformat"></a>CRichEditCtrl::SetParaFormat  
 단락 형식 지정이 현재 선택 영역에 대 한 특성을 설정 하는 `CRichEditCtrl` 개체입니다.  
  
```  
BOOL SetParaFormat(PARAFORMAT& pf);  
BOOL SetParaFormat(PARAFORMAT2& pf);
```  
  
### <a name="parameters"></a>매개 변수  
 `pf`  
 첫 번째 버전에 대 한 포인터는 [PARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787940) 새 기본값을 포함 하는 구조 단락 서식 특성입니다.  
  
 두 번째 버전에 대 한 포인터는 [PARAFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787942) 서식 있는 편집 2.0 확장인 구조에는 **PARAFORMAT** 구조를 서식 특성의 기본 문자를 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 로 지정 된 특성에만 **dwMask** 소속 `pf` 이 함수에 의해 변경 됩니다.  
  
 자세한 내용은 참조는 [EM_SETPARAFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774276) 메시지 및 **PARAFORMAT** 및 **PARAFORMAT2** 구조체에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&28;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_28.cpp)]  
  
##  <a name="setpunctuation"></a>CRichEditCtrl::SetPunctuation  
 Rich edit 컨트롤에는 문장 부호를 설정합니다.  
  
```  
BOOL SetPunctuation(
    UINT fType,  
    PUNCTUATION* lpPunc);
```  
  
### <a name="parameters"></a>매개 변수  
 `fType`  
 문장 부호 플래그입니다. 가능한 값의 목록에 대 한 참조는 `fType` 에 대 한 매개 변수 [EM_SETPUNCTUATION](http://msdn.microsoft.com/library/windows/desktop/bb774278) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `lpPunc`  
 에 대 한 포인터는 [문장 부호](http://msdn.microsoft.com/library/windows/desktop/bb787944) 구조체에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 운영 체제의 아시아 언어 버전에만 사용할 수 있습니다.  
  
##  <a name="setreadonly"></a>CRichEditCtrl::SetReadOnly  
 변경 된 `ECO_READONLY` 이 대 한 옵션 `CRichEditCtrl` 개체입니다.  
  
```  
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 `bReadOnly`  
 나타냅니다이 `CRichEditCtrl` 개체를 읽기 전용입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 옵션의 간략 한 설명을 참조 하십시오. [SetOptions](#setoptions)합니다. 이 함수를 사용 하 여이 대 한 모든 옵션을 설정 하려면 `CRichEditCtrl` 개체입니다.  
  
 자세한 내용은 참조 [EM_SETREADONLY](http://msdn.microsoft.com/library/windows/desktop/bb761655) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&29;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_29.cpp)]  
  
##  <a name="setrect"></a>CRichEditCtrl::SetRect  
 이 대 한 서식 지정 영역 설정 `CRichEditCtrl` 개체입니다.  
  
```  
void SetRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpRect`  
 [CRect](../../atl-mfc-shared/reference/crect-class.md) 또는에 대 한 포인터는 [RECT](../../mfc/reference/rect-structure1.md) 서식 지정 영역에 대 한 새 경계를 나타내는입니다.  
  
### <a name="remarks"></a>주의  
 서식 지정 사각형에는 텍스트에 대 한 제한 사각형은입니다. 제한 사각형은 서식 있는 편집 컨트롤 창의 크기와 무관 합니다. 때이 `CRichEditCtrl` 개체가 먼저 만들어진, 서식 지정 영역 창의 클라이언트 영역으로 동일한 크기입니다. 사용 하 여 `SetRect` 서식 있는 편집 창 보다 작거나 클 서식 지정 영역 수 있도록 합니다.  
  
 자세한 내용은 참조 [EM_SETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761657) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&30;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_30.cpp)]  
  
##  <a name="setsel"></a>CRichEditCtrl::SetSel  
 이 선택 설정 `CRichEditCtrl` 개체입니다.  
  
```  
void SetSel(
    long nStartChar,  
    long nEndChar);  
  
void SetSel(CHARRANGE& cr);
```  
  
### <a name="parameters"></a>매개 변수  
 `nStartChar`  
 선택 영역에 대 한 첫 번째 문자의&0;부터 시작 인덱스입니다.  
  
 `nEndChar`  
 선택 영역에 대 한 마지막 문자의&0;부터 시작 인덱스입니다.  
  
 `cr`  
 [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) 현재 선택 항목의 범위를 보유 하는 구조입니다.  
  
### <a name="remarks"></a>주의  
 이 함수는 두 가지 형태의 선택 영역에 대 한 범위를 설정 하는 다른 방법을 제공 합니다. 이 폼의 간략 한 설명을 따르십시오.  
  
- **SetSel (** `cr` **)** 이 폼에서 사용 하는 **CHARRANGE** 구조체를 해당 **cpMin** 및 **cpMax** 멤버 범위를 설정 합니다.  
  
- **SetSel (** `nStartChar` **,** `nEndChar` **)** 매개 변수를 사용 하는이 양식을 `nStartChar` 및 `nEndChar` 범위를 설정 합니다.  
  
 시작 중 더 큰로 표시 된 선택 항목의 끝에 캐럿 배치 됩니다 ( **cpMin** 또는 `nStartChar`) 및 end ( **cpMax** 또는 `nEndChar`) 인덱스입니다. 내용을이 함수는 `CRichEditCtrl` 캐럿이 표시 되도록 합니다.  
  
 이 모든 텍스트를 선택 하려면 `CRichEditCtrl` 개체, 호출 `SetSel` 0과-1의 최종 인덱스의 시작 인덱스입니다.  
  
 자세한 내용은 참조 [EM_EXSETSEL](http://msdn.microsoft.com/library/windows/desktop/bb788007) 메시지 및 [CHARRANGE](http://msdn.microsoft.com/library/windows/desktop/bb787885) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [GetSel](#getsel)합니다.  
  
##  <a name="setselectioncharformat"></a>CRichEditCtrl::SetSelectionCharFormat  
 이 현재 선택한 항목의 텍스트에 대 한 특성을 형식 지정 문자 설정 `CRichEditCtrl` 개체입니다.  
  
```  
BOOL SetSelectionCharFormat(CHARFORMAT& cf);  
BOOL SetSelectionCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>매개 변수  
 `cf`  
 첫 번째 버전에 대 한 포인터는 [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) 현재 선택 영역에 대 한 특성을 새 문자 서식을 포함 하는 구조입니다.  
  
 두 번째 버전에 대 한 포인터는 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) 구조를 서식 있는 편집 2.0 확장에는 **CHARFORMAT** 서식 특성 현재 선택 영역을 새 문자를 포함 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 로 지정 된 특성에만 **dwMask** 소속 `cf` 이 함수에 의해 변경 됩니다.  
  
 자세한 내용은 참조는 [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) 및 **CHARFORMAT** 및 **CHARFORMAT2** 구조체에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&31;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_31.cpp)]  
  
##  <a name="settargetdevice"></a>CRichEditCtrl::SetTargetDevice  
 WYSIWYG에 사용 되는 대상 장치 및 선 두께 설정 (표시 되는 가져온 것)이 서식 `CRichEditCtrl` 개체입니다.  
  
```  
BOOL SetTargetDevice(
    HDC hDC,  
    long lLineWidth);

 
BOOL SetTargetDevice(
    CDC& dc,  
    long lLineWidth);
```  
  
### <a name="parameters"></a>매개 변수  
 `hDC`  
 새 대상 장치에 대 한 장치 컨텍스트 핸들입니다.  
  
 *lLineWidth*  
 서식 지정에 사용할 선 두께입니다.  
  
 `dc`  
 [CDC](../../mfc/reference/cdc-class.md) 새 대상 장치에 대 한 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 Rich edit 컨트롤 장치를 소유한이 함수에 성공한 경우 컨텍스트 매개 변수로 전달 합니다. 이 경우 호출 하는 함수는 장치 컨텍스트를 삭제 해서는 안 합니다.  
  
 자세한 내용은 참조 [EM_SETTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/bb774282) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&32;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_32.cpp)]  
  
##  <a name="settextmode"></a>CRichEditCtrl::SetTextMode  
 Rich edit 컨트롤에 대 한 텍스트 모드 또는 실행 취소 및 다시 실행 수준을 설정합니다.  
  
```  
BOOL SetTextMode(UINT fMode);
```  
  
### <a name="parameters"></a>매개 변수  
 *fMode*  
 컨트롤의 텍스트 모드와 실행 취소 수준 매개 변수에 대 한 새 설정을 지정합니다. 목록이 가능한 값에 대 한 mode 매개 변수를 참조 하십시오. [EM_SETTEXTMODE](http://msdn.microsoft.com/library/windows/desktop/bb774286) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 성공적이 고 그렇지 않으면&0;이 아닌 경우&0;입니다.  
  
### <a name="remarks"></a>주의  
 텍스트 모드에 대 한 참조 **EM_SETTEXTMODE** 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 이 멤버 함수에는 컨트롤에 텍스트를 포함 하는 경우 실패 합니다. 컨트롤이 비어 있는지를 보내기는 [WM_SETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632644) 메시지는 빈 문자열입니다.  
  
##  <a name="setundolimit"></a>CRichEditCtrl::SetUndoLimit  
 실행 취소 큐에 저장할 수 있는 작업의 최대 수를 설정 합니다.  
  
```  
UINT SetUndoLimit(UINT nLimit);
```  
  
### <a name="parameters"></a>매개 변수  
 *nLimit*  
 실행 취소 큐에 저장할 수 있는 작업의 최대 수를 지정 합니다. 실행 취소 하지 않으려면&0;으로 설정 합니다.  
  
### <a name="return-value"></a>반환 값  
 컨트롤을 편집 하는 풍부한에 대 한 실행 취소 작업의 새 최대 수입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로, 실행 취소 대기열에 있는 동작의 최대 수는 100입니다. 이 값을 늘리면 새 번호를 수용 하기 위해 사용할 수 있는 메모리가 부족 하 여야 합니다. 성능 향상을 위해 제한을 가능한 가장 작은 값을 설정 합니다.  
  
##  <a name="setwordcharformat"></a>CRichEditCtrl::SetWordCharFormat  
 이 현재 선택 된 단어에 대 한 특성을 형식 지정 문자 설정 `CRichEditCtrl` 개체입니다.  
  
```  
BOOL SetWordCharFormat(CHARFORMAT& cf);  
BOOL SetWordCharFormat(CHARFORMAT2& cf);
```  
  
### <a name="parameters"></a>매개 변수  
 `cf`  
 첫 번째 버전에 대 한 포인터는 [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) 현재 선택 된 단어에 대 한 특성을 새 문자 서식을 포함 하는 구조입니다.  
  
 두 번째 버전에 대 한 포인터는 [CHARFORMAT2](http://msdn.microsoft.com/library/windows/desktop/bb787883) 서식 있는 편집 2.0 확장인 구조에는 **CHARFORMAT** 새 서식 특성을 현재 선택 된 단어 문자를 포함 하는 구조를 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아니고 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 로 지정 된 특성에만 **dwMask** 소속 `cf` 이 함수에 의해 변경 됩니다.  
  
 자세한 내용은 참조는 [EM_SETCHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb774230) 메시지 및 **CHARFORMAT** 및 **CHARFORMAT2** 구조체에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&33;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_33.cpp)]  
  
##  <a name="setwordwrapmode"></a>CRichEditCtrl::SetWordWrapMode  
 컨트롤을 편집 하는 풍부한에 대 한 자동 줄 바꿈 및 단어 분리 옵션을 설정 합니다.  
  
```  
UINT SetWordWrapMode(UINT uFlags) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `uFlags`  
 자동 줄 바꿈 및 단어 분리에 대 한 설정 하는 옵션입니다. 목록이 사용 가능한 옵션에 대 한 참조 [EM_SETWORDWRAPMODE](http://msdn.microsoft.com/library/windows/desktop/bb774294) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="return-value"></a>반환 값  
 현재 자동 줄 바꿈 및 단어 분리 옵션입니다.  
  
### <a name="remarks"></a>주의  
 이 메시지는 아시아 언어 버전의 운영 체제 에서만 사용할 수 있습니다.  
  
##  <a name="stopgrouptyping"></a>CRichEditCtrl::StopGroupTyping  
 컨트롤에서 수집 현재 실행 취소 작업에 작업을 입력 하 고 추가 중지 합니다.  
  
```  
void StopGroupTyping();
```  
  
### <a name="remarks"></a>주의  
 컨트롤 실행 취소 큐에서 새 작업에 있는 경우 다음 입력 작업을 저장 합니다.  
  
 자세한 내용은 참조 [EM_STOPGROUPTYPING](http://msdn.microsoft.com/library/windows/desktop/bb774300) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="streamin"></a>CRichEditCtrl::StreamIn  
 이 항목의 텍스트를 바꿉니다 `CRichEditCtrl` 텍스트 지정 된 입력 스트림에서 지정 된 개체입니다.  
  
```  
long StreamIn(
    int nFormat,  
    EDITSTREAM& es);
```  
  
### <a name="parameters"></a>매개 변수  
 `nFormat`  
 입력된 데이터 형식을 지정 하는 플래그입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
 `es`  
 [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) 입력된 스트림을 지정 하는 구조입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
### <a name="return-value"></a>반환 값  
 입력 스트림에서 읽은 문자 수입니다.  
  
### <a name="remarks"></a>주의  
 값 `nFormat` 다음 중 하나 여야 합니다.  
  
- `SF_TEXT`텍스트를 읽는을 나타냅니다.  
  
- `SF_RTF`읽는 텍스트 및 서식 지정을 나타냅니다.  
  
 이러한 값 중 하나 결합할 수 `SFF_SELECTION`합니다. 경우 `SFF_SELECTION` 지정 `StreamIn` 입력 스트림의 내용을 현재 선택 영역을 바꿉니다. 지정 하지 않으면 `StreamIn` 이의 전체 내용을 대체 `CRichEditCtrl` 개체입니다.  
  
 에 **EDITSTREAM** 매개 변수 `es`, 텍스트와 버퍼를 구성 하는 콜백 함수를 지정 합니다. 이 콜백 함수는 입력된 스트림의 가득 찰 때까지 반복적으로 호출 됩니다.  
  
 자세한 내용은 참조 [EM_STREAMIN](http://msdn.microsoft.com/library/windows/desktop/bb774302) 메시지 및 [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&34;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_34.cpp)]  
  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&35;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_35.cpp)]  
  
##  <a name="streamout"></a>CRichEditCtrl::StreamOut  
 이 작업의 콘텐츠를 작성 `CRichEditCtrl` 지정 된 출력 스트림에 개체입니다.  
  
```  
long StreamOut(
    int nFormat,  
    EDITSTREAM& es);
```  
  
### <a name="parameters"></a>매개 변수  
 `nFormat`  
 출력 데이터 형식을 지정 하는 플래그입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
 `es`  
 [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) 출력 스트림에 지정 하는 구조입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
### <a name="return-value"></a>반환 값  
 출력 스트림에 쓸 문자 수입니다.  
  
### <a name="remarks"></a>주의  
 값 `nFormat` 다음 중 하나 여야 합니다.  
  
- `SF_TEXT`쓰기 텍스트만을 나타냅니다.  
  
- `SF_RTF`작성할 텍스트 및 서식 지정을 나타냅니다.  
  
- `SF_RTFNOOBJS`나타냅니다 쓰기 텍스트 및 서식, 공백을 사용 하 여 OLE 항목을 바꿉니다.  
  
- `SF_TEXTIZED`쓰기 텍스트 및 서식, OLE 항목의 텍스트 표현을 나타냅니다.  
  
 이러한 값을 결합할 수 `SFF_SELECTION`합니다. 경우 `SFF_SELECTION` 지정 `StreamOut` 현재 선택 영역을 출력 스트림에 씁니다. 지정 하지 않으면 `StreamOut` 이 작업의 전체 내용을 씁니다 `CRichEditCtrl` 개체입니다.  
  
 에 **EDITSTREAM** 매개 변수 `es`, 텍스트 버퍼를 채웁니다 되는 콜백 함수를 지정 합니다. 이 콜백 함수는 출력 스트림에 가득 찰 때까지 반복적으로 호출 됩니다.  
  
 자세한 내용은 참조 [EM_STREAMOUT](http://msdn.microsoft.com/library/windows/desktop/bb774304) 메시지 및 [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891) 구조에서 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&36;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_36.cpp)]  
  
 [!code-cpp[NVC_MFC_CRichEditCtrl #&37;](../../mfc/reference/codesnippet/cpp/cricheditctrl-class_37.cpp)]  
  
##  <a name="undo"></a>CRichEditCtrl::Undo  
 Rich edit 컨트롤의 마지막 작업 실행 취소합니다.  
  
```  
BOOL Undo();
```  
  
### <a name="return-value"></a>반환 값  
 실행 취소 작업에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 실행 취소 작업 또한 취소할 수 없습니다. 예를 들어 첫 번째 호출 하 여 삭제 된 텍스트를 복원할 수 있습니다 **취소**합니다. 텍스트에 대 한 두 번째 호출을 사용 하 여 다시 중간 편집 작업이 없는으로 제거할 수 있습니다 **취소**합니다.  
  
 자세한 내용은 참조 [EM_UNDO](http://msdn.microsoft.com/library/windows/desktop/bb761670) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CanUndo](#canundo)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 워드 패드](../../visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CEdit 클래스](../../mfc/reference/cedit-class.md)   
 [CRichEditView 클래스](../../mfc/reference/cricheditview-class.md)

