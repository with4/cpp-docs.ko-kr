---
title: "CDragListBox 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDragListBox
dev_langs:
- C++
helpviewer_keywords:
- drag list box [C++]
- dragging list items
- CDragListBox class
- Windows [C++], list boxes
- list boxes
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
caps.latest.revision: 24
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
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 3010fd9a363aa1ca1c946a6fe967a7ba415649d4
ms.lasthandoff: 02/24/2017

---
# <a name="cdraglistbox-class"></a>CDragListBox 클래스
Windows 목록 상자의 기능을 제공 하는 것 외에도 `CDragListBox` 클래스 목록 상자 내에서 파일 이름과 같은 목록 상자 항목을 이동할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CDragListBox : public CListBox  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CDragListBox::CDragListBox](#cdraglistbox)|`CDragListBox` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CDragListBox::BeginDrag](#begindrag)|끌기 작업이 시작 될 때 프레임 워크에서 호출 합니다.|  
|[CDragListBox::CancelDrag](#canceldrag)|끌기 작업이 취소 된 때 프레임 워크에서 호출 합니다.|  
|[CDragListBox::Dragging](#dragging)|끌기 작업 중의 프레임 워크에서 호출 합니다.|  
|[CDragListBox::DrawInsert](#drawinsert)|끌어서 목록 상자의 삽입 안내선을 그립니다.|  
|[CDragListBox::Dropped](#dropped)|항목 삭제 된 후 프레임 워크에 의해 호출 됩니다.|  
|[CDragListBox::ItemFromPt](#itemfrompt)|끌고 있는 항목의 좌표를 반환 합니다.|  
  
## <a name="remarks"></a>주의  
 이 기능으로 목록 상자는 게 가장 유용한 방식으로 목록에서 항목을 주문를 수 있습니다. 기본적으로 목록 상자는 항목 목록에서 새 위치로 이동 합니다. 그러나 `CDragListBox` 이동 하지 않고 항목을 복사 하려면 개체를 사용자 지정할 수 있습니다.  
  
 와 연결 된 목록 상자 컨트롤에서 `CDragListBox` 클래스에 있어서는 안는 **LBS_SORT** 또는 **LBS_MULTIPLESELECT** 스타일입니다. 목록 상자 스타일에 대 한 참조 [목록 상자 스타일](../../mfc/reference/list-box-styles.md)합니다.  
  
 응용 프로그램의 기존 대화 상자에서 끌어 목록 상자를 사용 하려면 대화 상자 편집기를 사용 하 여 대화 상자 템플릿에 목록 상자 컨트롤을 추가 하 고 다음 멤버 변수를 할당 (범주의 `Control` 및 변수 유형 `CDragListBox`) 대화 상자 템플릿에서 목록 상자 컨트롤에 해당 합니다.  
  
 컨트롤을 멤버 변수에 할당에 대 한 자세한 내용은 참조 하십시오. [대화 상자 컨트롤 멤버 변수 정의 대 한 바로 가기](../../windows/defining-member-variables-for-dialog-controls.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CDragListBox`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="a-namebegindraga--cdraglistboxbegindrag"></a><a name="begindrag"></a>CDragListBox::BeginDrag  
 에 의해 호출 프레임 워크는 이벤트가 발생 하는 경우 마우스 왼쪽된 단추를 누르는 것과 같은 끌기 작업을 시작할 수 있습니다.  
  
```  
virtual BOOL BeginDrag(CPoint pt);
```  
  
### <a name="parameters"></a>매개 변수  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 끌고 있는 항목의 좌표를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 이 속성을 0이 아닌 끌어 허용 된 경우, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 끌기 작업이 시작 될 때의 결과 제어 하려는 경우이 함수를 재정의 합니다. 기본 구현에서 마우스를 캡처할 하 고 마우스 왼쪽 또는 오른쪽 단추를 클릭 하거나 끌어서 작업이 취소 되는 시점 esc 키를 누를 때까지 끌기 모드에서 제공 됩니다.  
  
##  <a name="a-namecanceldraga--cdraglistboxcanceldrag"></a><a name="canceldrag"></a>CDragListBox::CancelDrag  
 끌기 작업이 취소 된 때 프레임 워크에서 호출 합니다.  
  
```  
virtual void CancelDrag(CPoint pt);
```  
  
### <a name="parameters"></a>매개 변수  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 끌고 있는 항목의 좌표를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 목록 상자 컨트롤에 대 한 특수 처리를 처리 하려면이 함수를 재정의 합니다.  
  
##  <a name="a-namecdraglistboxa--cdraglistboxcdraglistbox"></a><a name="cdraglistbox"></a>CDragListBox::CDragListBox  
 `CDragListBox` 개체를 생성합니다.  
  
```  
CDragListBox();
```  
  
##  <a name="a-namedragginga--cdraglistboxdragging"></a><a name="dragging"></a>CDragListBox::Dragging  
 내에서 목록 상자 항목을 끌 때 프레임 워크에 의해 호출 된 `CDragListBox` 개체입니다.  
  
```  
virtual UINT Dragging(CPoint pt);
```  
  
### <a name="parameters"></a>매개 변수  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) x 및 y를 포함 하는 개체는 커서의 좌표가 화면입니다.  
  
### <a name="return-value"></a>반환 값  
 표시할 커서의 리소스 ID입니다. 다음 값이 가능 합니다.  
  
- `DL_COPYCURSOR`항목을 복사할 것을 나타냅니다.  
  
- `DL_MOVECURSOR`항목을 이동할 수는 나타냅니다.  
  
- `DL_STOPCURSOR`현재 놓기 대상 허용 하지 않음을 나타냅니다.  
  
### <a name="remarks"></a>주의  
 기본 동작을 반환 `DL_MOVECURSOR`합니다. 추가 기능을 제공 하려는 경우이 함수를 재정의 합니다.  
  
##  <a name="a-namedrawinserta--cdraglistboxdrawinsert"></a><a name="drawinsert"></a>CDragListBox::DrawInsert  
 지정 된 인덱스에 있는 항목 앞에 삽입 안내선을 그리는 데 프레임 워크에 의해 호출 됩니다.  
  
```  
virtual void DrawInsert(int nItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `nItem`  
 삽입 지점의&0;부터 시작 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 값은-1 삽입 안내선을 지웁니다. 모양 또는 삽입이 가이드의 동작을 수정 하려면이 함수를 재정의 합니다.  
  
##  <a name="a-namedroppeda--cdraglistboxdropped"></a><a name="dropped"></a>CDragListBox::Dropped  
 프레임 워크 내에서 항목을 삭제할 때 호출 된 `CDragListBox` 개체입니다.  
  
```  
virtual void Dropped(
    int nSrcIndex,  
    CPoint pt);
```  
  
### <a name="parameters"></a>매개 변수  
 *nSrcIndex*  
 삭제 된 문자열의&0;부터 시작 하는 인덱스를 지정합니다.  
  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 저장 사이트의 좌표를 포함 하는 개체입니다.  
  
### <a name="remarks"></a>주의  
 새 위치를 목록 상자 항목 및 해당 데이터를 복사 하 고 원래 항목을 삭제 하는 기본 동작입니다. 목록 내에서 다른 위치로 끌 수 있는 목록 상자 항목의 복사본을 사용할 수 있는 등의 기본 동작을 사용자 지정 하려면이 함수를 재정의 합니다.  
  
##  <a name="a-nameitemfrompta--cdraglistboxitemfrompt"></a><a name="itemfrompt"></a>CDragListBox::ItemFromPt  
 에 있는 목록 상자 항목의&0;부터 시작 하는 인덱스를 검색 하려면이 함수 호출 `pt`합니다.  
  
```  
int ItemFromPt(
    CPoint pt,  
    BOOL bAutoScroll = TRUE) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 목록 상자 내에서 한 점의 좌표를 포함 하는 개체입니다.  
  
 *bAutoScroll*  
 이 속성을 0이 아닌 스크롤 허용 된 경우, 그렇지 않으면 0입니다.  
  
### <a name="return-value"></a>반환 값  
 끌어서 목록 상자 항목의&0;부터 시작 인덱스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [TSTCON MFC 샘플](../../visual-cpp-samples.md)   
 [CListBox 클래스](../../mfc/reference/clistbox-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CListBox 클래스](../../mfc/reference/clistbox-class.md)

