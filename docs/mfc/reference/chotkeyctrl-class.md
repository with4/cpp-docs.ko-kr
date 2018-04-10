---
title: CHotKeyCtrl 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CHotKeyCtrl
- AFXCMN/CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::CHotKeyCtrl
- AFXCMN/CHotKeyCtrl::Create
- AFXCMN/CHotKeyCtrl::CreateEx
- AFXCMN/CHotKeyCtrl::GetHotKey
- AFXCMN/CHotKeyCtrl::GetHotKeyName
- AFXCMN/CHotKeyCtrl::GetKeyName
- AFXCMN/CHotKeyCtrl::SetHotKey
- AFXCMN/CHotKeyCtrl::SetRules
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl [MFC], CHotKeyCtrl
- CHotKeyCtrl [MFC], Create
- CHotKeyCtrl [MFC], CreateEx
- CHotKeyCtrl [MFC], GetHotKey
- CHotKeyCtrl [MFC], GetHotKeyName
- CHotKeyCtrl [MFC], GetKeyName
- CHotKeyCtrl [MFC], SetHotKey
- CHotKeyCtrl [MFC], SetRules
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 982d4dec9c00490248da0b0e0dec7fd44376c218
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl 클래스
Windows의 공용 바로 가기 컨트롤의 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CHotKeyCtrl : public CWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CHotKeyCtrl::CHotKeyCtrl](#chotkeyctrl)|`CHotKeyCtrl` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CHotKeyCtrl::Create](#create)|바로 가기 키 컨트롤을 만들고에 연결 된 `CHotKeyCtrl` 개체입니다.|  
|[CHotKeyCtrl::CreateEx](#createex)|Windows는 지정 된 확장된 스타일을 사용 하 여 바로 가기 키 컨트롤을 만들고에 연결 된 `CHotKeyCtrl` 개체입니다.|  
|[CHotKeyCtrl::GetHotKey](#gethotkey)|바로 가기 키 컨트롤에서 가상 키 코드 및 한정자의 플래그는 바로 가기 키를 검색합니다.|  
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|바로 가기 키에 할당 된, 로컬 문자 집합에서 키 이름을 검색 합니다.|  
|[CHotKeyCtrl::GetKeyName](#getkeyname)|지정된 된 가상 키 코드에 할당 된, 로컬 문자 집합에서 키 이름을 검색 합니다.|  
|[CHotKeyCtrl::SetHotKey](#sethotkey)|바로 가기 키 컨트롤에 대 한 바로 가기 키 조합을 설정합니다.|  
|[CHotKeyCtrl::SetRules](#setrules)|잘못 된 조합 및 바로 가기 키 컨트롤에 대 한 기본 한정자 조합이 정의합니다.|  
  
## <a name="remarks"></a>설명  
 "바로 가기 키 컨트롤"에 바로 가기 키를 만들 수 있는 창입니다. "바로 가기 키"는 키 조합 작업을 신속 하 게 수행 하려면 사용자를 누를 수입니다. (예를 들어 사용자 키를 만들 수는 핫 지정된 된 창을 활성화 하 고 Z 순서의 맨 위쪽에 표시 하는.) 바로 가기 키 컨트롤 사용자의 선택 항목을 표시 및 사용자가 올바른 키 조합을 선택 하면 합니다.  
  
 이 컨트롤 (및 따라서는 `CHotKeyCtrl` 클래스) 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수는 있습니다.  
  
 응용 프로그램 컨트롤에서 지정 된 키 조합을 검색 하 고 사용할 수는 사용자가 키 조합의 선택한 경우는 **WM_SETHOTKEY** 시스템의 바로 가기 키를 설정 하는 메시지입니다. 창에 지정 된 사용자를 누를 때마다 바로 가기 키 그 후 시스템의 모든 부분에서는 **WM_SETHOTKEY** 메시지 수신는 `WM_SYSCOMMAND` 메시지 지정 **SC_HOTKEY**합니다. 이 메시지를 수신 하는 창을 활성화 합니다. 호출한 응용 프로그램까지 바로 가기 키 유효 **WM_SETHOTKEY** 종료 됩니다.  
  
 이 메커니즘에 의존 하는 핫 키 지원 간에 차이가 있는 **WM_HOTKEY** 메시지와 Windows [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) 및 [UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327) 함수입니다.  
  
 사용 하 여 대 한 자세한 내용은 `CHotKeyCtrl`, 참조 [컨트롤](../../mfc/controls-mfc.md) 및 [CHotKeyCtrl 사용 하 여](../../mfc/using-chotkeyctrl.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHotKeyCtrl`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxcmn.h  
  
##  <a name="chotkeyctrl"></a>CHotKeyCtrl::CHotKeyCtrl  
 `CHotKeyCtrl` 개체를 생성합니다.  
  
```  
CHotKeyCtrl();
```  
  
##  <a name="create"></a>CHotKeyCtrl::Create  
 바로 가기 키 컨트롤을 만들고에 연결 된 `CHotKeyCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 바로 가기 키 컨트롤의 스타일을 지정합니다. 컨트롤 스타일의 조합을 적용 됩니다. 참조 [공통 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775498) 자세한 내용은 Windows sdk입니다.  
  
 `rect`  
 바로 가기 키 컨트롤의 크기와 위치를 지정합니다. 있습니다는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT 구조체](../../mfc/reference/rect-structure1.md)합니다.  
  
 `pParentWnd`  
 일반적으로 바로 가기 키 컨트롤의 부모 창 지정을 [CDialog](../../mfc/reference/cdialog-class.md)합니다. 않아야 **NULL**합니다.  
  
 `nID`  
 바로 가기 키 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우 초기화에 성공 하면 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 생성할는 `CHotKeyCtrl` 두 단계를 수행에서 하는 개체입니다. 먼저 생성자를 호출 하 고 호출 **만들기**, 바로 가기 키 컨트롤을 만들고에 연결 하는 `CHotKeyCtrl` 개체입니다.  
  
 컨트롤 확장된 창 스타일을 사용 하려면 호출 [CreateEx](#createex) 대신 **만들기**합니다.  
  
##  <a name="createex"></a>CHotKeyCtrl::CreateEx  
 컨트롤 (자식 창)을 만들고 사용 하 여 연결 하려면이 함수를 호출 하 여 `CHotKeyCtrl` 개체입니다.  
  
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
 만들 컨트롤의 확장된 스타일을 지정 합니다. 목록이 확장된 창 스타일에 대 한 참조는 `dwExStyle` 에 대 한 매개 변수 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows sdk에서입니다.  
  
 `dwStyle`  
 바로 가기 키 컨트롤의 스타일을 지정합니다. 컨트롤 스타일의 조합을 적용 됩니다. 자세한 내용은 참조 [공통 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775498) Windows sdk에서입니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와의 클라이언트 좌표에 만들어질 창 위치를 설명 하는 구조 `pParentWnd`합니다.  
  
 `pParentWnd`  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 컨트롤의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 사용 하 여 `CreateEx` 대신 [만들기](#create) Windows 확장된 스타일 접두사에 의해 지정 된 확장된 창 스타일을 적용할 **WS_EX_**합니다.  
  
##  <a name="gethotkey"></a>CHotKeyCtrl::GetHotKey  
 바로 가기 키 컨트롤에서 가상 키 코드 및 한정자의 플래그 바로 가기 키를 검색합니다.  
  
```  
DWORD GetHotKey() const;  
  
void GetHotKey(
    WORD& wVirtualKeyCode,  
    WORD& wModifiers) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `wVirtualKeyCode`  
 바로 가기 키의 가상 키 코드입니다. 표준 가상 키 코드 목록이 Winuser.h을 참조 하세요.  
  
 [out] `wModifiers`  
 바로 가기 키의 보조 키를 나타내는 플래그의 비트 조합 (OR)입니다.  
  
 보조키 플래그는 다음과 같습니다.  
  
|플래그|해당 키|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|Alt 키|  
|`HOTKEYF_CONTROL`|CTRL 키|  
|`HOTKEYF_EXT`|확장 된 키|  
|`HOTKEYF_SHIFT`|Shift 키|  
  
### <a name="return-value"></a>반환 값  
 첫 번째 범위에서 메서드를 오버 로드는 `DWORD` 가상 키 코드와 한정자 플래그를 포함 하는 합니다. 가상 키 코드를 포함 하는 하위 단어의 낮은 순서 바이트 하위 단어의 상위 바이트 보조키 플래그 포함 되어 있지 않으며 상위 단어는 0입니다.  
  
### <a name="remarks"></a>설명  
 가상 키 코드와 함께 보조 키의 바로 가기 키를 정의합니다.  
  
##  <a name="gethotkeyname"></a>CHotKeyCtrl::GetHotKeyName  
 바로 가기 키의 지역화 된 이름을 가져오려면이 함수를 호출 합니다.  
  
```  
CString GetHotKeyName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 선택 된 바로 가기 키의 지역화 된 이름입니다. 선택한 핫 키를가 하는 경우 `GetHotKeyName` 빈 문자열을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수를 반환 하는 이름을 키보드 드라이버에서 제공 됩니다. 지역화 된 버전의 Windows에서의 키보드 지역화 되지 않은 드라이버를 설치할 수 있으며 반대의 합니다.  
  
##  <a name="getkeyname"></a>CHotKeyCtrl::GetKeyName  
 지정 된 가상 키 코드에 할당 된 키의 지역화 된 이름을 가져오려면이 함수를 호출 합니다.  
  
```  
static CString GetKeyName(
    UINT vk,  
    BOOL fExtended);
```  
  
### <a name="parameters"></a>매개 변수  
 `vk`  
 가상 키 코드입니다.  
  
 *fExtended*  
 가상 키 코드 확장 된 키가 있으면 **TRUE**고, 그렇지 않으면 **FALSE**합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 키의 지역화 된 이름을 `vk` 매개 변수입니다. 키에 매핑된 이름이 없는 경우 `GetKeyName` 빈 문자열을 반환 합니다.  
  
### <a name="remarks"></a>설명  
 지역화 된 버전의 Windows에서의 키보드 지역화 되지 않은 드라이버를 설치할 수 있도록 키보드 드라이버에서이 함수가 반환 하는 키 이름을 제공 하며 그 반대 과정도 수행 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCControlLadenDialog#69](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]  
  
##  <a name="sethotkey"></a>CHotKeyCtrl::SetHotKey  
 바로 가기 키 컨트롤에 대 한 바로 가기 키를 설정합니다.  
  
```  
void SetHotKey(
    WORD wVirtualKeyCode,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `wVirtualKeyCode`  
 바로 가기 키의 가상 키 코드입니다. 표준 가상 키 코드 목록이 Winuser.h을 참조 하세요.  
  
 [in] `wModifiers`  
 바로 가기 키의 보조 키를 나타내는 플래그의 비트 조합 (OR)입니다.  
  
 보조키 플래그는 다음과 같습니다.  
  
|플래그|해당 키|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|Alt 키|  
|`HOTKEYF_CONTROL`|CTRL 키|  
|`HOTKEYF_EXT`|확장 된 키|  
|`HOTKEYF_SHIFT`|Shift 키|  
  
### <a name="remarks"></a>설명  
 가상 키 코드와 함께 보조 키의 바로 가기 키를 정의합니다.  
  
##  <a name="setrules"></a>CHotKeyCtrl::SetRules  
 잘못 된 조합 및 바로 가기 키 컨트롤에 대 한 기본 한정자 조합이 정의 하려면이 함수를 호출 합니다.  
  
```  
void SetRules(
    WORD wInvalidComb,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>매개 변수  
 `wInvalidComb`  
 잘못 된 키 조합을 지정 하는 플래그의 배열입니다. 다음 값의 조합 수 있습니다.  
  
- `HKCOMB_A`ALT  
  
- `HKCOMB_C`CTRL  
  
- `HKCOMB_CA`CTRL + ALT  
  
- `HKCOMB_NONE`수정 되지 않은 키  
  
- `HKCOMB_S`SHIFT 키  
  
- `HKCOMB_SA`SHIFT + ALT  
  
- `HKCOMB_SC`SHIFT + CTRL  
  
- `HKCOMB_SCA`SHIFT + CTRL + ALT  
  
 `wModifiers`  
 잘못 된 조합이 입력할 때 사용할 키 조합을 지정 하는 플래그의 배열입니다. 보조키 플래그에 대 한 자세한 내용은 참조 하십시오. [GetHotKey](#gethotkey)합니다.  
  
### <a name="remarks"></a>설명  
 에 지정 된 플래그에 정의 된 대로 잘못 된 키 조합이 조합을 사용할 `wInvalidComb`, 시스템에 지정 된 플래그와 함께 사용자가 입력 한 키를 결합 하는 OR 연산자를 사용 하 여 `wModifiers`합니다. 결과 키 조합은 문자열로 변환 되 고 바로 가기 키 컨트롤에 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)



