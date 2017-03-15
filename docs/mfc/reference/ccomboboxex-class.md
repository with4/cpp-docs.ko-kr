---
title: "CComboBoxEx 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComboBoxEx
dev_langs:
- C++
helpviewer_keywords:
- extended combo boxes, CComboBoxEx class
- Windows common controls [C++], extended combo boxes
- common controls [C++], extended combo boxes
- combo boxes [C++], CComboBoxEx class
- Internet Explorer 4.0 common controls
- CComboBoxEx class
ms.assetid: 33ca960a-2409-478c-84a4-a2ee8ecfe8f7
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
ms.openlocfilehash: e88ed701111b49e3a5d3b32868bfad8e77206086
ms.lasthandoff: 02/24/2017

---
# <a name="ccomboboxex-class"></a>CComboBoxEx 클래스
이미지 목록에 대한 지원을 제공하여 콤보 상자 컨트롤을 확장합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CComboBoxEx : public CComboBox  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CComboBoxEx::CComboBoxEx](#ccomboboxex)|`CComboBoxEx` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CComboBoxEx::Create](#create)|콤보 상자를 만들고 연결 하는 `CComboBoxEx` 개체입니다.|  
|[CComboBoxEx::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 콤보 상자를 만들고에 연결 된 **ComboBoxEx** 개체입니다.|  
|[CComboBoxEx::DeleteItem](#deleteitem)|항목을 제거는 **ComboBoxEx** 제어 합니다.|  
|[CComboBoxEx::GetComboBoxCtrl](#getcomboboxctrl)|자식 콤보 상자 컨트롤에 대 한 포인터를 검색합니다.|  
|[CComboBoxEx::GetEditCtrl](#geteditctrl)|편집 컨트롤의 부분에 대 한 핸들을 검색 한 **ComboBoxEx** 제어 합니다.|  
|[CComboBoxEx::GetExtendedStyle](#getextendedstyle)|검색에 사용 되는 확장된 스타일을 **ComboBoxEx** 제어 합니다.|  
|[CComboBoxEx::GetImageList](#getimagelist)|에 할당 하는 이미지 목록에 대 한 포인터를 검색 한 **ComboBoxEx** 제어 합니다.|  
|[CComboBoxEx::GetItem](#getitem)|검색 항목에 대 한 정보는 주어진 **ComboBoxEx** 항목입니다.|  
|[CComboBoxEx::HasEditChanged](#haseditchanged)|사용자의 내용을 변경 되었는지 여부 결정은 **ComboBoxEx** 입력 하 여 컨트롤을 편집 합니다.|  
|[CComboBoxEx::InsertItem](#insertitem)|새 항목을 삽입 한 **ComboBoxEx** 제어 합니다.|  
|[CComboBoxEx::SetExtendedStyle](#setextendedstyle)|확장된 스타일 내에서 설정 하는 **ComboBoxEx** 제어 합니다.|  
|[CComboBoxEx::SetImageList](#setimagelist)|이미지 목록에 대 한 설정 하는 **ComboBoxEx** 제어 합니다.|  
|[CComboBoxEx::SetItem](#setitem)|항목에 대해 특성을 설정 된 **ComboBoxEx** 제어 합니다.|  
|[CComboBoxEx::SetWindowTheme](#setwindowtheme)|비주얼 스타일을 확장 된 콤보 상자 컨트롤을 설정합니다.|  
  
## <a name="remarks"></a>주의  
 사용 하 여 `CComboBoxEx` 콤보 상자 컨트롤을 만들려면 더 이상 하려면 사용자 고유의 이미지를 그리기 코드를 구현 합니다. 대신 `CComboBoxEx` 이미지 목록에서 액세스 이미지에 있습니다.  
  
## <a name="image-list-support"></a>이미지 목록 지원  
 표준 콤보 상자에 콤보 상자의 소유자가 소유자 그리기 컨트롤 같은 콤보 상자를 만들어 이미지를 그리기 작업을 담당 합니다. 사용 하는 경우 `CComboBoxEx`, 그리기 스타일을 설정할 필요가 없습니다 **CBS_OWNERDRAWFIXED** 및 **CBS_HASSTRINGS** 암시 된 이러한 때문입니다. 그렇지 않으면 그리기 작업을 수행 하는 코드를 작성 해야 합니다. A `CComboBoxEx` 컨트롤에서는 항목당 최대&3; 개의 이미지: 선택 하지 않은 상태 여 서 및 오버레이 이미지에 대 한 선택 된 상태에 대 한 하나입니다.  
  
## <a name="styles"></a>스타일  
 `CComboBoxEx`스타일을 지 원하는 **CBS_SIMPLE**, **CBS_DROPDOWN**, **CBS_DROPDOWNLIST**, 및 **WS_CHILD**합니다. 창을 만들 때 전달 된 다른 모든 스타일은 컨트롤에 의해 무시 됩니다. 창을 만든 후 수 다른 콤보 상자 스타일 호출 하 여 제공 된 `CComboBoxEx` 멤버 함수 [SetExtendedStyle](#setextendedstyle)합니다. 이러한 스타일을 사용 하면 다음과 같은 작업을 수행할 수 있습니다.  
  
-   대/소문자 구분 되도록 목록에서 문자열 검색을 설정 합니다.  
  
-   콤보 상자 컨트롤 만들기 ('/'), 슬래시를 사용 하는 백슬래시 ('\\'), 기간과 ('. ') 단어 구분 기호로 합니다. 그러면 해당 사용자가 바로 가기 키 CTRL + 화살표를 사용 하 여 단어를 이동할 수 있습니다.  
  
-   콤보 상자 컨트롤을 표시 하거나 이미지를 표시 하지 중 하나를 설정 합니다. 이미지가 표시 되 면 콤보 상자의 이미지를 제공 하는 텍스트 들여쓰기를 제거할 수 있습니다.  
  
-   포함 된 더 넓은 콤보 상자를 자르는 하므로 크기를 포함 하 여 좁은 콤보 상자 컨트롤을 만듭니다.  
  
 이러한 스타일 플래그는에서 더 자세히 설명 [CComboBoxEx 사용 하 여](../../mfc/using-ccomboboxex.md)합니다.  
  
## <a name="item-retention-and-callback-item-attributes"></a>항목 보존 및 콜백 항목 특성  
 항목 정보를 항목 및 이미지, 들여쓰기 값 및 텍스트 문자열에 대 한 인덱스와 같은 Win32 구조에 저장 됩니다 [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 구조에는 콜백 플래그에 해당 하는 멤버가 포함 되어 있습니다.  
  
 개념, 자세한 설명은 [CComboBoxEx 사용 하 여](../../mfc/using-ccomboboxex.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 `CComboBoxEx`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="a-nameccomboboxexa--ccomboboxexccomboboxex"></a><a name="ccomboboxex"></a>CComboBoxEx::CComboBoxEx  
 이 멤버 함수를 만드는 호출을 `CComboBoxEx` 개체입니다.  
  
```  
CComboBoxEx();
```  
  
##  <a name="a-namecreatea--ccomboboxexcreate"></a><a name="create"></a>CComboBoxEx::Create  
 콤보 상자를 만들고 연결 하는 `CComboBoxEx` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 콤보 상자에 적용 되는 콤보 상자 스타일의 조합을 지정 합니다. 참조 **주의** 아래 스타일에 대 한 자세한 내용은 합니다.  
  
 `rect`  
 에 대 한 참조는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 구조 콤보 상자의 크기와 위치를 합니다.  
  
 `pParentWnd`  
 에 대 한 포인터는 [CWnd](../../mfc/reference/cwnd-class.md) 콤보 상자의 부모 창 개체 (일반적으로 `CDialog`). 않아야 **NULL**합니다.  
  
 `nID`  
 콤보 상자 컨트롤 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 개체가 성공적으로 만들어진 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 만들기를 `CComboBoxEx`&2; 단계를 거쳐에서 개체:  
  
1.  호출 [CComboBoxEx](#ccomboboxex) 생성 하는 `CComboBoxEx` 개체입니다.  
  
2.  확장 된 Windows 콤보 상자를 만들고에 연결 하는이 멤버 함수를 호출 하는 `CComboBoxEx` 개체입니다.  
  
 호출 하는 경우 **만들기**, MFC 공용 컨트롤을 초기화 합니다.  
  
 콤보 상자를 만들 때 다음 콤보 상자 스타일 중 일부 또는 모두를 지정할 수 있습니다.  
  
- **CBS_SIMPLE**  
  
- **CBS_DROPDOWN**  
  
- **CBS_DROPDOWNLIST**  
  
- **CBS_AUTOHSCROLL**  
  
- **WS_CHILD**  
  
 창을 만들 때 전달 된 다른 모든 스타일은 무시 됩니다. **ComboBoxEx** 컨트롤은 또한 추가 기능을 제공 하는 확장된 스타일을 지원 합니다. 이러한 스타일에 설명 된 [확장된 스타일을 제어 하는 ComboBoxEx](http://msdn.microsoft.com/library/windows/desktop/bb775742)에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 호출 하 여 이러한 스타일을 설정 [SetExtendedStyle](#setextendedstyle)합니다.  
  
 컨트롤 확장된 창 스타일을 사용 하는 경우 호출할 [CreateEx](#createex) 대신 **만들기**합니다.  
  
##  <a name="a-namecreateexa--ccomboboxexcreateex"></a><a name="createex"></a>CComboBoxEx::CreateEx  
 확장된 된 콤보 상자 컨트롤 (자식 창)을 만들어 사용 하 여 연결 하려면이 함수를 호출 하 여 `CComboBoxEx` 개체입니다.  
  
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
 콤보 상자 컨트롤의 스타일입니다. 참조 [만들기](#create) 스타일의 목록에 대 한 합니다.  
  
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
  
 `CreateEx`지정 된 확장된 창 스타일을 사용 하 여 컨트롤을 만듭니다 `dwExStyle`합니다. 설정 해야 확장된 스타일 특정 사용 하 여 확장 된 콤보 상자 컨트롤 [SetExtendedStyle](#setextendedstyle)합니다. 사용 예를 들어 `CreateEx` 으로 이러한 스타일을 설정 하려면 **WS_EX_CONTEXTHELP**를 사용 하지만 `SetExtendedStyle` 으로 이러한 스타일을 설정 하려면 **CBES_EX_CASESENSITIVE**합니다. 자세한 내용은 항목에서 설명 하는 스타일을 참조 하십시오. [ComboBoxEx 컨트롤 확장 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775742) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namedeleteitema--ccomboboxexdeleteitem"></a><a name="deleteitem"></a>CComboBoxEx::DeleteItem  
 항목을 제거는 **ComboBoxEx** 제어 합니다.  
  
```  
int DeleteItem(int iIndex);
```  
  
### <a name="parameters"></a>매개 변수  
 `iIndex`  
 제거할 항목의&0;부터 시작 인덱스입니다.  
  
### <a name="return-value"></a>반환 값  
 컨트롤에서 남은 항목의 수입니다. 경우 `iIndex` 유효 하지 않거나 함수 반환 **CB_ERR**합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 메시지의 기능을 구현 [CBEM_DELETEITEM](http://msdn.microsoft.com/library/windows/desktop/bb775768)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. DeleteItem, 호출 하는 경우는 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) 메시지를 **CBEN_DELETEITEM** 부모 창에 알림이 전송 됩니다.  
  
##  <a name="a-namegetcomboboxctrla--ccomboboxexgetcomboboxctrl"></a><a name="getcomboboxctrl"></a>CComboBoxEx::GetComboBoxCtrl  
 이 멤버 함수 내에서 콤보 상자 컨트롤에 대 한 단서를 호출 하는 `CComboBoxEx` 개체입니다.  
  
```  
CComboBox* GetComboBoxCtrl();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 `CComboBox` 개체입니다.  
  
### <a name="remarks"></a>주의  
 `CComboBoxEx` 컨트롤을 캡슐화 하는 부모 창을 이루어져는 `CComboBox`합니다.  
  
 `CComboBox` 반환 값은가 가리키는 개체가 임시 개체 이며 다음 유휴 처리 시간 중에 소멸 됩니다.  
  
##  <a name="a-namegeteditctrla--ccomboboxexgeteditctrl"></a><a name="geteditctrl"></a>CComboBoxEx::GetEditCtrl  
 콤보 상자에 대 한 편집 컨트롤에 대 한 포인터를 가져오려는이 멤버 함수를 호출 합니다.  
  
```  
CEdit* GetEditCtrl();
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CEdit](../../mfc/reference/cedit-class.md) 개체입니다.  
  
### <a name="remarks"></a>주의  
 A `CComboBoxEx` 제어를 만들면 편집 상자를 사용 하는 **CBS_DROPDOWN** 스타일입니다.  
  
 `CEdit` 반환 값은가 가리키는 개체가 임시 개체 이며 다음 유휴 처리 시간 중에 소멸 됩니다.  
  
##  <a name="a-namegetextendedstylea--ccomboboxexgetextendedstyle"></a><a name="getextendedstyle"></a>CComboBoxEx::GetExtendedStyle  
 이 멤버 함수에 사용 되는 확장된 스타일을 가져오려는 호출는 `CComboBoxEx` 제어 합니다.  
  
```  
DWORD GetExtendedStyle() const;  
```  
  
### <a name="return-value"></a>반환 값  
 `DWORD` 콤보 상자 컨트롤에 사용 되는 확장된 스타일을 포함 하는 값입니다.  
  
### <a name="remarks"></a>주의  
 참조 [ComboBoxEx 컨트롤 확장 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775742) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 이러한 스타일에 대 한 자세한 내용은 합니다.  
  
##  <a name="a-namegetimagelista--ccomboboxexgetimagelist"></a><a name="getimagelist"></a>CComboBoxEx::GetImageList  
 이 멤버 함수에서 사용 하는 이미지 목록에 대 한 단서를 호출 하는 `CComboBoxEx` 제어 합니다.  
  
```  
CImageList* GetImageList() const;  
```  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CImageList](../../mfc/reference/cimagelist-class.md) 개체입니다. 이 멤버 함수를 반환 하는 경우 실패 **NULL**합니다.  
  
### <a name="remarks"></a>주의  
 `CImageList` 반환 값은가 가리키는 개체가 임시 개체 이며 다음 유휴 처리 시간 중에 소멸 됩니다.  
  
##  <a name="a-namegetitema--ccomboboxexgetitem"></a><a name="getitem"></a>CComboBoxEx::GetItem  
 검색 항목에 대 한 정보는 주어진 **ComboBoxEx** 항목입니다.  
  
```  
BOOL GetItem(COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCBItem`  
 에 대 한 포인터는 [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) 구조를 항목 정보를 받게 됩니다.  
  
### <a name="return-value"></a>반환 값  
 작업에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 메시지의 기능을 구현 [CBEM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775779)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namehaseditchangeda--ccomboboxexhaseditchanged"></a><a name="haseditchanged"></a>CComboBoxEx::HasEditChanged  
 사용자의 내용을 변경 되었는지 여부 결정은 **ComboBoxEx** 입력 하 여 컨트롤을 편집 합니다.  
  
```  
BOOL HasEditChanged();
```  
  
### <a name="return-value"></a>반환 값  
 사용자가 컨트롤의 편집 상자에 입력 한 경우 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 메시지의 기능을 구현 [CBEM_HASEDITCHANGED](http://msdn.microsoft.com/library/windows/desktop/bb775782)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-nameinsertitema--ccomboboxexinsertitem"></a><a name="insertitem"></a>CComboBoxEx::InsertItem  
 새 항목을 삽입 한 **ComboBoxEx** 제어 합니다.  
  
```  
int InsertItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCBItem`  
 에 대 한 포인터는 [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) 구조를 항목 정보를 받게 됩니다. 이 구조는 항목에 대 한 콜백 플래그 값을 포함 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공 하면 새 항목이 삽입 된 인덱스 그렇지 않으면-1입니다.  
  
### <a name="remarks"></a>주의  
 호출 하는 경우 `InsertItem`, [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) 메시지를 [CBEN_INSERTITEM](http://msdn.microsoft.com/library/windows/desktop/bb775764) 부모 창에 알림이 전송 됩니다.  
  
##  <a name="a-namesetextendedstylea--ccomboboxexsetextendedstyle"></a><a name="setextendedstyle"></a>CComboBoxEx::SetExtendedStyle  
 컨트롤 확장 된 콤보 상자에 사용 되는 확장된 스타일을 설정 하려면이 멤버 함수를 호출 합니다.  
  
```  
DWORD SetExtendedStyle(
    DWORD dwExMask,  
    DWORD dwExStyles);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwExMask`  
 A `DWORD` 에 스타일을 나타내는 값 `dwExStyles` 영향을 받이 됩니다. 에 확장된 스타일 `dwExMask` 변경 됩니다. 다른 모든 스타일은 그대로 유지 됩니다. 이 매개 변수는&0; 이면 다음 모든 스타일의 경우 `dwExStyles` 영향을 받게 됩니다.  
  
 `dwExStyles`  
 A `DWORD` 콤보 상자가 포함 된 값 컨트롤 확장된 스타일을 컨트롤에 설정 합니다.  
  
### <a name="return-value"></a>반환 값  
 A `DWORD` 컨트롤에 대해 이전에 사용 되는 확장된 스타일을 포함 하는 값입니다.  
  
### <a name="remarks"></a>주의  
 참조 [ComboBoxEx 컨트롤 확장 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775742) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 이러한 스타일에 대 한 자세한 내용은 합니다.  
  
 확장된 창 스타일을 사용 하 여 제어를 확장 된 콤보 상자를 만들려면 사용 [CreateEx](#createex)합니다.  
  
##  <a name="a-namesetimagelista--ccomboboxexsetimagelist"></a><a name="setimagelist"></a>CComboBoxEx::SetImageList  
 이미지 목록에 대 한 설정 하는 **ComboBoxEx** 제어 합니다.  
  
```  
CImageList* SetImageList(CImageList* pImageList);
```  
  
### <a name="parameters"></a>매개 변수  
 `pImageList`  
 에 대 한 포인터는 `CImageList` 개체와 함께 사용 하 여 이미지를 포함 하는 `CComboBoxEx` 제어 합니다.  
  
### <a name="return-value"></a>반환 값  
 에 대 한 포인터는 [CImageList](../../mfc/reference/cimagelist-class.md) 이전에 사용 되는 이미지가 포함 된 개체는 `CComboBoxEx` 제어 합니다. **NULL** 이미지 목록이 없는 이전에 설정 된 경우.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 메시지의 기능을 구현 [CBEM_SETIMAGELIST](http://msdn.microsoft.com/library/windows/desktop/bb775787)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다. 기본 편집 컨트롤의 높이 변경 하는 경우 Win32 함수 호출 [SetWindowPos](http://msdn.microsoft.com/library/windows/desktop/ms633545) 호출한 후에 사용자 컨트롤 크기를 조정 하려면 `SetImageList`, 또는 제대로 표시 되지 것입니다.  
  
 `CImageList` 반환 값은가 가리키는 개체가 임시 개체 이며 다음 유휴 처리 시간 중에 소멸 됩니다.  
  
##  <a name="a-namesetitema--ccomboboxexsetitem"></a><a name="setitem"></a>CComboBoxEx::SetItem  
 항목에 대해 특성을 설정 된 **ComboBoxEx** 제어 합니다.  
  
```  
BOOL SetItem(const COMBOBOXEXITEM* pCBItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `pCBItem`  
 에 대 한 포인터는 [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746) 구조를 항목 정보를 받게 됩니다.  
  
### <a name="return-value"></a>반환 값  
 작업에 성공 하면 0이 아닌 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 메시지의 기능을 구현 [CBEM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb775788)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="a-namesetwindowthemea--ccomboboxexsetwindowtheme"></a><a name="setwindowtheme"></a>CComboBoxEx::SetWindowTheme  
 비주얼 스타일을 확장 된 콤보 상자 컨트롤을 설정합니다.  
  
```  
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```  
  
### <a name="parameters"></a>매개 변수  
 `pszSubAppName`  
 설정 하는 확장 된 콤보 상자 비주얼 스타일을 포함 하는 유니코드 문자열에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 값은 사용 되지 않습니다.  
  
### <a name="remarks"></a>주의  
 기능을 에뮬레이션 하는이 멤버 함수는 [CBEM_SETWINDOWTHEME](http://msdn.microsoft.com/library/windows/desktop/bb775790) 에 설명 된 대로 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 MFCIE](../../visual-cpp-samples.md)   
 [CComboBox 클래스](../../mfc/reference/ccombobox-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CComboBox 클래스](../../mfc/reference/ccombobox-class.md)

