---
title: "CVSListBox 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CVSListBox
dev_langs:
- C++
helpviewer_keywords:
- CVSListBox::PreTranslateMessage method
- CVSListBox class
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
caps.latest.revision: 30
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
ms.openlocfilehash: 4527249fc1a22a1db0623ea46954065fcbd071f4
ms.lasthandoff: 02/24/2017

---
# <a name="cvslistbox-class"></a>CVSListBox 클래스
`CVSListBox` 클래스는 편집 가능한 목록 컨트롤을 지원 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CVSListBox : public CVSListBoxBase  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CVSListBox::CVSListBox](#cvslistbox)|`CVSListBox` 개체를 생성합니다.|  
|`CVSListBox::~CVSListBox`|소멸자|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CVSListBox::AddItem](#additem)|목록 컨트롤에 문자열을 추가 합니다. (`CVSListBoxBase::AddItem`를 재정의합니다.)|  
|[CVSListBox::EditItem](#edititem)|목록 컨트롤 항목의 텍스트에서 편집 작업을 시작 합니다. (`CVSListBoxBase::EditItem`를 재정의합니다.)|  
|[CVSListBox::GetCount](#getcount)|편집할 수 있는 목록 컨트롤에서 문자열의 수를 검색합니다. (`CVSListBoxBase::GetCount`를 재정의합니다.)|  
|[CVSListBox::GetItemData](#getitemdata)|편집할 수 있는 목록 컨트롤 항목에 연결 하는 응용 프로그램별 32 비트 값을 검색 합니다. (`CVSListBoxBase::GetItemData`를 재정의합니다.)|  
|[CVSListBox::GetItemText](#getitemtext)|편집 가능한 목록 컨트롤 항목의 텍스트를 검색합니다. (`CVSListBoxBase::GetItemText`를 재정의합니다.)|  
|[CVSListBox::GetSelItem](#getselitem)|편집할 수 있는 목록 컨트롤에서 현재 선택 된 항목의&0;부터 시작 인덱스를 검색합니다. (`CVSListBoxBase::GetSelItem`를 재정의합니다.)|  
|`CVSListBox::PreTranslateMessage`|창 메시지를 변환 하 여으로 디스패치 되기 전에 [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows 함수입니다. 자세한 내용 및 메서드 구문에 대 한 참조 [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)합니다. (`CVSListBoxBase::PreTranslateMessage`를 재정의합니다.)|  
|[CVSListBox::RemoveItem](#removeitem)|편집할 수 있는 목록 컨트롤에서 항목을 제거 합니다. (`CVSListBoxBase::RemoveItem`를 재정의합니다.)|  
|[CVSListBox::SelectItem](#selectitem)|편집 가능한 목록 제어 문자열을 선택합니다. (`CVSListBoxBase::SelectItem`를 재정의합니다.)|  
|[CVSListBox::SetItemData](#setitemdata)|편집할 수 있는 목록 컨트롤 항목으로는 응용 프로그램별 32 비트 값을 연결합니다. (`CVSListBoxBase::SetItemData`를 재정의합니다.)|  
  
### <a name="protected-methods"></a>Protected 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CVSListBox::GetListHwnd](#getlisthwnd)|현재 포함 된 목록 뷰 컨트롤에 핸들을 반환 합니다.|  
  
## <a name="remarks"></a>주의  
 `CVSListBox` 클래스 사용자 만들기, 수정, 삭제 또는 목록 컨트롤에서 항목을 다시 정렬할 수 있는 편집 단추 집합을 제공 합니다.  
  
 다음은 편집할 수 있는 목록 컨트롤의 그림입니다. "Item2" 제목은, 두 번째 목록 항목을 편집 하기 위해 선택 됩니다.  
  
 ![CVSListBox 컨트롤](../../mfc/reference/media/cvslistbox.png "cvslistbox")  
  
 리소스 편집기를 사용 하 여 편집할 수 있는 목록 컨트롤을 추가 하려면 다음에 유의 **도구 상자** 편집기의 창 편집할 수 있는 미리 정의 된 목록 컨트롤을 제공 하지 않습니다. 대신,와 같은 정적 컨트롤을 추가 **그룹 상자** 제어 합니다. 프레임 워크를 사용 하 여 정적 컨트롤 자리 표시자로 편집할 수 있는 목록 컨트롤의 위치와 크기를 지정 합니다.  
  
 대화 상자 템플릿에 편집 가능한 목록 컨트롤을 사용 하려면 선언는 `CVSListBox` 대화 상자 클래스에서 변수입니다. 를 지원 하기 위해 변수와 컨트롤 간의 데이터 교환을 정의 `DDX_Control` 매크로 항목에는 `DoDataExchange` 대화 상자의 메서드. 기본적으로 편집할 수 있는 목록 컨트롤 편집 단추 없이 생성 됩니다. 편집 단추를 사용 하도록 설정 하려면 상속 된 CVSListBoxBase::SetStandardButtons 메서드를 사용 합니다.  
  
 자세한 내용은 예제 디렉터리를 참조 하십시오.는 `New Controls` Page3.cpp 및 Page3.h 파일을 샘플링 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CStatic](../../mfc/reference/cstatic-class.md)  
  
 `CVSListBoxBase`  
  
 [CVSListBox](../../mfc/reference/cvslistbox-class.md)  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxvslistbox.h  
  
##  <a name="a-nameadditema--cvslistboxadditem"></a><a name="additem"></a>CVSListBox::AddItem  
 목록 컨트롤에 문자열을 추가 합니다.  
  
```  
virtual int AddItem(
    const CString& strIext,  
    DWORD_PTR dwData=0,  
    int iIndex=-1);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `strIext`  
 문자열에 대 한 참조입니다.  
  
 [in] `dwData`  
 문자열 연결 되는 응용 프로그램별 32 비트 값입니다. 기본값은 0입니다.  
  
 [in] `iIndex`  
 문자열을 보유 하는 위치의&0;부터 시작 하는 인덱스입니다. 하는 경우는 `iIndex` 매개 변수는-1, 문자열 목록의 끝에 추가 됩니다. 기본값은 -1입니다.  
  
### <a name="return-value"></a>반환 값  
 목록 컨트롤에서 문자열의 위치의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="remarks"></a>주의  
 사용 된 [CVSListBox::GetItemData](#getitemdata) 로 지정 된 값을 검색 하는 메서드는 `dwData` 매개 변수입니다. 이 값은 응용 프로그램별 정수 또는 다른 데이터에 대 한 포인터를 수 있습니다.  
  
##  <a name="a-namecvslistboxa--cvslistboxcvslistbox"></a><a name="cvslistbox"></a>CVSListBox::CVSListBox  
 `CVSListBox` 개체를 생성합니다.  
  
```  
CVSListBox();
```  
  
### <a name="return-value"></a>반환 값  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameedititema--cvslistboxedititem"></a><a name="edititem"></a>CVSListBox::EditItem  
 목록 컨트롤 항목의 텍스트에서 편집 작업을 시작 합니다.  
  
```  
virtual BOOL EditItem(int iIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iIndex`  
 목록 컨트롤 항목의&0;부터 시작 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`편집 작업이 성공적으로 시작 하는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
 사용자가 편집 작업을 시작 항목의 레이블을 두 번 클릭 하거나 눌러는 **F2** 또는 **스페이스바** 항목에 포커스가 있을 때 키입니다.  
  
##  <a name="a-namegetcounta--cvslistboxgetcount"></a><a name="getcount"></a>CVSListBox::GetCount  
 편집할 수 있는 목록 컨트롤에서 문자열의 수를 검색합니다.  
  
```  
virtual int GetCount() const;  
```  
  
### <a name="return-value"></a>반환 값  
 목록 컨트롤의 항목 수입니다.  
  
### <a name="remarks"></a>주의  
 Note 수가 인지 마지막 항목의 인덱스 값 보다&1; 씩 증가 하므로 인덱스는&0;부터 시작 합니다.  
  
##  <a name="a-namegetitemdataa--cvslistboxgetitemdata"></a><a name="getitemdata"></a>CVSListBox::GetItemData  
 편집할 수 있는 목록 컨트롤 항목에 연결 하는 응용 프로그램별 32 비트 값을 검색 합니다.  
  
```  
virtual DWORD_PTR GetItemData(int iIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iIndex`  
 편집 가능한 목록 컨트롤 항목의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 항목에 연결 하는 32 비트 값입니다.  
  
### <a name="remarks"></a>주의  
 사용 된 [CVSListBox::SetItemData](#setitemdata) 또는 [CVSListBox::AddItem](#additem) 목록 컨트롤 항목으로 32 비트 값을 연결 하는 방법이 있습니다. 이 값은 응용 프로그램별 정수 또는 다른 데이터에 대 한 포인터를 수 있습니다.  
  
##  <a name="a-namegetitemtexta--cvslistboxgetitemtext"></a><a name="getitemtext"></a>CVSListBox::GetItemText  
 편집 가능한 목록 컨트롤 항목의 텍스트를 검색합니다.  
  
```  
virtual CString GetItemText(int iIndex) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iIndex`  
 편집 가능한 목록 컨트롤 항목의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) 지정된 된 항목의 텍스트가 포함 된 개체입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-namegetlisthwnda--cvslistboxgetlisthwnd"></a><a name="getlisthwnd"></a>CVSListBox::GetListHwnd  
 현재 포함 된 목록 뷰 컨트롤에 핸들을 반환 합니다.  
  
```  
virtual HWND GetListHwnd() const;  
```  
  
### <a name="return-value"></a>반환 값  
 포함 된 목록 뷰 컨트롤에 대 한 핸들입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드를 사용 하 여 지 원하는 포함 된 목록 뷰 컨트롤에 대 한 핸들을 검색 하는 `CVSListBox` 클래스입니다.  
  
##  <a name="a-namegetselitema--cvslistboxgetselitem"></a><a name="getselitem"></a>CVSListBox::GetSelItem  
 편집할 수 있는 목록 컨트롤에서 현재 선택 된 항목의&0;부터 시작 인덱스를 검색합니다.  
  
```  
virtual int GetSelItem() const;  
```  
  
### <a name="return-value"></a>반환 값  
 이 메서드는 성공 하는 경우 현재 선택 된 항목;의&0;부터 시작 하는 인덱스 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameremoveitema--cvslistboxremoveitem"></a><a name="removeitem"></a>CVSListBox::RemoveItem  
 편집할 수 있는 목록 컨트롤에서 항목을 제거 합니다.  
  
```  
virtual BOOL RemoveItem(int iIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iIndex`  
 편집 가능한 목록 컨트롤 항목의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 `TRUE`지정된 된 항목이 제거 되는 경우 그렇지 않으면 `FALSE`합니다.  
  
### <a name="remarks"></a>주의  
  
##  <a name="a-nameselectitema--cvslistboxselectitem"></a><a name="selectitem"></a>CVSListBox::SelectItem  
 편집 가능한 목록 제어 문자열을 선택합니다.  
  
```  
virtual BOOL SelectItem(int iItem);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iItem`  
 편집 가능한 목록 컨트롤 항목의&0;부터 시작 하는 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 이 메서드가 성공적으로 수행되면 `TRUE`이고, 그렇지 않으면 `FALSE`입니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 지정된 된 항목을 선택 하 고, 필요한 경우 항목을 뷰로 스크롤합니다.  
  
##  <a name="a-namesetitemdataa--cvslistboxsetitemdata"></a><a name="setitemdata"></a>CVSListBox::SetItemData  
 편집할 수 있는 목록 컨트롤 항목으로는 응용 프로그램별 32 비트 값을 연결합니다.  
  
```  
virtual void SetItemData(
    int iIndex,  
    DWORD_PTR dwData);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `iIndex`  
 편집 가능한 목록 컨트롤 항목의&0;부터 시작 하는 인덱스입니다.  
  
 [in] `dwData`  
 32 비트 값입니다. 이 값은 응용 프로그램별 정수 또는 다른 데이터에 대 한 포인터를 수 있습니다.  
  
### <a name="remarks"></a>주의  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [클래스](../../mfc/reference/mfc-classes.md)

