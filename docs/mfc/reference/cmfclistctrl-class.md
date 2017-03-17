---
title: "CMFCListCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl::EnableMarkSortedColumn
- AFXLISTCTRL/CMFCListCtrl::EnableMultipleSort
- AFXLISTCTRL/CMFCListCtrl::GetHeaderCtrl
- AFXLISTCTRL/CMFCListCtrl::IsMultipleSort
- AFXLISTCTRL/CMFCListCtrl::OnCompareItems
- AFXLISTCTRL/CMFCListCtrl::OnGetCellBkColor
- AFXLISTCTRL/CMFCListCtrl::OnGetCellFont
- AFXLISTCTRL/CMFCListCtrl::OnGetCellTextColor
- AFXLISTCTRL/CMFCListCtrl::RemoveSortColumn
- AFXLISTCTRL/CMFCListCtrl::SetSortColumn
- AFXLISTCTRL/CMFCListCtrl::Sort
dev_langs:
- C++
helpviewer_keywords:
- CMFCListCtrl class
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
caps.latest.revision: 29
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
ms.openlocfilehash: 3a4c67b2d7ea2a5356f7c053403edf414319a928
ms.lasthandoff: 02/24/2017

---
# <a name="cmfclistctrl-class"></a>CMFCListCtrl 클래스
`CMFCListCtrl` 클래스의 기능을 확장 [CListCtrl 클래스](../../mfc/reference/clistctrl-class.md) 의 고급 헤더 컨트롤 기능을 지원 하 여 클래스는 [CMFCHeaderCtrl 클래스](../../mfc/reference/cmfcheaderctrl-class.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMFCListCtrl::EnableMarkSortedColumn](#enablemarksortedcolumn)|다른 배경색으로 정렬 된 열을 표시할 수가 있습니다.|  
|[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)|여러 정렬 모드를 활성화 합니다.|  
|[CMFCListCtrl::GetHeaderCtrl](#getheaderctrl)|밑줄이 그어진된 헤더 컨트롤에 대 한 참조를 반환합니다.|  
|[CMFCListCtrl::IsMultipleSort](#ismultiplesort)|목록 컨트롤에 여러 정렬 모드 인지 확인 합니다.|  
|[CMFCListCtrl::OnCompareItems](#oncompareitems)|두 개의 목록 컨트롤 항목을 비교 해야 하는 경우에 프레임 워크에서 호출 합니다.|  
|[CMFCListCtrl::OnGetCellBkColor](#ongetcellbkcolor)|개별 셀의 배경색을 결정 해야 할 때에 프레임 워크에서 호출 합니다.|  
|[CMFCListCtrl::OnGetCellFont](#ongetcellfont)|그리고 있는 셀에 대 한 글꼴을 얻어야 하는 경우에 프레임 워크에서 호출 합니다.|  
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|개별 셀의 텍스트 색을 결정 해야 할 때에 프레임 워크에서 호출 합니다.|  
|[CMFCListCtrl::RemoveSortColumn](#removesortcolumn)|정렬 된 열 목록에서 정렬 열을 제거합니다.|  
|[CMFCListCtrl::SetSortColumn](#setsortcolumn)|현재 정렬 된 열 및 정렬 순서를 설정합니다.|  
|[CMFCListCtrl::Sort](#sort)|목록 컨트롤을 정렬합니다.|  
  
## <a name="remarks"></a>주의  
 `CMFCListCtrl`에 두 가지 향상 된 기능과 [CListCtrl 클래스](../../mfc/reference/clistctrl-class.md) 클래스입니다. 첫째, 열 정렬을 지 사용 가능한 옵션 헤더에 자동으로 정렬 화살표를 그리기를 나타냅니다. 둘째, 동시에 여러 열에 대해 정렬 하는 데이터를 지원 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `CMFCListCtrl` 클래스에서 다양한 메서드를 사용하는 방법을 보여 줍니다. 목록 컨트롤을 만들, 열을 삽입, 항목을 삽입 한 항목의 텍스트를 설정 및 목록 컨트롤의 글꼴을 설정 하는 방법을 보여 줍니다. 이 코드 조각은의 일부인는 [Visual Studio 데모 샘플](../../visual-cpp-samples.md)합니다.  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo #&25;](../../mfc/codesnippet/cpp/cmfclistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo #&26;](../../mfc/codesnippet/cpp/cmfclistctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxlistctrl.h  
  
##  <a name="enablemarksortedcolumn"></a>CMFCListCtrl::EnableMarkSortedColumn  
 다른 배경색으로 정렬 된 열을 표시합니다.  
  
```  
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bMark`  
 다른 배경색을 사용 하도록 설정할지 여부를 결정 하는 부울 매개 변수입니다.  
  
 [in] `bRedraw`  
 컨트롤을 즉시 다시 그리도록 여부를 결정 하는 부울 매개 변수입니다.  
  
### <a name="remarks"></a>주의  
 `EnableMarkSortedColumn`메서드를 사용 하 여 `CDrawingManager::PixelAlpha` 정렬 된 열에 사용할 색을 계산 합니다. 선택한 색은 일반 배경색을 기반으로 합니다.  
  
##  <a name="enablemultiplesort"></a>CMFCListCtrl::EnableMultipleSort  
 여러 열 목록 컨트롤에서 데이터의 행을 정렬할 수 있습니다.  
  
```  
void EnableMultipleSort(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `bEnable`  
 여러 열 정렬 모드를 사용 하도록 설정할지 여부를 지정 하는 부울입니다.  
  
### <a name="remarks"></a>주의  
 여러 열에 따라 정렬 사용 하도록 설정 하면 열 계층이 필요가 있습니다. 데이터 행을 기본 열에 의해 먼저 정렬 됩니다. 그런 다음 해당 하는 모든 값 우선 순위에 따라 각 후속 열 정렬 됩니다.  
  
##  <a name="getheaderctrl"></a>CMFCListCtrl::GetHeaderCtrl  
 헤더 컨트롤에 대 한 참조를 반환합니다.  
  
```  
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```  
  
### <a name="return-value"></a>반환 값  
 기본에 대 한 참조 [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 목록 컨트롤에 대 한 헤더 컨트롤에 열 제목을 포함 하는 창입니다. 일반적으로 열 바로 위에 배치 됩니다.  
  
##  <a name="ismultiplesort"></a>CMFCListCtrl::IsMultipleSort  
 목록 컨트롤의 현재에서 정렬을 지원 하는지를 여러 열에 대해 확인 합니다.  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `TRUE`목록 컨트롤에 여러 정렬; 지 원하는 경우 `FALSE` 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 경우는 [CMFCListCtrl 클래스](../../mfc/reference/cmfclistctrl-class.md) 여러 정렬을 지 원하는 사용자 여러 열 목록 컨트롤에서 데이터를 정렬할 수 있습니다. 여러 정렬 기능을 사용 하려면 호출 [CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)합니다.  
  
##  <a name="oncompareitems"></a>CMFCListCtrl::OnCompareItems  
 프레임 워크는 두 개의 항목을 비교 하는 경우이 메서드를 호출 합니다.  
  
```  
virtual int OnCompareItems(
    LPARAM lParam1,  
    LPARAM lParam2,  
    int iColumn);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `lParam1`  
 비교할 첫 번째 항목입니다.  
  
 [in] `lParam2`  
 비교할 두 번째 항목입니다.  
  
 [in] `iColumn`  
 이 메서드는 정렬 된 열의 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 이 두 항목의 상대 위치를 나타내는 정수입니다. 음수 값을 첫 번째 항목 두 번째 앞에 야 양수 값 이면 첫 번째 항목 두 번째 따라야 하 고&0; 이면이 두 항목은 동일 나타냅니다.  
  
### <a name="remarks"></a>주의  
 기본 구현에서는 항상 0을 반환합니다. 정렬 알고리즘을 제공 하려면이 함수를 재정의 해야 합니다.  
  
##  <a name="ongetcellbkcolor"></a>CMFCListCtrl::OnGetCellBkColor  
 프레임 워크는 개별 셀의 배경색을 결정 해야 할 때이 메서드를 호출 합니다.  
  
```  
virtual COLORREF OnGetCellBkColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nRow`  
 문제의 셀의 행입니다.  
  
 [in] `nColumn`  
 문제의 셀의 열입니다.  
  
### <a name="return-value"></a>반환 값  
 A `COLOREF` 셀의 배경색을 지정 하는 값입니다.  
  
### <a name="remarks"></a>주의  
 기본 구현은 `OnGetCellBkColor` 제공된 된 입력된 매개 변수를 사용 하지 않는 한 대신 호출 `GetBkColor`합니다. 따라서 기본적으로 전체 목록 컨트롤에는 동일한 배경색을 갖게 됩니다. 재정의할 수 `OnGetCellBkColor` 별도 배경색으로 개별 셀을 표시 하는 파생된 클래스에 있습니다.  
  
##  <a name="ongetcellfont"></a>CMFCListCtrl::OnGetCellFont  
 프레임 워크는 개별 셀에 대 한 글꼴 얻을 경우이 메서드를 호출 합니다.  
  
```  
virtual HFONT OnGetCellFont(
    int nRow,  
    int nColumn,  
    DWORD dwData = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nRow`  
 문제의 셀의 행입니다.  
  
 [in] `nColumn`  
 문제의 셀의 열입니다.  
  
 [in] `dwData`  
 사용자 정의 데이터입니다. 기본 구현에서는이 매개 변수를 사용 하지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 현재 셀에 사용 되는 글꼴에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로이 메서드는 다음과 같이 반환 됩니다. `NULL`합니다. 목록 컨트롤의 셀 모두에 동일한 글꼴이 되어 있습니다. 다른 셀에 대 한 다양 한 글꼴을 제공 하기 위해이 메서드를 재정의 합니다.  
  
##  <a name="ongetcelltextcolor"></a>CMFCListCtrl::OnGetCellTextColor  
 프레임 워크는 개별 셀의 텍스트 색을 결정 해야 할 때이 메서드를 호출 합니다.  
  
```  
virtual COLORREF OnGetCellTextColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `nRow`  
 문제의 셀의 행입니다.  
  
 [in] `nColumn`  
 문제의 셀의 열입니다.  
  
### <a name="return-value"></a>반환 값  
 A `COLOREF` 셀의 텍스트 색을 지정 하는 값입니다.  
  
### <a name="remarks"></a>주의  
 기본적으로이 메서드는 다음과 같이 호출 됩니다. `GetTextColor` 에 관계 없이 입력된 매개 변수입니다. 전체 목록 컨트롤에는 동일한 텍스트 색을 갖게 됩니다. 재정의할 수 `OnGetCellTextColor` 개별 셀을 별도 텍스트 색을 표시 하는 파생된 클래스에 있습니다.  
  
##  <a name="removesortcolumn"></a>CMFCListCtrl::RemoveSortColumn  
 정렬 된 열 목록에서 정렬 열을 제거합니다.  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iColumn`  
 제거할 열입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 헤더 컨트롤에서 정렬 열을 제거합니다. 호출 [CMFCHeaderCtrl::RemoveSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn)합니다.  
  
##  <a name="setsortcolumn"></a>CMFCListCtrl::SetSortColumn  
 현재 정렬 된 열 및 정렬 순서를 설정합니다.  
  
```  
void SetSortColumn(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iColumn`  
 열 정렬입니다.  
  
 [in] `bAscending`  
 정렬 순서를 지정 하는 부울입니다.  
  
 [in] `bAdd`  
 메서드가로 표시 된 열을 추가 하는지 여부를 지정 하는 부울 `iColumn` 정렬 열 목록에 있습니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 메서드를 사용 하 여 헤더 컨트롤에 입력된 매개 변수를 전달 [CMFCHeaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn)합니다.  
  
##  <a name="sort"></a>CMFCListCtrl::Sort  
 목록 컨트롤을 정렬합니다.  
  
```  
virtual void Sort(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iColumn`  
 열 정렬입니다.  
  
 [in] `bAscending`  
 정렬 순서를 지정 하는 부울입니다.  
  
 [in] `bAdd`  
 이 메서드가로 표시 된 열을 추가 하는지 여부를 지정 하는 부울 `iColumn` 정렬 열 목록에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)   
 [CListCtrl 클래스](../../mfc/reference/clistctrl-class.md)

