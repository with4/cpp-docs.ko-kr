---
title: "CComboBox 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComboBox
- AFXWIN/CComboBox
- AFXWIN/CComboBox::CComboBox
- AFXWIN/CComboBox::AddString
- AFXWIN/CComboBox::Clear
- AFXWIN/CComboBox::CompareItem
- AFXWIN/CComboBox::Copy
- AFXWIN/CComboBox::Create
- AFXWIN/CComboBox::Cut
- AFXWIN/CComboBox::DeleteItem
- AFXWIN/CComboBox::DeleteString
- AFXWIN/CComboBox::Dir
- AFXWIN/CComboBox::DrawItem
- AFXWIN/CComboBox::FindString
- AFXWIN/CComboBox::FindStringExact
- AFXWIN/CComboBox::GetComboBoxInfo
- AFXWIN/CComboBox::GetCount
- AFXWIN/CComboBox::GetCueBanner
- AFXWIN/CComboBox::GetCurSel
- AFXWIN/CComboBox::GetDroppedControlRect
- AFXWIN/CComboBox::GetDroppedState
- AFXWIN/CComboBox::GetDroppedWidth
- AFXWIN/CComboBox::GetEditSel
- AFXWIN/CComboBox::GetExtendedUI
- AFXWIN/CComboBox::GetHorizontalExtent
- AFXWIN/CComboBox::GetItemData
- AFXWIN/CComboBox::GetItemDataPtr
- AFXWIN/CComboBox::GetItemHeight
- AFXWIN/CComboBox::GetLBText
- AFXWIN/CComboBox::GetLBTextLen
- AFXWIN/CComboBox::GetLocale
- AFXWIN/CComboBox::GetMinVisible
- AFXWIN/CComboBox::GetTopIndex
- AFXWIN/CComboBox::InitStorage
- AFXWIN/CComboBox::InsertString
- AFXWIN/CComboBox::LimitText
- AFXWIN/CComboBox::MeasureItem
- AFXWIN/CComboBox::Paste
- AFXWIN/CComboBox::ResetContent
- AFXWIN/CComboBox::SelectString
- AFXWIN/CComboBox::SetCueBanner
- AFXWIN/CComboBox::SetCurSel
- AFXWIN/CComboBox::SetDroppedWidth
- AFXWIN/CComboBox::SetEditSel
- AFXWIN/CComboBox::SetExtendedUI
- AFXWIN/CComboBox::SetHorizontalExtent
- AFXWIN/CComboBox::SetItemData
- AFXWIN/CComboBox::SetItemDataPtr
- AFXWIN/CComboBox::SetItemHeight
- AFXWIN/CComboBox::SetLocale
- AFXWIN/CComboBox::SetMinVisibleItems
- AFXWIN/CComboBox::SetTopIndex
- AFXWIN/CComboBox::ShowDropDown
dev_langs:
- C++
helpviewer_keywords:
- CComboBox [MFC], CComboBox
- CComboBox [MFC], AddString
- CComboBox [MFC], Clear
- CComboBox [MFC], CompareItem
- CComboBox [MFC], Copy
- CComboBox [MFC], Create
- CComboBox [MFC], Cut
- CComboBox [MFC], DeleteItem
- CComboBox [MFC], DeleteString
- CComboBox [MFC], Dir
- CComboBox [MFC], DrawItem
- CComboBox [MFC], FindString
- CComboBox [MFC], FindStringExact
- CComboBox [MFC], GetComboBoxInfo
- CComboBox [MFC], GetCount
- CComboBox [MFC], GetCueBanner
- CComboBox [MFC], GetCurSel
- CComboBox [MFC], GetDroppedControlRect
- CComboBox [MFC], GetDroppedState
- CComboBox [MFC], GetDroppedWidth
- CComboBox [MFC], GetEditSel
- CComboBox [MFC], GetExtendedUI
- CComboBox [MFC], GetHorizontalExtent
- CComboBox [MFC], GetItemData
- CComboBox [MFC], GetItemDataPtr
- CComboBox [MFC], GetItemHeight
- CComboBox [MFC], GetLBText
- CComboBox [MFC], GetLBTextLen
- CComboBox [MFC], GetLocale
- CComboBox [MFC], GetMinVisible
- CComboBox [MFC], GetTopIndex
- CComboBox [MFC], InitStorage
- CComboBox [MFC], InsertString
- CComboBox [MFC], LimitText
- CComboBox [MFC], MeasureItem
- CComboBox [MFC], Paste
- CComboBox [MFC], ResetContent
- CComboBox [MFC], SelectString
- CComboBox [MFC], SetCueBanner
- CComboBox [MFC], SetCurSel
- CComboBox [MFC], SetDroppedWidth
- CComboBox [MFC], SetEditSel
- CComboBox [MFC], SetExtendedUI
- CComboBox [MFC], SetHorizontalExtent
- CComboBox [MFC], SetItemData
- CComboBox [MFC], SetItemDataPtr
- CComboBox [MFC], SetItemHeight
- CComboBox [MFC], SetLocale
- CComboBox [MFC], SetMinVisibleItems
- CComboBox [MFC], SetTopIndex
- CComboBox [MFC], ShowDropDown
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fffa5c09f1572200ca7850c8870b7daee9e3e75f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ccombobox-class"></a>CComboBox 클래스
Windows 콤보 상자의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CComboBox : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComboBox::CComboBox](#ccombobox)|`CComboBox` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Ccombobox:: Addstring](#addstring)|콤보 상자의 또는으로 목록 상자에 대 한 정렬된 위치에 있는 목록 상자에서 목록 끝에 문자열을 추가 **CBS_SORT** 스타일입니다.|  
|[CComboBox::Clear](#clear)|삭제 (취소) 편집 컨트롤에 있는 경우 현재 선택 합니다.|  
|[CComboBox::CompareItem](#compareitem)|정렬 된 소유자가 그린 콤보 상자에 새 목록 항목의 상대 위치를 결정 하기 위해 프레임 워크에서 호출 됩니다.|  
|[CComboBox::Copy](#copy)|클립보드에 있는 경우 현재 선택 영역 복사 **CF_TEXT** 형식입니다.|  
|[CComboBox::Create](#create)|콤보 상자를 만들고 연결 하는 `CComboBox` 개체입니다.|  
|[CComboBox::Cut](#cut)|삭제 (컷) 제어 하 고 삭제 된 텍스트에서 클립보드에 복사 하 고 편집의 경우 현재 선택 **CF_TEXT** 형식입니다.|  
|[CComboBox::DeleteItem](#deleteitem)|목록 항목 소유자가 그린 콤보 상자에서 삭제 될 때 프레임 워크에서 호출 됩니다.|  
|[CComboBox::DeleteString](#deletestring)|콤보 상자의 목록 상자에서 문자열을 삭제합니다.|  
|[CComboBox::Dir](#dir)|콤보 상자의 목록 상자에 파일 이름 목록이 추가합니다.|  
|[CComboBox::DrawItem](#drawitem)|소유자가 그린 콤보 상자 변경의 시각적 측면이 때 프레임 워크에서 호출 됩니다.|  
|[CComboBox::FindString](#findstring)|콤보 상자의 목록 상자에서 지정된 된 접두사를 포함 하는 첫 번째 문자열을 찾습니다.|  
|[CComboBox::FindStringExact](#findstringexact)|콤보 상자) (에서 지정된 된 문자열과 일치 하는 첫 번째 목록 상자 문자열을 찾습니다.|  
|[CComboBox::GetComboBoxInfo](#getcomboboxinfo)|에 대 한 정보를 검색 합니다.는 `CComboBox` 개체입니다.|  
|[CComboBox::GetCount](#getcount)|콤보 상자의 목록 상자에 있는 항목의 수를 검색 합니다.|  
|[CComboBox::GetCueBanner](#getcuebanner)|콤보 상자 컨트롤에 대해 표시 되는 큐 텍스트를 가져옵니다.|  
|[CComboBox::GetCurSel](#getcursel)|콤보 상자의 목록 상자에 있는 경우에 현재 선택 된 항목의 인덱스를 검색 합니다.|  
|[CComboBox::GetDroppedControlRect](#getdroppedcontrolrect)|드롭다운 콤보 상자의 표시 (다운 삭제) 목록 상자의 화면 좌표를 검색합니다.|  
|[CComboBox::GetDroppedState](#getdroppedstate)|표시 여부를 결정 드롭다운 콤보 상자의 목록 상자 (드롭다운 됨).|  
|[CComboBox::GetDroppedWidth](#getdroppedwidth)|콤보 상자의 드롭다운 목록 상자 부분에 대 한 너비 허용 되는 최소값을 검색 합니다.|  
|[CComboBox::GetEditSel](#geteditsel)|콤보 상자의 편집 컨트롤에 현재 선택 영역의 시작 및 끝 문자 위치를 가져옵니다.|  
|[CComboBox::GetExtendedUI](#getextendedui)|콤보 상자는 기본 사용자 인터페이스 또는 확장 된 사용자 인터페이스에 있는지 여부를 결정 합니다.|  
|[CComboBox::GetHorizontalExtent](#gethorizontalextent)|콤보 상자의 목록 상자 부분 가로로 스크롤할 수 있는 픽셀 너비를 반환 합니다.|  
|[CComboBox::GetItemData](#getitemdata)|지정 된 콤보 상자 항목에 연결 된 응용 프로그램에서 제공 32 비트 값을 검색 합니다.|  
|[CComboBox::GetItemDataPtr](#getitemdataptr)|지정 된 콤보 상자 항목과 연결 된 응용 프로그램에서 제공 32 비트 포인터를 검색 합니다.|  
|[CComboBox::GetItemHeight](#getitemheight)|콤보 상자에 있는 목록 항목의 높이 검색합니다.|  
|[CComboBox::GetLBText](#getlbtext)|콤보 상자의 목록 상자에서 문자열을 가져옵니다.|  
|[CComboBox::GetLBTextLen](#getlbtextlen)|콤보 상자의 목록 상자에는 문자열의 길이 가져옵니다.|  
|[CComboBox::GetLocale](#getlocale)|콤보 상자에 대 한 로캘 식별자를 검색합니다.|  
|[CComboBox::GetMinVisible](#getminvisible)|현재 콤보 상자의 드롭다운 목록에 표시 된 항목의 최소 수를 가져옵니다.|  
|[CComboBox::GetTopIndex](#gettopindex)|콤보 상자의 목록 상자 부분에 표시 되는 첫 번째 항목의 인덱스를 반환합니다.|  
|[CComboBox::InitStorage](#initstorage)|Preallocates 항목과 콤보 상자의 목록 상자 부분 문자열에 대 한 메모리 블록입니다.|  
|[CComboBox::InsertString](#insertstring)|콤보 상자의 목록 상자에 문자열을 삽입합니다.|  
|[CComboBox::LimitText](#limittext)|콤보 상자의 편집 컨트롤에 입력할 수 있는 텍스트의 길이 제한 합니다.|  
|[CComboBox::MeasureItem](#measureitem)|소유자가 그린 콤보 상자를 만들 때 콤보 상자 크기를 결정 하기 위해 프레임 워크에서 호출 됩니다.|  
|[CComboBox::Paste](#paste)|클립보드의 현재 커서 위치에 있는 편집 컨트롤에 데이터를 삽입합니다. 데이터를 클립보드에 데이터를 포함 하는 경우에 삽입 **CF_TEXT** 형식입니다.|  
|[CComboBox::ResetContent](#resetcontent)|목록에서 모든 항목 상자 및 콤보 상자 컨트롤을 편집할를 제거 합니다.|  
|[CComboBox::SelectString](#selectstring)|콤보 상자의 목록 상자에 문자열을 검색 하 고, 문자열이 발견 되는 경우 목록 상자에 문자열을 선택 하 고 편집 컨트롤을 해당 문자열을 복사 합니다.|  
|[CComboBox::SetCueBanner](#setcuebanner)|콤보 상자 컨트롤에 대해 표시 되는 큐 텍스트를 설정 합니다.|  
|[CComboBox::SetCurSel](#setcursel)|콤보 상자의 목록 상자에 문자열을 선택합니다.|  
|[CComboBox::SetDroppedWidth](#setdroppedwidth)|콤보 상자의 드롭다운 목록 상자 부분에 대 한 너비 허용 되는 최소값을 설정 합니다.|  
|[CComboBox::SetEditSel](#seteditsel)|콤보 상자의 편집 컨트롤에 문자를 선택합니다.|  
|[CComboBox::SetExtendedUI](#setextendedui)|선택 하는 기본 사용자 인터페이스 또는 있는 콤보 상자에 대 한 확장 된 사용자 인터페이스는 **CBS_DROPDOWN** 또는 **CBS_DROPDOWNLIST** 스타일입니다.|  
|[CComboBox::SetHorizontalExtent](#sethorizontalextent)|콤보 상자의 목록 상자 부분 가로로 스크롤할 수 있는 픽셀에서 너비를 설정 합니다.|  
|[CComboBox::SetItemData](#setitemdata)|콤보 상자에 지정 된 항목과 연결 된 32 비트 값을 설정 합니다.|  
|[CComboBox::SetItemDataPtr](#setitemdataptr)|콤보 상자에 지정 된 항목과 연결 된 32 비트 포인터를 설정 합니다.|  
|[CComboBox::SetItemHeight](#setitemheight)|콤보 상자 또는 콤보 상자의 편집 컨트롤 (또는 정적 텍스트) 부분의 높이에 목록 항목의 높이 설정합니다.|  
|[CComboBox::SetLocale](#setlocale)|콤보 상자에 대 한 로캘 식별자를 설정합니다.|  
|[CComboBox::SetMinVisibleItems](#setminvisibleitems)|현재 콤보 상자의 드롭다운 목록에 표시 된 항목의 최소 수를 설정 합니다.|  
|[CComboBox::SetTopIndex](#settopindex)|위쪽에 지정 된 인덱스 항목을 표시 하는 콤보 상자의 목록 상자 부분을 알려 줍니다.|  
|[CComboBox::ShowDropDown](#showdropdown)|표시 하거나 숨깁니다 있는 콤보 상자의 목록 상자는 **CBS_DROPDOWN** 또는 **CBS_DROPDOWNLIST** 스타일입니다.|  
  
## <a name="remarks"></a>설명  
 콤보 상자 목록 상자 정적 컨트롤 또는 편집 컨트롤 조합으로 이루어져 있습니다. 컨트롤의 목록 상자 부분은 항상 표시 될 수 있습니다 또는 수만 드롭다운 사용자가 컨트롤 옆의 드롭다운 화살표를 선택 합니다.  
  
 목록 상자에서 현재 선택 된 항목 (있는 경우)는 정적으로 표시 또는 편집 컨트롤입니다. 또한, 콤보 상자에서 드롭다운 목록에서 스타일을 사용자 목록에서 항목 중 하나의 초기 문자를 입력할 수 및 목록 상자, 표시 되는 경우는 강조 표시 초기 문자가 된 다음 항목입니다.  
  
 다음 표에서 세 가지 콤보 상자 비교 [스타일](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles)합니다.  
  
|스타일|목록 상자 표시 된 경우|정적 또는 편집 컨트롤|  
|-----------|-------------------------------|-----------------------------|  
|단순|Always|편집|  
|Drop-down|삭제 될 때|편집|  
|드롭다운 목록|삭제 될 때|정적|  
  
 만들 수는 `CComboBox` 대화 서식 파일에서 또는 코드에서 직접 개체입니다. 두 경우 모두 먼저 생성자 호출 `CComboBox` 생성 하는 `CComboBox` 호출; 개체는 [만들기](#create) 컨트롤을 만들고에 연결 하는 멤버 함수는 `CComboBox` 개체입니다.  
  
 콤보 상자에서 해당 부모에 보냅니다 Windows 알림 메시지를 처리 하려는 경우 (일반적으로 클래스에서 파생 `CDialog`), 각 메시지에 대 한 부모 클래스에는 메시지 맵 항목 및 메시지 처리기 멤버 함수를 추가 합니다.  
  
 각 메시지 맵 항목은 다음 형식을 사용 합니다.  
  
 **ON_**알림 **(**`id`**,**`memberFxn`**)**  
  
 여기서 `id` 알림을 전송 하는 콤보 상자 컨트롤의 자식 창 ID를 지정 하 고 `memberFxn` 알림을 처리 하도록 작성 한 부모 멤버 함수의 이름입니다.  
  
 부모의 함수 프로토타입에 다음과 같습니다.  
  
 **afx_msg** `void` `memberFxn` **();**  
  
 특정 알림을 보낼 수는 순서를 예측할 수 없습니다. 특히, 한 **CBN_SELCHANGE** 알림 앞 이나 뒤에 발생할 수 있습니다는 **CBN_CLOSEUP** 알림입니다.  
  
 메시지 맵 항목에는 다음과 같습니다.  
  
- **ON_CBN_CLOSEUP** (Windows 3.1 이상.) 콤보 상자의 목록 상자를 종료 했습니다. 에 있는 콤보 상자에 대 한이 알림 메시지를 보내지는 [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일입니다.  
  
- **ON_CBN_DBLCLK** 사용자가 콤보 상자의 목록 상자에 문자열을 두 번 클릭 합니다. 콤보 상자에 대 한이 알림 메시지를 보내는는 **CBS_SIMPLE** 스타일입니다. 콤보 상자에 대 한는 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 또는 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일을 두 번 클릭 올 수 없습니다 한 번의 클릭 목록 상자 므 합니다.  
  
- **ON_CBN_DROPDOWN** 을 드롭다운은 콤보 상자의 목록 상자 (시각화 되어야) 합니다. 이 알림 메시지는 콤보 상자에 대해서만 발생할 수 있습니다는 **CBS_DROPDOWN** 또는 **CBS_DROPDOWNLIST** 스타일입니다.  
  
- **ON_CBN_EDITCHANGE** 사용자가 콤보 상자의 편집 컨트롤 부분에서 텍스트를 변경할 수도 있는 동작을 수행한 합니다. 와 달리는 **CBN_EDITUPDATE** 메시지가 Windows 화면을 업데이트 하 고 나면이 메시지가 표시 됩니다. 콤보 상자에 전송 되지 않습니다는 **CBS_DROPDOWNLIST** 스타일입니다.  
  
- **ON_CBN_EDITUPDATE** 콤보 상자의 편집 컨트롤 부분이 변경 된 텍스트가 표시 되려고 합니다. 이 알림 메시지는 컨트롤의 텍스트의 서식을 지정한 나 텍스트를 표시 하기 전에 전송 됩니다. 콤보 상자에 전송 되지 않습니다는 **CBS_DROPDOWNLIST** 스타일입니다.  
  
- **ON_CBN_ERRSPACE** 콤보 상자에서 특정 요청을 충족 하기 위해 충분 한 메모리를 할당할 수 없습니다.  
  
- **ON_CBN_SELENDCANCEL** (Windows 3.1 이상.) 사용자의 선택을 취소 해야 나타냅니다. 사용자가 항목을 클릭 하 고 다른 창 또는 숨기려면 콤보 상자의 목록 상자 컨트롤을 클릭 합니다. 하기 전에이 알림 메시지를 보내는 **CBN_CLOSEUP** 알림 메시지를 사용자가 선택한 무시 되어야 함을 나타냅니다. **CBN_SELENDCANCEL** 또는 **CBN_SELENDOK** 알림 메시지를 보내는 경우에는 **CBN_CLOSEUP** 알림 메시지가 전송 되지 않습니다 (으로 콤보 상자의 경우로 **CBS_SIMPLE** 스타일).  
  
- **ON_CBN_SELENDOK** 사용자가 항목을 선택 하 고 ENTER 키를 누르거나 하거나 콤보 상자의 목록 상자를 숨기려면 아래쪽 화살표 키를 클릭 합니다. 하기 전에이 알림 메시지를 보내는 **CBN_CLOSEUP** 는 사용자가 선택한 고려할 유효한 나타낼 메시지를 합니다. **CBN_SELENDCANCEL** 또는 **CBN_SELENDOK** 알림 메시지를 보내는 경우에는 **CBN_CLOSEUP** 알림 메시지가 전송 되지 않습니다 (으로 콤보 상자의 경우로 **CBS_SIMPLE** 스타일).  
  
- **ON_CBN_KILLFOCUS** 콤보 상자 입력된 포커스가 손실 됩니다.  
  
- **ON_CBN_SELCHANGE** 콤보 상자의 목록 상자에서 선택 목록 상자에서를 클릭 하거나 화살표 키를 사용 하 여 선택 영역을 변경 하는 사용자 이름이 변경 되려고 합니다. 이 메시지를 처리할 때 콤보 상자의 편집 컨트롤의 텍스트가 통해 검색할 수 있습니다 `GetLBText` 또는 다른 비슷한 함수입니다. `GetWindowText`사용할 수 없습니다.  
  
- **ON_CBN_SETFOCUS** 콤보 상자 입력된 포커스를 받습니다.  
  
 만드는 경우는 `CComboBox` (대화 상자 리소스의 경우) 하 여 대화 상자 내에서 개체는 `CComboBox` 개체는 사용자가 대화 상자를 닫을 때 자동으로 제거 됩니다.  
  
 포함 한 경우는 `CComboBox` 개체 또 다른 창에서 개체를 삭제할 필요가 없습니다. 만드는 경우는 `CComboBox` 개체 스택, 자동으로 삭제 됩니다. 만드는 경우는 `CComboBox` 개체를 사용 하 여 힙에 **새** 함수를 호출한 다음 **삭제** Windows 콤보 상자의 소멸 될 때 destroy 개체에 있습니다.  
  
 **참고** 처리 하려는 경우 `WM_KEYDOWN` 및 `WM_CHAR` 메시지를 있는 하위 클래스를 만들려면 콤보 상자의 편집 하 고 목록 상자 컨트롤, 클래스를 파생 `CEdit` 및 `CListBox`, 파생 해당 메시지에 대 한 처리기를 추가 하 고 클래스입니다. 자세한 내용은 참조 [http://support.microsoft.com/default.aspxscid=kb;en-us; Q174667](http://support.microsoft.com/default.aspxscid=kb;en-us;q174667) 및 [CWnd::SubclassWindow](../../mfc/reference/cwnd-class.md#subclasswindow)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CComboBox`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="addstring"></a>Ccombobox:: Addstring  
 콤보 상자의 목록 상자에 문자열을 추가 합니다.  
  
```  
int AddString(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszString`  
 추가 되도록 하는 null로 끝나는 문자열을 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값은 0 보다 크거나 경우 목록 상자에서 문자열에 0부터 시작 인덱스는 합니다. 반환 값은 **CB_ERR** 오류가 발생 하는 경우 반환 값은 **CB_ERRSPACE** 새 문자열을 저장할 사용 가능한 공간이 부족 한 경우.  
  
### <a name="remarks"></a>설명  
 목록 상자도 생성 되지 않은 경우는 [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일에는 문자열이 목록의 끝에 추가 됩니다. 그렇지 않으면 문자열의 목록에 삽입 됩니다 및 목록이 정렬 됩니다.  
  
> [!NOTE]
>  이 함수는 Windows **ComboBoxEx** 컨트롤에서 지원되지 않습니다. 이 컨트롤에 대 한 자세한 내용은 참조 하십시오. [ComboBoxEx 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb775738) Windows sdk에서입니다.  
  
 사용 하 여 목록 내의 특정 위치에 문자열을 삽입 하려면는 [InsertString](#insertstring) 멤버 함수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#3](../../mfc/reference/codesnippet/cpp/ccombobox-class_1.cpp)]  
  
##  <a name="ccombobox"></a>CComboBox::CComboBox  
 `CComboBox` 개체를 생성합니다.  
  
```  
CComboBox();
```  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_2.cpp)]  
  
##  <a name="clear"></a>CComboBox::Clear  
 삭제 (취소) 콤보 상자의 편집 컨트롤에 있는 경우 현재 선택 합니다.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>설명  
 현재 선택 영역을 삭제 하 고 삭제 된 내용을 클립보드에 배치를 사용는 [잘라내기](#cut) 멤버 함수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#4](../../mfc/reference/codesnippet/cpp/ccombobox-class_3.cpp)]  
  
##  <a name="compareitem"></a>CComboBox::CompareItem  
 정렬 된 소유자 그리기 콤보 상자의 목록 상자 부분에 새 항목의 상대 위치를 결정 하기 위해 프레임 워크에서 호출 됩니다.  
  
```  
virtual int CompareItem(LPCOMPAREITEMSTRUCT lpCompareItemStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpCompareItemStruct`  
 에 대 한 긴 포인터는 [COMPAREITEMSTRUCT](../../mfc/reference/compareitemstruct-structure.md) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 에 설명 된 두 항목의 상대 위치를 나타내는 `COMPAREITEMSTRUCT` 구조입니다. 다음 값 중 하나일 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|- 1|항목 1 항목 2 앞에 정렬 합니다.|  
|0|항목 1 및 2 항목 정렬 동일 합니다.|  
|1|항목 1 항목 2 뒤에 정렬합니다.|  
  
 참조 [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem) 에 대 한 설명은 `COMPAREITEMSTRUCT`합니다.  
  
### <a name="remarks"></a>설명  
 기본적으로이 멤버 함수는 아무 작업도 수행 하지 않습니다. 소유자 그리기 콤보 상자를 사용 하 여를 만들면는 **LBS_SORT** 스타일 목록 상자에 추가 하는 새 항목을 정렬 프레임 워크를 지원 하기 위해이 멤버 함수를 재정의 해야 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#5](../../mfc/reference/codesnippet/cpp/ccombobox-class_4.cpp)]  
  
##  <a name="copy"></a>CComboBox::Copy  
 클립보드에 콤보 상자의 편집 컨트롤에 있는 경우 현재 선택 영역 복사 **CF_TEXT** 형식입니다.  
  
```  
void Copy();
```  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#6](../../mfc/reference/codesnippet/cpp/ccombobox-class_5.cpp)]  
  
##  <a name="create"></a>CComboBox::Create  
 콤보 상자를 만들고 연결 하는 `CComboBox` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 콤보 상자의 스타일을 지정합니다. 어떠한 조합의 적용 [콤보 상자 스타일](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 상자로 합니다.  
  
 `rect`  
 콤보 상자의 크기와 위치를 가리킵니다. 일 수 있습니다는 [RECT 구조체](../../mfc/reference/rect-structure1.md) 또는 `CRect` 개체입니다.  
  
 `pParentWnd`  
 콤보 상자의 부모 창 (일반적으로 `CDialog`). 않아야 **NULL**합니다.  
  
 `nID`  
 콤보 상자 컨트롤 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 생성할는 `CComboBox` 두 단계를 수행에서 하는 개체입니다. 먼저 생성자를 호출 하 고 호출 **만들기**, Windows 콤보 상자의 만들고에 연결 하는 `CComboBox` 개체입니다.  
  
 때 **만들기** 실행 되 면 Windows 보냅니다는 [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), 및 [WM_ GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 콤보 상자에는 메시지입니다.  
  
 기본적으로 이러한 메시지의 처리는 [OnNcCreate](../../mfc/reference/cwnd-class.md#onnccreate), [OnCreate](../../mfc/reference/cwnd-class.md#oncreate), [OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize), 및 [OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo) 멤버 함수 에 `CWnd` 기본 클래스입니다. 기본 메시지 처리를 확장 하려면에서 클래스를 파생 `CComboBox`, 메시지 맵을 새 클래스에 추가 하 고 위의 메시지 처리기 멤버 함수를 재정의 합니다. 재정의 `OnCreate`, 예를 들어 새 클래스에 대 한 필요한 초기화를 수행 하도록 합니다.  
  
 다음 적용 [창 스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 콤보 상자 컨트롤입니다. :  
  
- **WS_CHILD** 항상  
  
- **WS_VISIBLE** 일반적으로  
  
- **WS_DISABLED** 거의  
  
- **WS_VSCROLL** 콤보 상자의 목록 상자에 대 한 세로 스크롤 기능을 추가 하려면  
  
- **WS_HSCROLL** 콤보 상자의 목록 상자에 대 한 가로 스크롤 기능을 추가 하려면  
  
- **WS_GROUP** 컨트롤을 그룹화  
  
- **WS_TABSTOP** 콤보 상자 탭 이동 순서에 포함 하려면  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_6.cpp)]  
  
##  <a name="cut"></a>CComboBox::Cut  
 삭제 (컷) 현재 선택, 콤보 상자에서 편집 하는 경우 제어 하 고 삭제 된 텍스트에서 클립보드에 복사 **CF_TEXT** 형식입니다.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>설명  
 현재 선택 영역을 클립보드에 삭제 된 텍스트를 배치 하지 않고 삭제 하려면 호출는 [지우기](#clear) 멤버 함수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#7](../../mfc/reference/codesnippet/cpp/ccombobox-class_7.cpp)]  
  
##  <a name="deleteitem"></a>CComboBox::DeleteItem  
 사용자는 소유자 그리기에서 항목을 삭제 될 때 프레임 워크에서 호출 `CComboBox` 개체 또는 콤보 상자가 제거 합니다.  
  
```  
virtual void DeleteItem(LPDELETEITEMSTRUCT lpDeleteItemStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpDeleteItemStruct`  
 Windows에 대 한 긴 포인터 [DELETEITEMSTRUCT](../../mfc/reference/deleteitemstruct-structure.md) 삭제 된 항목에 대 한 정보가 포함 된 구조체입니다. 참조 [CWnd::OnDeleteItem](../../mfc/reference/cwnd-class.md#ondeleteitem) 에 대 한 설명은이 구조입니다.  
  
### <a name="remarks"></a>설명  
 이 함수의 기본 구현은 아무 작업도 수행하지 않습니다. 필요에 따라 콤보 상자를 다시 그리게이 함수를 재정의 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#8](../../mfc/reference/codesnippet/cpp/ccombobox-class_8.cpp)]  
  
##  <a name="deletestring"></a>CComboBox::DeleteString  
 위치에 항목을 삭제 `nIndex` 콤보 상자에서 합니다.  
  
```  
int DeleteString(UINT nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 인덱스를 삭제 해야 하는 문자열을 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값은 0 보다 크거나 경우 목록에 남아 있는 문자열의 개수는 다음 합니다. 반환 값은 **CB_ERR** 경우 `nIndex` 목록의 항목 개수 보다 큰 인덱스를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 다음 모든 항목 `nIndex` 이제 한 칸 아래로 이동 합니다. 예를 들어, 콤보 상자에 두 개의 항목이 포함 된 경우 첫 번째 항목을 삭제 된 나머지 항목을 지금 첫 번째 위치에 발생 합니다. `nIndex`첫 번째 위치에 있는 항목에 대 한 0을 =입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#9](../../mfc/reference/codesnippet/cpp/ccombobox-class_9.cpp)]  
  
##  <a name="dir"></a>CComboBox::Dir  
 콤보 상자의 목록 상자에 파일 이름 또는 드라이브의 목록을 추가합니다.  
  
```  
int Dir(
    UINT attr,  
    LPCTSTR lpszWildCard);
```  
  
### <a name="parameters"></a>매개 변수  
 `attr`  
 조합이 포함 될 수는 `enum` 값에서 설명 [CFile::GetStatus](../../mfc/reference/cfile-class.md#getstatus) 또는 다음 값의 임의 조합 합니다.  
  
- **DDL_READWRITE** 파일에서 읽거나 수에 기록 합니다.  
  
- **DDL_READONLY** 파일에서 읽을 수 있지만에 기록 되지 않습니다.  
  
- **DDL_HIDDEN** 숨겨져 파일과 디렉터리 목록에 표시 되지 않습니다.  
  
- **DDL_SYSTEM** 파일 시스템 파일입니다.  
  
- **DDL_DIRECTORY** 지정 하는 이름 `lpszWildCard` 디렉터리를 지정 합니다.  
  
- **DDL_ARCHIVE** 파일 보관 되었습니다.  
  
- **DDL_DRIVES** 로 지정 된 이름과 일치 하는 모든 드라이브가 포함 `lpszWildCard`합니다.  
  
- **DDL_EXCLUSIVE** Exclusive 플래그입니다. 단독 플래그가 설정 된 경우 지정 된 형식의 파일에만 나열 됩니다. 그렇지 않은 경우 지정 된 형식의 파일은 "일반" 파일 외에도 나열 됩니다.  
  
 `lpszWildCard`  
 파일 사양 문자열을 가리킵니다. 문자열에서 와일드 카드를 포함할 수 있습니다 (예를 들어 *.\*).  
  
### <a name="return-value"></a>반환 값  
 반환 값은 0 보다 크거나 경우 목록에 추가 된 마지막 파일의 0부터 시작 인덱스는 합니다. 반환 값은 **CB_ERR** 오류가 발생 하는 경우 반환 값은 **CB_ERRSPACE** 새 문자열을 저장할 수 있는 공간이 부족 한 경우.  
  
### <a name="remarks"></a>설명  
 이 함수는 Windows **ComboBoxEx** 컨트롤에서 지원되지 않습니다. 이 컨트롤에 대 한 자세한 내용은 참조 하십시오. [ComboBoxEx 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb775738) Windows sdk에서입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#10](../../mfc/reference/codesnippet/cpp/ccombobox-class_10.cpp)]  
  
##  <a name="drawitem"></a>CComboBox::DrawItem  
 소유자 그리기 콤보 상자 변경의 시각적 측면이 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpDrawItemStruct`  
 에 대 한 포인터는 [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) 드로잉 필요한의 종류에 대 한 정보가 포함 된 구조체입니다.  
  
### <a name="remarks"></a>설명  
 **itemAction** 의 멤버는 `DRAWITEMSTRUCT` 구조 정의 그리기 작업을 수행 하는 것입니다. 참조 [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) 에 대 한 설명은이 구조입니다.  
  
 기본적으로이 멤버 함수는 아무 작업도 수행 하지 않습니다. 소유자 그리기에 대 한 그리기를 구현 하려면이 멤버 함수 재정의 `CComboBox` 개체입니다. 응용 프로그램에 제공 된 디스플레이 컨텍스트에 대해 선택한 모든 그래픽 장치 GDI (인터페이스) 개체를 복원 해야이 멤버 함수 종료 전에 `lpDrawItemStruct`합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#11](../../mfc/reference/codesnippet/cpp/ccombobox-class_11.cpp)]  
  
##  <a name="findstring"></a>CComboBox::FindString  
 을 찾았지만 선택 하지 않는 콤보 상자의 목록 상자에서 지정된 된 접두사를 포함 하는 첫 번째 문자열입니다.  
  
```  
int FindString(
    int nStartAfter,  
    LPCTSTR lpszString) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nStartAfter`  
 첫 번째 항목을 검색 하기 전에 항목의 0부터 시작 하는 인덱스를 포함 합니다. 로 지정 된 항목에 다시 목록 상자 맨 위부터 계속 검색 목록 상자의 아래쪽에 도달 하면 `nStartAfter`합니다. -1 이면 전체 목록 상자 시작 부분에서 검색 됩니다.  
  
 `lpszString`  
 검색할 접두사를 포함 하는 null로 끝나는 문자열을 가리킵니다. 검색 독립적 이며 대/소문자 이므로 모든 조합의 대문자 및 소문자가이 문자열 포함 될 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값 보다 큰 또는 0 인 경우 일치 하는 항목의 0부터 시작 인덱스입니다. **CB_ERR** 검색에 실패 한 경우.  
  
### <a name="remarks"></a>설명  
 이 함수는 Windows **ComboBoxEx** 컨트롤에서 지원되지 않습니다. 이 컨트롤에 대 한 자세한 내용은 참조 하십시오. [ComboBoxEx 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb775738) Windows sdk에서입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#12](../../mfc/reference/codesnippet/cpp/ccombobox-class_12.cpp)]  
  
##  <a name="findstringexact"></a>CComboBox::FindStringExact  
 호출 된 `FindStringExact` 멤버 함수에 지정 된 문자열과 일치 하는 콤보 상자에서 첫 번째 목록 상자 문자열을 찾을 `lpszFind`합니다.  
  
```  
int FindStringExact(
    int nIndexStart,  
    LPCTSTR lpszFind) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndexStart`  
 첫 번째 항목을 검색 하기 전에 항목의 0부터 시작 하는 인덱스를 지정 합니다. 로 지정 된 항목에 다시 목록 상자 맨 위부터 계속 검색 목록 상자의 아래쪽에 도달 하면 `nIndexStart`합니다. 경우 `nIndexStart` -1 이면 전체 목록 상자 시작 부분에서 검색 됩니다.  
  
 `lpszFind`  
 검색할 null로 끝나는 문자열을 가리킵니다. 이 문자열의 확장명을 포함 하 여 전체 파일 이름을 포함할 수 있습니다. 검색 대/소문자를 구분 하지 않으므로 모든 조합의 대문자 및 소문자가이 문자열 포함 될 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 일치 하는 항목의 0부터 시작 하는 인덱스 또는 **CB_ERR** 검색에 실패 한 경우.  
  
### <a name="remarks"></a>설명  
 소유자 그리기 스타일을 없이 콤보 상자를 만든 경우의 [CBS_HASSTRINGS](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일 `FindStringExact` 워드 단위 값의 값과 일치 시 키 려 `lpszFind`합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#13](../../mfc/reference/codesnippet/cpp/ccombobox-class_13.cpp)]  
  
##  <a name="getcomboboxinfo"></a>CComboBox::GetComboBoxInfo  
 에 대 한 정보를 검색에서 `CComboBox` 개체입니다.  
  
```  
BOOL GetComboBoxInfo(PCOMBOBOXINFO pcbi) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *pcbi*  
 에 대 한 포인터는 [COMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775798) 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>설명  
 기능을 에뮬레이션 하는이 멤버 함수는 [CB_GETCOMBOBOXINFO](http://msdn.microsoft.com/library/windows/desktop/bb775839) Windows SDK에 설명 된 대로 메시지입니다.  
  
##  <a name="getcount"></a>CComboBox::GetCount  
 콤보 상자의 목록 상자 부분에 있는 항목의 수를 검색 하려면이 멤버 함수를 호출 합니다.  
  
```  
int GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 항목 수입니다. 반환 된 횟수가 1 (인덱스는 0부터 시작) 마지막 항목의 인덱스 값 보다 큽니다. **CB_ERR** 오류가 발생 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#14](../../mfc/reference/codesnippet/cpp/ccombobox-class_14.cpp)]  
  
##  <a name="getcuebanner"></a>CComboBox::GetCueBanner  
 콤보 상자 컨트롤에 대해 표시 되는 큐 텍스트를 가져옵니다.  
  
```  
CString GetCueBanner() const;  
  
BOOL GetCueBanner(
    LPTSTR lpszText,   
    int cchText) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[out] `lpszText`|큐 배너 텍스트를 수신 하는 버퍼에 대 한 포인터입니다.|  
|[in] `cchText`|버퍼의 크기는는 `lpszText` 매개 변수를 가리킵니다.|  
  
### <a name="return-value"></a>반환 값  
 첫 번째 오버 로드에는 [CString](../../atl-mfc-shared/using-cstring.md) 않으면 큐 배너 텍스트를 포함 하는 개체, 한 `CString` 개체 길이가 0입니다.  
  
 또는  
  
 두 번째 오버 로드에서 `true` 이 메서드가 성공적 이면 `false`합니다.  
  
### <a name="remarks"></a>설명  
 큐 텍스트 콤보 상자 컨트롤의 입력된 영역에 표시 되는 프롬프트입니다. 큐 텍스트는 사용자 입력을 제공할 때까지 표시 됩니다.  
  
 이 메서드는 전송 된 [CB_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775843) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="getcursel"></a>CComboBox::GetCurSel  
 선택 된 콤보 상자에서 항목을 확인 하려면이 함수를 호출 합니다.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>반환 값  
 콤보 상자의 목록 상자에서 현재 선택한 항목의 0부터 시작 하는 인덱스 또는 **CB_ERR** 선택 된 항목이 없는 경우.  
  
### <a name="remarks"></a>설명  
 `GetCurSel`목록에 인덱스를 반환합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#15](../../mfc/reference/codesnippet/cpp/ccombobox-class_15.cpp)]  
  
##  <a name="getdroppedcontrolrect"></a>CComboBox::GetDroppedControlRect  
 호출 된 `GetDroppedControlRect` 드롭다운 콤보 상자의 표시 (삭제) 목록 상자의 화면 좌표를 검색 하려면 멤버 함수입니다.  
  
```  
void GetDroppedControlRect(LPRECT lprect) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *lprect*  
 가리키는 [RECT 구조체](../../mfc/reference/rect-structure1.md) 좌표를 수신 하는입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#16](../../mfc/reference/codesnippet/cpp/ccombobox-class_16.cpp)]  
  
##  <a name="getdroppedstate"></a>CComboBox::GetDroppedState  
 호출 된 `GetDroppedState` 멤버 함수를 (내려가면) 드롭다운 콤보 상자의 목록 상자를 표시할지 여부를 결정 합니다.  
  
```  
BOOL GetDroppedState() const;  
```  
  
### <a name="return-value"></a>반환 값  
 목록 상자에 표시 되 면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#17](../../mfc/reference/codesnippet/cpp/ccombobox-class_17.cpp)]  
  
##  <a name="getdroppedwidth"></a>CComboBox::GetDroppedWidth  
 콤보 상자의 목록 상자를 픽셀 단위로 허용 가능한 최소 너비를 검색 하려면이 함수를 호출 합니다.  
  
```  
int GetDroppedWidth() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 최소 허용 가능한 너비 (픽셀)입니다. 그렇지 않으면 **CB_ERR**합니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 콤보 상자에만 적용 됩니다는 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 또는 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일입니다.  
  
 기본적으로 허용 가능한 최소 너비인 드롭 다운 목록 상자는 0입니다. 허용 가능한 최소 너비를 호출 하 여 설정할 수 있습니다 [SetDroppedWidth](#setdroppedwidth)합니다. 콤보 상자의 목록 상자 부분이 표시 될 때 해당 너비는 허용 가능한 최소 너비 또는 콤보 상자 너비 중 더 큰 숫자입니다.  
  
### <a name="example"></a>예  
  예를 참조 [SetDroppedWidth](#setdroppedwidth)합니다.  
  
##  <a name="geteditsel"></a>CComboBox::GetEditSel  
 콤보 상자의 편집 컨트롤에 현재 선택 영역의 시작 및 끝 문자 위치를 가져옵니다.  
  
```  
DWORD GetEditSel() const;  
```  
  
### <a name="return-value"></a>반환 값  
 상위 word에서 선택 항목의 끝 다음 하위 단어의 시작 위치 및 선택 되지 않은 첫 번째 문자의 위치를 포함 하는 32 비트 값입니다. 이 함수는 편집 컨트롤 없이 콤보 상자에 사용 되는 경우 **CB_ERR** 반환 됩니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#18](../../mfc/reference/codesnippet/cpp/ccombobox-class_18.cpp)]  
  
##  <a name="getextendedui"></a>CComboBox::GetExtendedUI  
 호출 된 `GetExtendedUI` 멤버 함수는 기본 사용자 인터페이스 또는 확장 된 사용자 인터페이스는 콤보 상자에 있는지 확인 합니다.  
  
```  
BOOL GetExtendedUI() const;  
```  
  
### <a name="return-value"></a>반환 값  
 콤보 상자에는 확장 된 사용자 인터페이스에는 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 확장 된 사용자 인터페이스는 다음과 같은 방법으로 식별할 수 있습니다.  
  
-   으로 콤보 상자에 대 한 목록 상자를 표시 정적 컨트롤을 클릭 하 고 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일입니다.  
  
-   아래쪽 화살표 키를 누르면 (F4 사용 안 함)의 목록 상자를 표시 합니다.  
  
 정적 컨트롤에서 스크롤 항목 목록 표시 (화살표 키가 비활성화) 없는 경우 비활성화 됩니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#19](../../mfc/reference/codesnippet/cpp/ccombobox-class_19.cpp)]  
  
##  <a name="gethorizontalextent"></a>CComboBox::GetHorizontalExtent  
 콤보 상자에서 콤보 상자의 목록 상자 부분을 가로로 스크롤할 수 픽셀에서 너비를 검색 합니다.  
  
```  
UINT GetHorizontalExtent() const;  
```  
  
### <a name="return-value"></a>반환 값  
 스크롤할 수 있는 너비 (픽셀)에서 콤보 상자의 목록 상자 부분입니다.  
  
### <a name="remarks"></a>설명  
 콤보 상자의 목록 상자 부분 가로 스크롤 막대가 있는 경우에 적용 됩니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#20](../../mfc/reference/codesnippet/cpp/ccombobox-class_20.cpp)]  
  
##  <a name="getitemdata"></a>CComboBox::GetItemData  
 지정 된 콤보 상자 항목에 연결 된 응용 프로그램에서 제공 32 비트 값을 검색 합니다.  
  
```  
DWORD_PTR GetItemData(int nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 콤보 상자의 목록 상자에 있는 항목의 0부터 시작 하는 인덱스를 포함합니다.  
  
### <a name="return-value"></a>반환 값  
 항목에 연결 된 32 비트 값 또는 **CB_ERR** 오류가 발생 합니다.  
  
### <a name="remarks"></a>설명  
 32 비트 값으로 설정할 수 있습니다는 `dwItemData` 의 매개 변수는 [SetItemData](#setitemdata) 멤버 함수 호출 합니다. 사용 하 여는 `GetItemDataPtr` 32 비트 값을 검색할 수 한 포인터인 멤버 함수 ( **void\***).  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#21](../../mfc/reference/codesnippet/cpp/ccombobox-class_21.cpp)]  
  
##  <a name="getitemdataptr"></a>CComboBox::GetItemDataPtr  
 응용 프로그램에서 제공 32 비트 값 포인터와 지정 된 콤보 상자 항목에 연결 된 검색 ( **void\***).  
  
```  
void* GetItemDataPtr(int nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 콤보 상자의 목록 상자에 있는 항목의 0부터 시작 하는 인덱스를 포함합니다.  
  
### <a name="return-value"></a>반환 값  
 오류가 발생 하는 경우에 포인터 또는-1을 검색 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#22](../../mfc/reference/codesnippet/cpp/ccombobox-class_22.cpp)]  
  
##  <a name="getitemheight"></a>CComboBox::GetItemHeight  
 호출 된 `GetItemHeight` 콤보 상자에 있는 목록 항목의 높이 검색 하려면 멤버 함수입니다.  
  
```  
int GetItemHeight(int nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 검색할 수 있는 높이 콤보 상자의 구성 요소를 지정 합니다. 경우는 `nIndex` 매개 변수가-1 이면 콤보 상자의 편집 컨트롤 (또는 정적 텍스트) 부분의 높이 검색 합니다. 콤보 상자에는 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일 `nIndex` 를 검색할 수 있는 높이 목록 항목의 0부터 시작 하는 인덱스를 지정 합니다. 그렇지 않으면 `nIndex` 0으로 설정 해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 픽셀 콤보 상자에 지정된 된 항목의 높이입니다. 오류가 발생할 경우 반환 값은 **CB_ERR** 입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#23](../../mfc/reference/codesnippet/cpp/ccombobox-class_23.cpp)]  
  
##  <a name="getlbtext"></a>CComboBox::GetLBText  
 콤보 상자의 목록 상자에서 문자열을 가져옵니다.  
  
```  
int GetLBText(
    int nIndex,  
    LPTSTR lpszText) const;  
  
void GetLBText(
    int nIndex,  
    CString& rString) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 복사할 목록 상자 문자열의 0부터 시작 인덱스를 포함 합니다.  
  
 `lpszText`  
 문자열을 받을 수 있는 버퍼를 가리킵니다. 버퍼에 문자열 및 null 종결 문자에 대 한 충분 한 공간이 있어야 합니다.  
  
 `rString`  
 에 대 한 참조는 `CString`합니다.  
  
### <a name="return-value"></a>반환 값  
 길이 (바이트)의 null 종결 문자를 제외 하는 문자열입니다. 경우 `nIndex` 유효한 인덱스를 지정 하지 않는 경우 반환 값은 **CB_ERR**합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버에 두 번째 형태 채우기 함수는 `CString` 항목의 텍스트와 함께 개체입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#24](../../mfc/reference/codesnippet/cpp/ccombobox-class_24.cpp)]  
  
##  <a name="getlbtextlen"></a>CComboBox::GetLBTextLen  
 콤보 상자의 목록 상자에는 문자열의 길이 가져옵니다.  
  
```  
int GetLBTextLen(int nIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 목록 상자 문자열의 0부터 시작 인덱스를 포함합니다.  
  
### <a name="return-value"></a>반환 값  
 Null 종결 문자를 제외한 바이트 문자열의 길이입니다. 경우 `nIndex` 유효한 인덱스를 지정 하지 않는 경우 반환 값은 **CB_ERR**합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CComboBox::GetLBText](#getlbtext)합니다.  
  
##  <a name="getlocale"></a>CComboBox::GetLocale  
 콤보 상자에서 사용 하는 로캘을 검색 합니다.  
  
```  
LCID GetLocale() const;  
```  
  
### <a name="return-value"></a>반환 값  
 콤보 상자의 문자열에 대 한 로캘 id (LCID) 값입니다.  
  
### <a name="remarks"></a>설명  
 예를 들어 로캘 정렬 된 콤보 상자에서 문자열의 정렬 순서를 결정 하려면 사용 됩니다.  
  
### <a name="example"></a>예  
  예를 참조 [CComboBox::SetLocale](#setlocale)합니다.  
  
##  <a name="getminvisible"></a>CComboBox::GetMinVisible  
 현재 콤보 상자 컨트롤의 드롭다운 목록에 표시 된 항목의 최소 수를 가져옵니다.  
  
```  
int GetMinVisible() const;  
```  
  
### <a name="return-value"></a>반환 값  
 최소 현재 드롭 다운 목록에 표시 되는 항목 수입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [CB_GETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
##  <a name="gettopindex"></a>CComboBox::GetTopIndex  
 콤보 상자의 목록 상자 부분에 표시 되는 첫 번째 항목의 0부터 시작 하는 인덱스를 검색합니다.  
  
```  
int GetTopIndex() const;  
```  
  
### <a name="return-value"></a>반환 값  
 성공 하면 콤보 상자의 목록 상자 부분에 표시 되는 첫 번째 항목의 0부터 시작 인덱스 **CB_ERR** 그렇지 않은 경우.  
  
### <a name="remarks"></a>설명  
 처음에 0 항목 목록 상자의 위쪽에는 있지만 목록 상자 스크롤 된 다른 항목 맨 위에 있는 될 수 있습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#25](../../mfc/reference/codesnippet/cpp/ccombobox-class_25.cpp)]  
  
##  <a name="initstorage"></a>CComboBox::InitStorage  
 콤보 상자의 목록 상자 부분에서 목록 상자 항목을 저장 하기 위한 메모리를 할당 합니다.  
  
```  
int InitStorage(
    int nItems,  
    UINT nBytes);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItems`  
 추가할 항목의 수를 지정 합니다.  
  
 `nBytes`  
 메모리의 양 (바이트)를 항목 문자열에 대 한 할당 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 경우 성공는 최대 항목 수 콤보 상자의 목록 상자 부분 메모리 재할당이 필요 하지 않으면 전에 저장할 수 있습니다 **CB_ERRSPACE**, 메모리가 부족 의미를 사용할 수 있습니다.  
  
### <a name="remarks"></a>설명  
 많은 수의 항목은 목록 상자 부분에 추가 하기 전에이 함수 호출의 `CComboBox`합니다.  
  
 Windows 95/98만:는 `wParam` 매개 변수는 16 비트 값으로 제한 합니다. 즉, 목록 상자 개 이상 항목을 포함할 수 없습니다. 항목 수가 제한 된 경우에 목록 상자에 있는 항목의 총 크기는 사용 가능한 메모리 크기로 제한 됩니다.  
  
 이 함수를 사용 하면 다 수 (100 넘으면) 항목의 목록 상자를 초기화 하는 속도입니다. 그러면 다음 메모리의 지정 된 크기를 preallocates [AddString](#addstring), [InsertString](#insertstring), 및 [Dir](#dir) 함수는 사용 가능한 가장 짧은 시간입니다. 매개 변수 예상치를 사용할 수 있습니다. 평가 하면 일부 추가 메모리 할당 됩니다. 하면 과소 평가 하는 경우 일반 할당 미리 할당 된 크기를 초과 하는 항목에 사용 됩니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#26](../../mfc/reference/codesnippet/cpp/ccombobox-class_26.cpp)]  
  
##  <a name="insertstring"></a>CComboBox::InsertString  
 콤보 상자의 목록 상자에 문자열을 삽입합니다.  
  
```  
int InsertString(
    int nIndex,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 문자열을 받을 목록 상자의 위치에 대한 0부터 시작하는 인덱스를 포함합니다. 이 매개 변수가-1 이면 문자열이 목록의 끝에 추가 됩니다.  
  
 `lpszString`  
 삽입할 null 종료 문자열을 가리킵니다.  
  
### <a name="return-value"></a>반환 값  
 문자열이 삽입된 위치의 0부터 시작하는 인덱스입니다. 오류가 발생할 경우 반환 값은 **CB_ERR** 입니다. 공간이 부족하여 새 문자열을 저장할 수 없는 경우 반환 값은 **CB_ERRSPACE** 입니다.  
  
### <a name="remarks"></a>설명  
 와 달리는 [AddString](#addstring) 멤버 함수는 `InsertString` 멤버 함수에 포함 된 목록을 발생 하지 않습니다는 [CBS_SORT](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 정렬 스타일입니다.  
  
> [!NOTE]
>  이 함수는 Windows **ComboBoxEx** 컨트롤에서 지원되지 않습니다. 이 컨트롤에 대 한 자세한 내용은 참조 하십시오. [ComboBoxEx 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb775738) Windows sdk에서입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#27](../../mfc/reference/codesnippet/cpp/ccombobox-class_27.cpp)]  
  
##  <a name="limittext"></a>CComboBox::LimitText  
 콤보 상자의 편집 컨트롤에 입력할 수 있는 텍스트의 길이 (바이트)를 제한 합니다.  
  
```  
BOOL LimitText(int nMaxChars);
```  
  
### <a name="parameters"></a>매개 변수  
 `nMaxChars`  
 입력할 수 있는 텍스트의 바이트 단위로 지정 합니다. 이 매개 변수가 0 이면 텍스트 길이 65, 535 바이트에 설정 됩니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0이 아닙니다. 콤보 상자 스타일에 대 한 메서드를 호출 하면 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 콤보 상자 편집 컨트롤 없이 반환 값은 또는 **CB_ERR**합니다.  
  
### <a name="remarks"></a>설명  
 콤보 상자 스타일 없으면 [CBS_AUTOHSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles), edit 컨트롤의 크기 보다 커져 텍스트 제한을 설정 아무런 효과가 없습니다.  
  
 `LimitText`만 입력할 수 있는 텍스트를 제한 합니다. 모든 텍스트에 영향을 주지 이미 편집 컨트롤에 때이 메시지를 보낼 나 목록 상자에 문자열을 선택 하는 편집 컨트롤에 복사 하는 텍스트의 길이 영향을 것입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#28](../../mfc/reference/codesnippet/cpp/ccombobox-class_28.cpp)]  
  
##  <a name="measureitem"></a>CComboBox::MeasureItem  
 소유자 그리기 스타일이 적용 된 콤보 상자를 만들 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpMeasureItemStruct`  
 에 대 한 긴 포인터는 [MEASUREITEMSTRUCT](../../mfc/reference/measureitemstruct-structure.md) 구조입니다.  
  
### <a name="remarks"></a>설명  
 기본적으로이 멤버 함수는 아무 작업도 수행 하지 않습니다. 이 멤버 함수를 재정의 하 고 입력의 `MEASUREITEMSTRUCT` 구조를 콤보 상자에서 목록의 크기의 상자에 게 알립니다. 콤보 상자 만들어진 경우는 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일, 프레임 워크가 멤버 함수 목록 상자에서 각 항목에 대 한 호출 합니다. 그렇지 않은 경우이 멤버는 한 번만 호출 됩니다.  
  
 사용 하는 **CBS_OWNERDRAWFIXED** 사용 하 여 만든 소유자 그리기 콤보 상자의 스타일의 [SubclassDlgItem](../../mfc/reference/cwnd-class.md#subclassdlgitem) 의 멤버 함수 `CWnd` 추가 프로그래밍 고려 사항 포함 됩니다. 참조 [기술 참고 14](../../mfc/tn014-custom-controls.md)합니다.  
  
 참조 [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) 에 대 한 설명은 `MEASUREITEMSTRUCT` 구조입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#29](../../mfc/reference/codesnippet/cpp/ccombobox-class_29.cpp)]  
  
##  <a name="paste"></a>CComboBox::Paste  
 클립보드의 현재 커서 위치에 콤보 상자의 편집 컨트롤에 데이터를 삽입합니다.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>설명  
 데이터를 클립보드에 데이터를 포함 하는 경우에 삽입 **CF_TEXT** 형식입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#30](../../mfc/reference/codesnippet/cpp/ccombobox-class_30.cpp)]  
  
##  <a name="resetcontent"></a>CComboBox::ResetContent  
 목록에서 모든 항목 상자 및 콤보 상자 컨트롤을 편집할를 제거 합니다.  
  
```  
void ResetContent();
```  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#31](../../mfc/reference/codesnippet/cpp/ccombobox-class_31.cpp)]  
  
##  <a name="selectstring"></a>CComboBox::SelectString  
 콤보 상자의 목록 상자에 문자열을 검색 하 고 문자열이 발견 되는 경우 목록 상자에 문자열을 선택 하 고 편집 컨트롤에 복사 합니다.  
  
```  
int SelectString(
    int nStartAfter,  
    LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>매개 변수  
 `nStartAfter`  
 첫 번째 항목을 검색 하기 전에 항목의 0부터 시작 하는 인덱스를 포함 합니다. 로 지정 된 항목에 다시 목록 상자 맨 위부터 계속 검색 목록 상자의 아래쪽에 도달 하면 `nStartAfter`합니다. -1 이면 전체 목록 상자 시작 부분에서 검색 됩니다.  
  
 `lpszString`  
 검색할 접두사를 포함 하는 null로 끝나는 문자열을 가리킵니다. 검색 독립적 이며 대/소문자 이므로 모든 조합의 대문자 및 소문자가이 문자열 포함 될 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 문자열이 발견 된 경우 선택된 된 항목의 0부터 시작 하는 인덱스입니다. 반환 값은 검색 하지 못한 경우 **CB_ERR** 현재 선택 영역이 변경 되지 않습니다.  
  
### <a name="remarks"></a>설명  
 문자열의 초기 문자 (시작 점에서) 접두사 문자열의에서 문자를 일치 하는 경우에 선택 됩니다.  
  
 `SelectString` 및 `FindString` 멤버 함수는 문자열을 찾으려면 되지만 `SelectString` 멤버 함수는 또한 문자열을 선택 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#32](../../mfc/reference/codesnippet/cpp/ccombobox-class_32.cpp)]  
  
##  <a name="setcuebanner"></a>CComboBox::SetCueBanner  
 콤보 상자 컨트롤에 대해 표시 되는 큐 텍스트를 설정 합니다.  
  
```  
BOOL SetCueBanner(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] *lpszText*|큐 텍스트를 포함 하는 null로 끝나는 버퍼에 대 한 포인터입니다.|  
  
### <a name="return-value"></a>반환 값  
 해당 메서드에 성공하면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 큐 텍스트 콤보 상자 컨트롤의 입력된 영역에 표시 되는 프롬프트입니다. 큐 텍스트는 사용자 입력을 제공할 때까지 표시 됩니다.  
  
 이 메서드는 전송 된 [CB_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb775897) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 변수를 정의 `m_combobox`즉, 콤보 상자 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 콤보 상자 컨트롤에 대 한 큐 배너를 설정합니다.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="setcursel"></a>CComboBox::SetCurSel  
 콤보 상자의 목록 상자에 문자열을 선택합니다.  
  
```  
int SetCurSel(int nSelect);
```  
  
### <a name="parameters"></a>매개 변수  
 `nSelect`  
 선택 하는 데 사용할 문자열의 0부터 시작 하는 인덱스를 지정 합니다. -1 이면 목록 상자에서 현재 선택 제거 되 고 편집 컨트롤의 선택이 취소 됩니다.  
  
### <a name="return-value"></a>반환 값  
 메시지를 성공적으로 선택한 항목의 0부터 시작 하는 인덱스입니다. 반환 값은 **CB_ERR** 경우 `nSelect` 목록의 항목 개수 보다 큰 경우 `nSelect` 선택을 해제는-1로 설정 됩니다.  
  
### <a name="remarks"></a>설명  
 필요한 경우 (목록 상자가 표시 됩니다) 하는 경우 목록 상자에서 문자열을을 뷰로 스크롤합니다. 콤보 상자의 편집 컨트롤의에서 텍스트를 새 선택을 반영 하도록 변경 됩니다. 목록 상자에서 이전 선택은 모두 제거 됩니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#33](../../mfc/reference/codesnippet/cpp/ccombobox-class_35.cpp)]  
  
##  <a name="setdroppedwidth"></a>CComboBox::SetDroppedWidth  
 콤보 상자의 목록 상자를 픽셀 단위로 허용 가능한 최소 너비를 설정 하려면이 함수를 호출 합니다.  
  
```  
int SetDroppedWidth(UINT nWidth);
```  
  
### <a name="parameters"></a>매개 변수  
 `nWidth`  
 픽셀 단위로 콤보 상자의 목록 상자 부분 허용 가능한 최소 너비입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 목록으로 새 너비 상자, 그렇지 않으면 **CB_ERR**합니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 콤보 상자에만 적용 됩니다는 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 또는 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일입니다.  
  
 기본적으로 허용 가능한 최소 너비인 드롭 다운 목록 상자는 0입니다. 콤보 상자의 목록 상자 부분이 표시 될 때 해당 너비는 허용 가능한 최소 너비 또는 콤보 상자 너비 중 더 큰 숫자입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#34](../../mfc/reference/codesnippet/cpp/ccombobox-class_36.cpp)]  
  
##  <a name="seteditsel"></a>CComboBox::SetEditSel  
 콤보 상자의 편집 컨트롤에 문자를 선택합니다.  
  
```  
BOOL SetEditSel(
    int nStartChar,  
    int nEndChar);
```  
  
### <a name="parameters"></a>매개 변수  
 `nStartChar`  
 시작 위치를 지정합니다. 시작 위치는-1로 설정 되 면 기존 선택은 모두 제거 됩니다.  
  
 `nEndChar`  
 끝 위치를 지정합니다. 끝 위치에서 마지막 시작 위치에서 모든 텍스트 다음-1로 설정 된 경우에 편집 컨트롤의 문자 선택 되어 있습니다.  
  
### <a name="return-value"></a>반환 값  
 멤버 함수에 성공 하면 0이 아닌 그렇지 않으면 0입니다. **CB_ERR** 경우 `CComboBox` 에 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일 또는 목록 상자에는 없습니다.  
  
### <a name="remarks"></a>설명  
 위치는 0부터 시작 합니다. 편집 컨트롤의 첫 번째 문자를 선택 하려면 0의 시작 위치를 지정 합니다. 끝 위치 선택 하려면 마지막 문자 바로 뒤의 문자입니다. 예를 들어 편집 컨트롤의 처음 4 개 문자를 선택 하려면 사용 합니다 0의 시작 위치와 끝 위치 4입니다.  
  
> [!NOTE]
>  이 함수는 Windows **ComboBoxEx** 컨트롤에서 지원되지 않습니다. 이 컨트롤에 대 한 자세한 내용은 참조 하십시오. [ComboBoxEx 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb775738) Windows sdk에서입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CComboBox::GetEditSel](#geteditsel)합니다.  
  
##  <a name="setextendedui"></a>CComboBox::SetExtendedUI  
 호출의 `SetExtendedUI` 멤버 함수는 기본 사용자 인터페이스 또는 있는 콤보 상자에 대 한 확장 된 사용자 인터페이스 중 하나를 선택 하 고 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 또는 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일입니다.  
  
```  
int SetExtendedUI(BOOL bExtended = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *bExtended*  
 콤보 상자 확장 된 사용자 인터페이스 또는 기본 사용자 인터페이스를 사용할지 여부를 지정 합니다. 값이 **TRUE** 확장 선택 사용자 인터페이스를, **FALSE** 표준 사용자 인터페이스를 선택 합니다.  
  
### <a name="return-value"></a>반환 값  
 **CB_OKAY** 작업이 성공할 경우 또는 **CB_ERR** 오류가 발생 합니다.  
  
### <a name="remarks"></a>설명  
 확장 된 사용자 인터페이스는 다음과 같은 방법으로 식별할 수 있습니다.  
  
-   으로 콤보 상자에 대 한 목록 상자를 표시 정적 컨트롤을 클릭 하 고 **CBS_DROPDOWNLIST** 스타일입니다.  
  
-   아래쪽 화살표 키를 누르면 (F4 사용 안 함)의 목록 상자를 표시 합니다.  
  
 정적 컨트롤에서 스크롤을 사용할 수 없습니다 항목 목록이 표시 되지 않으면 (화살표 키가 비활성화) 합니다.  
  
### <a name="example"></a>예  
  예를 참조 [CComboBox::GetExtendedUI](#getextendedui)합니다.  
  
##  <a name="sethorizontalextent"></a>CComboBox::SetHorizontalExtent  
 콤보 상자의 목록 상자 부분을 가로로 스크롤할 수 픽셀 너비를 설정 합니다.  
  
```  
void SetHorizontalExtent(UINT nExtent);
```  
  
### <a name="parameters"></a>매개 변수  
 *nExtent*  
 콤보 상자의 목록 상자 부분을 가로로 스크롤할 수 픽셀 수를 지정 합니다.  
  
### <a name="remarks"></a>설명  
 목록 상자의 너비가이 값 보다 작은 경우 가로 스크롤 막대를 가로로 목록 상자의 항목 스크롤됩니다. 가로 스크롤 막대가 숨겨집니다 목록 상자의 너비가이 값 보다 크거나 같은 경우 또는 콤보 상자에는 [CBS_DISABLENOSCROLL](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일을 사용 하지 않도록 설정 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#35](../../mfc/reference/codesnippet/cpp/ccombobox-class_37.cpp)]  
  
##  <a name="setitemdata"></a>CComboBox::SetItemData  
 콤보 상자에 지정 된 항목과 연결 된 32 비트 값을 설정 합니다.  
  
```  
int SetItemData(
    int nIndex,  
    DWORD_PTR dwItemData);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 설정할 항목을 0 기반 인덱스를 포함 합니다.  
  
 `dwItemData`  
 항목과 연결할 새 값을 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 **CB_ERR** 오류가 발생 합니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여는 `SetItemDataPtr` 32 비트는 항목 하는 포인터 여야 하는 경우 멤버 함수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#36](../../mfc/reference/codesnippet/cpp/ccombobox-class_38.cpp)]  
  
##  <a name="setitemdataptr"></a>CComboBox::SetItemDataPtr  
 지정된 된 포인터를 콤보 상자에 지정 된 항목과 연결 된 32 비트 값을 설정 ( **void\***).  
  
```  
int SetItemDataPtr(
    int nIndex,  
    void* pData);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 항목으로 0 기반 인덱스를 포함합니다.  
  
 `pData`  
 항목과 연결 하는 포인터를 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 **CB_ERR** 오류가 발생 합니다.  
  
### <a name="remarks"></a>설명  
 이 포인터 콤보 상자 내에서 항목의 상대 위치 항목을 추가 하거나 제거할 때마다 변경 될 수 있지만 콤보 상자의 수명에 대 한 유효한 상태를 유지 합니다. 따라서 상자 내에서 항목의 인덱스를 변경할 수 있지만 포인터 신뢰할 수 있는 상태로 유지 됩니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#37](../../mfc/reference/codesnippet/cpp/ccombobox-class_39.cpp)]  
  
##  <a name="setitemheight"></a>CComboBox::SetItemHeight  
 호출 된 `SetItemHeight` 멤버 함수를 콤보 상자 또는 콤보 상자의 편집 컨트롤 (또는 정적 텍스트) 부분의 높이에 목록 항목의 높이 설정 합니다.  
  
```  
int SetItemHeight(
    int nIndex,  
    UINT cyItemHeight);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 목록 항목의 높이 또는 콤보 상자의 편집 컨트롤 (또는 정적 텍스트) 부분의 높이 설정 되었는지 여부를 지정 합니다.  
  
 콤보 상자에는 [CBS_OWNERDRAWVARIABLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일 `nIndex` 설정 필요가 없으면, 해당 높이 목록 항목의 0부터 시작 하는 인덱스를 지정 `nIndex` 0과의 모든 목록 항목을 설정할 수는 높이 이어야 합니다.  
  
 경우 `nIndex` 은 편집 컨트롤의 높이-1 또는 콤보 상자의 정적 텍스트 부분 값 이어야 합니다.  
  
 `cyItemHeight`  
 높이로 식별 되는 콤보 상자 구성 요소를 픽셀 단위로 지정 `nIndex`합니다.  
  
### <a name="return-value"></a>반환 값  
 **CB_ERR** 인덱스나 높이 잘못 되었습니다. 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 콤보 상자의 편집 컨트롤 (또는 정적 텍스트) 부분의 높이 목록 항목의 높이 독립적으로 설정 됩니다. 응용 프로그램 편집 컨트롤 (또는 정적 텍스트) 부분의 높이 특정 목록 상자 항목의 높이 보다 작으면 임을 확인 해야 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#38](../../mfc/reference/codesnippet/cpp/ccombobox-class_40.cpp)]  
  
##  <a name="setlocale"></a>CComboBox::SetLocale  
 이 콤보 상자에 대 한 로캘 식별자를 설정합니다.  
  
```  
LCID SetLocale(LCID nNewLocale);
```  
  
### <a name="parameters"></a>매개 변수  
 `nNewLocale`  
 새 로캘 id (LCID) 콤보 상자에 대해 설정할 값입니다.  
  
### <a name="return-value"></a>반환 값  
 이전 로캘 id (LCID)이 콤보 상자에 대 한 값입니다.  
  
### <a name="remarks"></a>설명  
 경우 **SetLocale** 를 호출 하지 않으면 기본 시스템에서 로캘을 가져옵니다. 이 시스템 기본 로캘 제어판의를 사용 하 여 수정할 수 있는 국가 (또는 국제) 응용 프로그램입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#39](../../mfc/reference/codesnippet/cpp/ccombobox-class_41.cpp)]  
  
##  <a name="setminvisibleitems"></a>CComboBox::SetMinVisibleItems  
 상자 컨트롤의 현재 콤보 드롭 다운 목록에서 표시 된 항목의 최소 수를 설정 합니다.  
  
```  
BOOL SetMinVisibleItems(int iMinVisible);
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `iMinVisible`|표시 된 항목의 최소 수를 지정 합니다.|  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `true`이고, 그렇지 않으면 `false`입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 전송 된 [CB_SETMINVISIBLE](http://msdn.microsoft.com/library/windows/desktop/bb775915) 메시지는 Windows SDK에 설명 되어 있습니다.  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 변수를 정의 `m_combobox`즉, 콤보 상자 컨트롤을 프로그래밍 방식으로 액세스 하는 데 사용 합니다. 이 변수는 다음 예제에서 사용됩니다.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#1](../../mfc/reference/codesnippet/cpp/ccombobox-class_33.h)]  
  
### <a name="example"></a>예  
 다음 코드 예제에서는 콤보 상자 컨트롤의 드롭다운 목록에 20 개의 항목을 삽입합니다. 그런 다음 드롭다운 화살표를 누를 때 최소 10 개의 항목을 표시할 수를 지정 합니다.  
  
 [!code-cpp[NVC_MFC_CComboBox_s1#2](../../mfc/reference/codesnippet/cpp/ccombobox-class_34.cpp)]  
  
##  <a name="settopindex"></a>CComboBox::SetTopIndex  
 특정 항목 콤보 상자의 목록 상자 부분에 표시 되는지 확인 합니다.  
  
```  
int SetTopIndex(int nIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `nIndex`  
 목록 상자 항목의 0부터 시작 하는 인덱스를 지정합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 0 또는 **CB_ERR** 오류가 발생 합니다.  
  
### <a name="remarks"></a>설명  
 목록 상자에 지정 된 항목 될 때까지 스크롤 하는 시스템 `nIndex` 표시 목록 맨 위에 있는 상자 또는 최대 스크롤 범위에 도달 했습니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFC_CComboBox#40](../../mfc/reference/codesnippet/cpp/ccombobox-class_42.cpp)]  
  
##  <a name="showdropdown"></a>CComboBox::ShowDropDown  
 표시 하거나 숨깁니다 있는 콤보 상자의 목록 상자는 [CBS_DROPDOWN](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 또는 [CBS_DROPDOWNLIST](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일입니다.  
  
```  
void ShowDropDown(BOOL bShowIt = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 *bShowIt*  
 드롭다운 목록 상자 표시 하거나 숨길 수 있는지 여부를 지정 합니다. 값이 **TRUE** 목록 상자를 표시 합니다. 값이 **FALSE** 목록 상자를 숨깁니다.  
  
### <a name="remarks"></a>설명  
 기본적으로이 스타일의 콤보 상자 목록 상자를 표시 됩니다.  
  
 이 멤버 함수는 사용 하 여 만든 콤보 상자에 영향을 주지는 [CBS_SIMPLE](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles) 스타일입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CComboBox::GetDroppedState](#getdroppedstate)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 CTRLBARS](../../visual-cpp-samples.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CButton 클래스](../../mfc/reference/cbutton-class.md)   
 [CEdit 클래스](../../mfc/reference/cedit-class.md)   
 [CListBox 클래스](../../mfc/reference/clistbox-class.md)   
 [CScrollBar 클래스](../../mfc/reference/cscrollbar-class.md)   
 [CStatic 클래스](../../mfc/reference/cstatic-class.md)   
 [CDialog 클래스](../../mfc/reference/cdialog-class.md)
