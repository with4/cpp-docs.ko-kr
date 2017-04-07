---
title: "CLinkCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLinkCtrl
- AFXCMN/CLinkCtrl
- AFXCMN/CLinkCtrl::CLinkCtrl
- AFXCMN/CLinkCtrl::Create
- AFXCMN/CLinkCtrl::CreateEx
- AFXCMN/CLinkCtrl::GetIdealHeight
- AFXCMN/CLinkCtrl::GetIdealSize
- AFXCMN/CLinkCtrl::GetItem
- AFXCMN/CLinkCtrl::GetItemID
- AFXCMN/CLinkCtrl::GetItemState
- AFXCMN/CLinkCtrl::GetItemUrl
- AFXCMN/CLinkCtrl::HitTest
- AFXCMN/CLinkCtrl::SetItem
- AFXCMN/CLinkCtrl::SetItemID
- AFXCMN/CLinkCtrl::SetItemState
- AFXCMN/CLinkCtrl::SetItemUrl
dev_langs:
- C++
helpviewer_keywords:
- CLinkCtrl class
- Web pages, link control
- controls [MFC], links
- links [C++], link control
- SysLink control
ms.assetid: d1cd876a-ecca-42db-8ac4-9cd327df0cd4
caps.latest.revision: 23
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
ms.openlocfilehash: 710fef79306c906e13e99beac15401835422ecbe
ms.lasthandoff: 02/24/2017

