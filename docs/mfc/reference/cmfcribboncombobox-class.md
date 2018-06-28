---
title: CMFCRibbonComboBox 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::CMFCRibbonComboBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::AddItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::DeleteItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::EnableDropDownListResize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::FindItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCount
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetCurSel
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetDropDownHeight
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetIntermediateSize
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::GetItemData
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::HasEditBox
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::IsResizeDropDownList
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::OnSelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::RemoveAllItems
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SelectItem
- AFXRIBBONCOMBOBOX/CMFCRibbonComboBox::SetDropDownHeight
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonComboBox [MFC], CMFCRibbonComboBox
- CMFCRibbonComboBox [MFC], AddItem
- CMFCRibbonComboBox [MFC], DeleteItem
- CMFCRibbonComboBox [MFC], EnableDropDownListResize
- CMFCRibbonComboBox [MFC], FindItem
- CMFCRibbonComboBox [MFC], GetCount
- CMFCRibbonComboBox [MFC], GetCurSel
- CMFCRibbonComboBox [MFC], GetDropDownHeight
- CMFCRibbonComboBox [MFC], GetIntermediateSize
- CMFCRibbonComboBox [MFC], GetItem
- CMFCRibbonComboBox [MFC], GetItemData
- CMFCRibbonComboBox [MFC], HasEditBox
- CMFCRibbonComboBox [MFC], IsResizeDropDownList
- CMFCRibbonComboBox [MFC], OnSelectItem
- CMFCRibbonComboBox [MFC], RemoveAllItems
- CMFCRibbonComboBox [MFC], SelectItem
- CMFCRibbonComboBox [MFC], SetDropDownHeight
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5894f1fc9bd901bef6e830250f4e1f8e9bdd335
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040756"
---
# <a name="cmfcribboncombobox-class"></a>CMFCRibbonComboBox 클래스
`CMFCRibbonComboBox` 클래스 리본 막대, 리본 패널 또는 리본 팝업 메뉴에 추가할 수 있는 콤보 상자 컨트롤을 구현 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCRibbonComboBox : public CMFCRibbonEdit  
```  
  
## <a name="members"></a>멤버  
  
### <a name="constructors"></a>생성자  
  
|name|설명|  
|----------|-----------------|  
|[CMFCRibbonComboBox::CMFCRibbonComboBox](#cmfcribboncombobox)|CMFCRibbonComboBox 개체를 만듭니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCRibbonComboBox::AddItem](#additem)|목록 상자에 고유한 항목을 추가합니다.|  
|[CMFCRibbonComboBox::DeleteItem](#deleteitem)|목록 상자에서 지정된 된 항목을 삭제합니다.|  
|[CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)|떨어지면 목록 상자에서 크기를 변경할 수 있는지 여부를 지정 합니다.|  
|[CMFCRibbonComboBox::FindItem](#finditem)|지정 된 문자열과 일치 하는 목록 상자에서 첫 번째 항목의 인덱스를 반환 합니다.|  
|[CMFCRibbonComboBox::GetCount](#getcount)|목록 상자에서 항목의 수를 반환합니다.|  
|[CMFCRibbonComboBox::GetCurSel](#getcursel)|목록 상자에서 현재 선택 된 항목의 인덱스를 가져옵니다.|  
|[CMFCRibbonComboBox::GetDropDownHeight](#getdropdownheight)|목록 상자를 삭제할 때 목록 상자의 높이 가져옵니다.|  
|[CMFCRibbonComboBox::GetIntermediateSize](#getintermediatesize)|중간 모드에 표시 된 대로 콤보 상자의 크기를 반환 합니다.|  
|[CMFCRibbonComboBox::GetItem](#getitem)|목록 상자에서 지정된 된 인덱스에 항목에 연결 된 문자열을 반환 합니다.|  
|[CMFCRibbonComboBox::GetItemData](#getitemdata)|목록 상자에서 지정된 된 인덱스에 항목에 연결 된 데이터를 반환 합니다.|  
|[CMFCRibbonComboBox::HasEditBox](#haseditbox)|편집 상자 컨트롤에 포함 되어 있는지 여부를 나타냅니다.|  
|[CMFCRibbonComboBox::IsResizeDropDownList](#isresizedropdownlist)|목록 상자 크기를 조정할 수 있는지 여부를 나타냅니다.|  
|[CMFCRibbonComboBox::OnSelectItem](#onselectitem)|목록 상자에서 항목을 선택할 때 프레임 워크에서 호출 됩니다.|  
|[CMFCRibbonComboBox::RemoveAllItems](#removeallitems)|목록 상자에서 모든 항목을 삭제 하 고 편집 상자를 지웁니다.|  
|[CMFCRibbonComboBox::SelectItem](#selectitem)|목록 상자에서 항목을 선택합니다.|  
|[CMFCRibbonComboBox::SetDropDownHeight](#setdropdownheight)|놓을 때 목록 상자의 높이 설정 합니다.|  
  
## <a name="remarks"></a>설명  
 정적 레이블 또는 사용자가 편집할 수 있는 레이블을 사용 하 여 결합 된 목록 상자의 글꼴로 리본 콤보 상자 구성 됩니다. 리본 콤보 상자를 만들 때 원하는 형식을 지정 해야 합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는의 개체를 생성 하는 `CMFCRibbonComboBox` 클래스, 콤보 상자에 항목을 추가, 콤보 상자에서 항목을 선택 및 콤보 상자 패널에 추가 합니다.  
  
 [!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/cpp/cmfcribboncombobox-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxribboncombobox.h  
  
##  <a name="additem"></a>  CMFCRibbonComboBox::AddItem  
 목록 상자에 고유한 항목을 추가합니다.  
  
```  
virtual INT_PTR AddItem(
    LPCTSTR lpszItem,  
    DWORD_PTR dwData=0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *lpszItem*  
 추가할 항목의 문자열입니다.  
  
 [in] *dwData*  
 추가할 항목에 연결 된 데이터입니다.  
  
### <a name="return-value"></a>반환 값  
 추가 된 항목의 0부터 시작 하는 인덱스입니다.  
  
##  <a name="cmfcribboncombobox"></a>  CMFCRibbonComboBox::CMFCRibbonComboBox  
 `CMFCRibbonComboBox` 개체를 생성합니다.  
  
```  
public:  
CMFCRibbonComboBox(
    UINT nID,  
    BOOL bHasEditBox=TRUE,  
    Int nWidth=-1,  
    LPCTSTR lpszLabel=NULL,  
    Int nImage=-1);

protected:  
CMFCRibbonComboBox();
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *nID*  
 콤보 상자의 ID입니다.  
  
 [in] *bHasEditBox*  
 `TRUE` 컨트롤에서 입력란을 원하는 경우 `FALSE` 그렇지 않은 경우.  
  
 [in] *nWidth*  
 너비의 픽셀;에 있는 콤보 상자 또는 기본 너비에 대 한-1을 추가 합니다.  
  
 [in] *lpszLabel*  
 콤보 상자의 레이블 표시 합니다.  
  
 [in] *nImage*  
 콤보 상자의 작은 이미지 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 기본 너비는 108 픽셀입니다.  
  
##  <a name="deleteitem"></a>  CMFCRibbonComboBox::DeleteItem  
 목록 상자에서 지정된 된 항목을 삭제합니다.  
  
```  
BOOL DeleteItem(int iIndex);
BOOL DeleteItem(DWORD_PTR dwData);

BOOL DeleteItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *iIndex*  
 삭제할 항목의 0부터 시작 하는 인덱스입니다.  
  
 [in] *dwData*  
 삭제할 항목에 연결 된 데이터입니다.  
  
 [in] *lpszText*  
 삭제할 항목의 문자열입니다. 동일한 문자열로 여러 항목이 있으면 첫 번째 항목이 삭제 됩니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 지정된 된 항목이 삭제 되었음을 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="enabledropdownlistresize"></a>  CMFCRibbonComboBox::EnableDropDownListResize  
 떨어지면 목록 상자에서 크기를 변경할 수 있는지 여부를 지정 합니다.  
  
```  
void EnableDropDownListResize(BOOL bEnable=FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *bEnable*  
 `TRUE` 크기 조정; 사용 하도록 설정 하려면 `FALSE` 크기를 조정 하지 않으려면입니다.  
  
### <a name="remarks"></a>설명  
 크기를 조정할 때 목록 상자 크기를 표시 하는 항목에 맞게 변경 됩니다.  
  
##  <a name="finditem"></a>  CMFCRibbonComboBox::FindItem  
 지정 된 문자열과 일치 하는 목록 상자에서 첫 번째 항목의 인덱스를 반환 합니다.  
  
```  
int FindItem(LPCTSTR lpszText) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *lpszText*  
 목록 상자에 있는 항목의 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 항목의 0부터 시작 인덱스 또는 항목을 찾을 수 없는 경우-1을 추가 합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getcount"></a>  CMFCRibbonComboBox::GetCount  
 목록 상자에서 항목의 수를 반환합니다.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 목록 상자 또는 목록 상자에 항목이 없는 경우 0에 있는 항목의 수입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getcursel"></a>  CMFCRibbonComboBox::GetCurSel  
 목록 상자에서 현재 선택 된 항목의 인덱스를 가져옵니다.  
  
```  
int GetCurSel() const;  
```  
  
### <a name="return-value"></a>반환 값  
 목록 상자에서 현재 선택 된 항목의 0부터 시작 인덱스 또는 선택 된 항목이 없으면-1입니다.  
  
##  <a name="getdropdownheight"></a>  CMFCRibbonComboBox::GetDropDownHeight  
 목록 상자를 삭제할 때 목록 상자의 높이 가져옵니다.  
  
```  
int GetDropDownHeight();
```  
  
### <a name="return-value"></a>반환 값  
 목록 상자의 픽셀 단위 높이입니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getintermediatesize"></a>  CMFCRibbonComboBox::GetIntermediateSize  
 중간 모드에 표시 된 대로 콤보 상자의 크기를 반환 합니다.  
  
```  
virtual CSize GetIntermediateSize(CDC* pDC);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *pDC*  
 콤보 상자에 대 한 장치 컨텍스트에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 콤보 상자의 크기입니다.  
  
### <a name="remarks"></a>설명  
 반환 되는 크기는 기반으로 콤보 상자의 크기가 작은 이미지를 표시 하는 경우 합니다.  
  
##  <a name="getitem"></a>  CMFCRibbonComboBox::GetItem  
 목록 상자에서 지정된 된 인덱스에 항목에 연결 된 문자열을 반환 합니다.  
  
```  
LPCTSTR GetItem(int iIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *iIndex*  
 목록 상자에 있는 항목의 0부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 항목과 연결 된 문자열에 대 한 포인터 그렇지 않으면 `NULL` 인덱스 매개 변수가 유효 하지 않을 경우 또는 인덱스 매개 변수가-1이 고 콤보 상자에서 선택한 항목이 없습니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="getitemdata"></a>  CMFCRibbonComboBox::GetItemData  
 목록 상자에서 지정된 된 인덱스에 항목에 연결 된 데이터를 반환 합니다.  
  
```  
DWORD_PTR GetItemData(int iIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *iIndex*  
 목록 상자에 있는 항목의 0부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 항목;에 연결 된 데이터 0 또는 항목이 없는 경우 또는 인덱스 매개 변수가-1이 고 목록 상자에서 선택한 항목이 없습니다.  
  
##  <a name="haseditbox"></a>  CMFCRibbonComboBox::HasEditBox  
 편집 상자 컨트롤에 포함 되어 있는지 여부를 나타냅니다.  
  
```  
BOOL HasEditBox() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 컨트롤 편집 상자; 포함 되 면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="isresizedropdownlist"></a>  CMFCRibbonComboBox::IsResizeDropDownList  
 목록 상자 크기를 조정할 수 있는지 여부를 나타냅니다.  
  
```  
BOOL IsResizeDropDownList() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 목록 상자 크기를 조정할 수; 경우 그렇지 않으면 `FALSE`합니다. [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize)  
  
### <a name="remarks"></a>설명  
 목록 상자를 사용 하 여 크기 조정 사용 하도록 설정할 수 있습니다는 [CMFCRibbonComboBox::EnableDropDownListResize](#enabledropdownlistresize) 메서드.  
  
##  <a name="onselectitem"></a>  CMFCRibbonComboBox::OnSelectItem  
 사용자가 목록 상자에서 항목을 선택할 때 프레임 워크에서 호출 됩니다.  
  
```  
virtual void OnSelectItem(int nItem);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *nItem*  
 선택한 항목의 인덱스입니다.  
  
### <a name="remarks"></a>설명  
 선택 하는 사용자 입력된을 처리 하려는 경우이 메서드를 재정의 합니다.  
  
##  <a name="removeallitems"></a>  CMFCRibbonComboBox::RemoveAllItems  
 목록 상자에서 모든 항목을 삭제 하 고 편집 상자를 지웁니다.  
  
```  
void RemoveAllItems();
```  
  
### <a name="remarks"></a>설명  
  
##  <a name="selectitem"></a>  CMFCRibbonComboBox::SelectItem  
 목록 상자에서 항목을 선택합니다.  
  
```  
BOOL SelectItem(int iIndex);
BOOL SelectItem(DWORD_PTR dwData);

BOOL SelectItem(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *iIndex*  
 목록 상자에 있는 항목의 0부터 시작 하는 인덱스입니다.  
  
 [in] *dwData*  
 목록 상자에서 항목에 연결 된 데이터입니다.  
  
 [in] *lpszText*  
 목록 상자에 있는 항목의 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE` 메서드가 성공 하면 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>설명  
  
##  <a name="setdropdownheight"></a>  CMFCRibbonComboBox::SetDropDownHeight  
 놓을 때 목록 상자의 높이 설정 합니다.  
  
```  
void SetDropDownHeight(int nHeight);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] *nHeight*  
 목록 상자의 픽셀 단위 높이입니다.  
  
### <a name="remarks"></a>설명  
 기본 높이 150 픽셀입니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonEdit 클래스](../../mfc/reference/cmfcribbonedit-class.md)