---
# <a name="clinkctrl-class"></a>CLinkCtrl 클래스
Windows의 공용 SysLink 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CLinkCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CLinkCtrl::CLinkCtrl](#clinkctrl)|`CLinkCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CLinkCtrl::Create](#create)|링크 컨트롤을 만들고이에 연결 된 `CLinkCtrl` 개체입니다.|  
|[CLinkCtrl::CreateEx](#createex)|확장된 스타일을 사용 하 여 링크 컨트롤을 만들고에 연결 된 `CLinkCtrl` 개체입니다.|  
|[CLinkCtrl::GetIdealHeight](#getidealheight)|링크 컨트롤의 이상적인 높이 검색합니다.|  
|[CLinkCtrl::GetIdealSize](#getidealsize)|링크의 지정된 된 너비에 따라 현재 링크 컨트롤에 대 한 링크 텍스트의 기본 설정된 높이 계산합니다.|  
|[CLinkCtrl::GetItem](#getitem)|상태 및 링크 컨트롤 항목의 특성을 검색합니다.|  
|[CLinkCtrl::GetItemID](#getitemid)|링크 컨트롤 항목의 ID를 검색합니다.|  
|[CLinkCtrl::GetItemState](#getitemstate)|링크 컨트롤 항목의 상태를 검색합니다.|  
|[CLinkCtrl::GetItemUrl](#getitemurl)|링크 컨트롤 항목으로 표현 하는 URL을 검색 합니다.|  
|[CLinkCtrl::HitTest](#hittest)|사용자 지정된 된 링크를 클릭 했는지 여부를 결정 합니다.|  
|[CLinkCtrl::SetItem](#setitem)|상태를 설정 하는 링크 컨트롤 항목의 특성입니다.|  
|[CLinkCtrl::SetItemID](#setitemid)|링크 컨트롤 항목의 ID를 설정합니다.|  
|[CLinkCtrl::SetItemState](#setitemstate)|링크 컨트롤 항목의 상태를 설정합니다.|  
|[CLinkCtrl::SetItemUrl](#setitemurl)|링크 컨트롤 항목으로 나타내는 URL을 설정 합니다.|  
  
## <a name="remarks"></a>주의  
 "링크 컨트롤" 창에 하이퍼텍스트 링크를 포함 하는 편리한 방법을 제공 합니다. 실제 컨트롤에는 마크업 텍스트를 렌더링 하 고 포함된 된 링크를 클릭할 때 적절 한 응용 프로그램을 시작 하는 창입니다. 여러 개의 링크를 하나의 컨트롤 내에서 지원 되 고 인덱스는&0;부터 시작 하 여 액세스할 수 있습니다.  
  
 이 컨트롤 (및 따라서는 `CLinkCtrl` 클래스) 및 나중에 Windows XP에서 실행 되는 프로그램에만 사용할 수 있습니다.  
  
 자세한 내용은 참조 [SysLink 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb760706) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CLinkCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="clinkctrl"></a>CLinkCtrl::CLinkCtrl  
 `CLinkCtrl` 개체를 생성합니다.  
  
```  
CLinkCtrl();
```  
  
##  <a name="create"></a>CLinkCtrl::Create  
 링크 컨트롤을 만들고이에 연결 된 `CLinkCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL Create(DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszLinkMarkup`  
 표시는 표시할 텍스트를 포함 하는&0;로 끝나는 문자열에 대 한 포인터입니다. 자세한 내용은 항목의 "태그 및 링크 액세스" 섹션을 참조 하십시오. [SysLink 컨트롤의 개요](http://msdn.microsoft.com/library/windows/desktop/bb760706) 에 [MSDN Library](http://go.microsoft.com/fwlink/linkid=556)합니다.  
  
 `dwStyle`  
 링크 컨트롤의 스타일을 지정합니다. 모든 조합의 컨트롤 스타일을 적용 합니다. 참조 [일반적인 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775498) 에 `Windows SDK` 자세한 내용은 합니다.  
  
 `rect`  
 링크 컨트롤의 크기와 위치를 지정합니다. 수 중 하나는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](../../mfc/reference/rect-structure1.md) 구조입니다.  
  
 `pParentWnd`  
 링크 컨트롤의 부모 창을 지정합니다. 않아야 `NULL`합니다.  
  
 `nID`  
 링크 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `true`초기화에 성공 하면 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>주의  
 생성 한 `CLinkCtrl` 두 단계에서는 개체입니다. 먼저, 생성자를 호출 하 고 다음 호출 `Create`, 링크 컨트롤을 만들고에 연결 하는 `CLinkCtrl` 개체입니다. 컨트롤 확장된 창 스타일을 사용 하는 경우 호출할 [CLinkCtrl::CreateEx](#createex) 대신 `Create`합니다.  
  
 두 번째 형태는 `Create` 메서드는 사용 되지 않습니다. 지정 하는 첫 번째 폼을 사용 하 여는 `lpszLinkMarkup` 매개 변수입니다.  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 라는 두 개의 변수를 정의 `m_Link1` 및 `m_Link2`, 두 개의 링크 컨트롤에 액세스 하는 데 사용 되는 합니다.  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s&#1;&2;](../../mfc/reference/codesnippet/cpp/clinkctrl-class_1.h)]  
  
### <a name="example"></a>예제  
 다음 코드 예제에서는 다른 링크 컨트롤의 위치에 따라 하나의 링크 컨트롤을 만듭니다. 리소스 로더는 응용 프로그램을 시작 하는 경우 첫 번째 링크 컨트롤을 만듭니다. 응용 프로그램의 OnInitDialog 메서드 들어가면 첫 번째 링크 컨트롤의 위치를 기준으로 두 번째 링크 컨트롤을 만듭니다. 그런 다음 두 번째 링크 컨트롤을 표시 하는 텍스트에 맞게 조정 있습니다.  
  
 [!code-cpp[NVC_MFC_CLinkCtrl_s&#1;&1;](../../mfc/reference/codesnippet/cpp/clinkctrl-class_2.cpp)]  
  
##  <a name="createex"></a>CLinkCtrl::CreateEx  
 확장된 스타일을 사용 하 여 링크 컨트롤을 만들고에 연결 된 `CLinkCtrl` 개체입니다.  
  
```  
virtual BOOL CreateEx(
    LPCTSTR lpszLinkMarkup,   
    DWORD dwExStyle,  
    DWORD dwStyle,   
    const RECT& rect,   
    CWnd* pParentWnd,   
    UINT nID);

 
virtual BOOL CreateEx(DWORD  dwExStyle,
    DWORD  dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT  nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszLinkMarkup`  
 표시는 표시할 텍스트를 포함 하는&0;로 끝나는 문자열에 대 한 포인터입니다. 자세한 내용은 항목의 "태그 및 링크 액세스" 섹션을 참조 하십시오. [SysLink 컨트롤의 개요](http://msdn.microsoft.com/library/windows/desktop/bb760706) 에 [MSDN Library](http://go.microsoft.com/fwlink/linkid=556)합니다.  
  
 `dwExStyle`  
 링크 컨트롤의 확장된 스타일을 지정합니다. 확장된 창 스타일의 목록에 대 한 참조는 `dwExStyle` 에 대 한 매개 변수 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `dwStyle`  
 링크 컨트롤의 스타일을 지정합니다. 모든 조합의 컨트롤 스타일을 적용 합니다. 자세한 내용은 참조 [일반적인 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775498) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `rect`  
 링크 컨트롤의 크기와 위치를 지정합니다. 수 중 하나는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT](../../mfc/reference/rect-structure1.md) 구조입니다.  
  
 `pParentWnd`  
 링크 컨트롤의 부모 창을 지정합니다. 않아야 `NULL`합니다.  
  
 `nID`  
 링크 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 `true`초기화에 성공 하면 그렇지 않으면 `false`합니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 `CreateEx` 대신 [만들기](#create) 확장된 Windows 스타일 상수를 적용 합니다.  
  
 두 번째 형태는 `CreateEx` 메서드는 사용 되지 않습니다. 지정 하는 첫 번째 폼을 사용 하 여는 `lpszLinkMarkup` 매개 변수입니다.  
  
##  <a name="getidealheight"></a>CLinkCtrl::GetIdealHeight  
 링크 컨트롤의 이상적인 높이 검색합니다.  
  
```  
int GetIdealHeight() const;  
```  
  
### <a name="return-value"></a>반환 값  
 픽셀 단위의 컨트롤의 이상적인 높이입니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [LM_GETIDEALHEIGHT](http://msdn.microsoft.com/library/windows/desktop/bb760716)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getidealsize"></a>CLinkCtrl::GetIdealSize  
 링크의 지정된 된 너비에 따라 현재 링크 컨트롤에 대 한 링크 텍스트의 기본 설정된 높이 계산합니다.  
  
```  
int GetIdealSize(
    int cxMaxWidth,   
    SIZE* pSize) const;  
```  
  
### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `cxMaxWidth`|픽셀 단위로 링크의 최대 너비입니다.|  
|[out] *`pSize`|Windows에 대 한 포인터 [크기](http://msdn.microsoft.com/library/windows/desktop/dd145106) 구조입니다. 이 메서드가 반환 하는 경우는 `cy` 의 멤버는 `SIZE` 구조에 의해 지정 된 링크 텍스트 너비에 대 한 이상적인 링크 텍스트 높이 `cxMaxWidth`합니다. `cx` 구조체의 멤버에 실제로 필요한 링크 텍스트 너비를 포함 합니다.|  
  
### <a name="return-value"></a>반환 값  
 링크 텍스트 (픽셀)에서의 기본 설정된 높이입니다. 값과 같으면 반환 값은는 `cy` 의 멤버는 `SIZE` 구조입니다.  
  
### <a name="remarks"></a>주의  
 에 대 한 예제는 `GetIdealSize` 메서드 예제를 참조 하십시오 [CLinkCtrl::Create](#create)합니다.  
  
 이 메서드는 전송 된 [LM_GETIDEALSIZE](http://msdn.microsoft.com/library/windows/desktop/bb760718) 에 설명 된 메시지는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getitem"></a>CLinkCtrl::GetItem  
 상태 및 링크 컨트롤 항목의 특성을 검색합니다.  
  
```  
BOOL GetItem(PLITEM pItem) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 에 대 한 포인터는 [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) 구조 항목 정보를 받을 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getitemid"></a>CLinkCtrl::GetItemID  
 링크 컨트롤 항목의 ID를 검색합니다.  
  
```  
BOOL GetItemID(
    int iLink,  
    CString& strID) const;  
  
BOOL GetItemID(
    int iLink,  
    LPWSTR szID,  
    UINT cchID) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `iLink`  
 링크 컨트롤 항목의 인덱스입니다.  
  
 *strID*  
 A [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) 지정된 된 항목의 ID를 포함 하는 개체입니다.  
  
 *szID*  
 지정된 된 항목의 ID가 포함 된 null로 끝나는 문자열입니다.  
  
 *cchID*  
 크기의 문자는 *szID* 버퍼입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
> [!NOTE]
>  또한이 함수는 반환 **FALSE** 경우의 버퍼 *szID 또는 strID* 보다 작으면 **MAX_LINKID_TEXT**합니다.  
  
### <a name="remarks"></a>주의  
 특정 링크 컨트롤 항목의 ID를 검색합니다. 자세한 내용은 Win32 메시지를 참조 하십시오. [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getitemstate"></a>CLinkCtrl::GetItemState  
 링크 컨트롤 항목의 상태를 검색합니다.  
  
```  
BOOL GetItemState(
    int iLink,  
    UINT* pnState,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `iLink`  
 링크 컨트롤 항목의 인덱스입니다.  
  
 `pnState`  
 지정 된 상태 항목의 값입니다.  
  
 `stateMask`  
 가져올 어떤 상태 항목을 설명 하는 플래그의 조합입니다. 값의 목록에 대 한 설명을 참조는 **상태** 멤버에는 [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) 구조입니다. 허용 가능한 항목은에서 허용 하는 것과 동일 **상태**합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 특정 링크 컨트롤 항목의 지정 된 상태 항목의 값을 검색합니다. 자세한 내용은 Win32 메시지를 참조 하십시오. [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="getitemurl"></a>CLinkCtrl::GetItemUrl  
 링크 컨트롤 항목으로 표현 하는 URL을 검색 합니다.  
  
```  
BOOL GetItemUrl(
    int iLink,  
    CString& strUrl) const;  
  
BOOL GetItemUrl(
    int iLink,  
    LPWSTR szUrl,  
    UINT cchUrl) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 `iLink`  
 링크 컨트롤 항목의 인덱스입니다.  
  
 `strUrl`  
 A [CStringT](../../atl-mfc-shared/reference/cstringt-class.md) 지정된 된 항목을 나타내는 URL이 포함 된 개체  
  
 `szUrl`  
 지정된 된 항목으로 표시 하는 URL을 포함 하는 null로 끝나는 문자열  
  
 *cchUrl*  
 크기의 문자는 *szURL* 버퍼입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
> [!NOTE]
>  또한이 함수는 반환 **FALSE** 경우의 버퍼 *szUrl 또는 strUrl* 보다 작으면 **MAX_LINKID_TEXT**합니다.  
  
### <a name="remarks"></a>주의  
 지정 된 링크 컨트롤 항목으로 표현 하는 URL을 검색 합니다. 자세한 내용은 Win32 메시지를 참조 하십시오. [LM_GETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760720) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="hittest"></a>CLinkCtrl::HitTest  
 사용자가 지정된 된 링크를 클릭 하는 경우를 결정 합니다.  
  
```  
BOOL HitTest(PLHITTESTINFO phti) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *phti*  
 에 대 한 포인터는 **LHITTESTINFO** 링크에 대 한 사용자가 클릭 한 모든 정보가 포함 된 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [LM_HITTEST](http://msdn.microsoft.com/library/windows/desktop/bb760722)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="setitem"></a>CLinkCtrl::SetItem  
 상태를 설정 하는 링크 컨트롤 항목의 특성입니다.  
  
```  
BOOL SetItem(PLITEM pItem);
```  
  
### <a name="parameters"></a>매개 변수  
 `pItem`  
 에 대 한 포인터는 [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) 설정 하는 정보가 포함 된 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수는 Win32 메시지의 동작을 구현 [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724)에 설명 된 대로 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="setitemid"></a>CLinkCtrl::SetItemID  
 링크 컨트롤 항목의 ID를 검색합니다.  
  
```  
BOOL SetItemID(
    int iLink,  
    LPCWSTR szID);
```  
  
### <a name="parameters"></a>매개 변수  
 `iLink`  
 링크 컨트롤 항목의 인덱스입니다.  
  
 *szID*  
 지정된 된 항목의 ID가 포함 된 null로 끝나는 문자열입니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 특정 링크 컨트롤 항목의 ID를 설정 합니다. 자세한 내용은 Win32 메시지를 참조 하십시오. [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="setitemstate"></a>CLinkCtrl::SetItemState  
 링크 컨트롤 항목의 상태를 검색합니다.  
  
```  
BOOL SetItemState(
    int iLink,  
    UINT state,  
    UINT stateMask = LIS_FOCUSED | LIS_ENABLED | LIS_VISITED);
```  
  
### <a name="parameters"></a>매개 변수  
 `iLink`  
 링크 컨트롤 항목의 인덱스입니다.  
  
 `pnState`  
 설정 되 고 지정 된 상태 항목의 값입니다.  
  
 `stateMask`  
 설정 중인 상태 항목을 설명 하는 플래그의 조합입니다. 값의 목록에 대 한 설명을 참조는 **상태** 멤버에는 [LITEM](http://msdn.microsoft.com/library/windows/desktop/bb760710) 구조입니다. 허용 가능한 항목은에서 허용 하는 것과 동일 **상태**합니다.  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 특정 링크 컨트롤 항목의 지정 된 상태 항목의 값을 설정합니다. 자세한 내용은 Win32 메시지를 참조 하십시오. [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
##  <a name="setitemurl"></a>CLinkCtrl::SetItemUrl  
 링크 컨트롤 항목으로 나타내는 URL을 설정 합니다.  
  
```  
BOOL SetItemUrl(
    int iLink,  
    LPCWSTR szUrl);
```  
  
### <a name="parameters"></a>매개 변수  
 `iLink`  
 링크 컨트롤 항목의 인덱스입니다.  
  
 `szUrl`  
 지정된 된 항목으로 표시 하는 URL을 포함 하는 null로 끝나는 문자열  
  
### <a name="return-value"></a>반환 값  
 반환 **TRUE** 성공 **FALSE** 실패 합니다.  
  
### <a name="remarks"></a>주의  
 지정 된 링크 컨트롤 항목으로 나타내는 URL을 설정 합니다. 자세한 내용은 Win32 메시지를 참조 하십시오. [LM_SETITEM](http://msdn.microsoft.com/library/windows/desktop/bb760724) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)

