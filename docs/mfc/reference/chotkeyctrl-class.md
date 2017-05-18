---
title: "CHotKeyCtrl 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- hot key controls
- CHotKeyCtrl class
- Windows common controls [C++], CHotKeyCtrl
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cbcc720d2b934cde9f8beb9bb95499d9cc569413
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

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
|[CHotKeyCtrl::Create](#create)|Hot key 컨트롤을 만들고 연결 하는 `CHotKeyCtrl` 개체입니다.|  
|[CHotKeyCtrl::CreateEx](#createex)|지정 된 Windows 확장된 스타일을 사용 하 여 바로 가기 키 컨트롤을 만들고에 연결 된 `CHotKeyCtrl` 개체입니다.|  
|[CHotKeyCtrl::GetHotKey](#gethotkey)|Hot key 컨트롤에서 가상 키 코드 및 한정자 플래그의 바로 가기 키를 검색합니다.|  
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|바로 가기 키에 할당 하는 로컬 문자 집합에서 키 이름을 검색 합니다.|  
|[CHotKeyCtrl::GetKeyName](#getkeyname)|지정된 된 가상 키 코드에 할당 하는 로컬 문자 집합에서 키 이름을 검색 합니다.|  
|[CHotKeyCtrl::SetHotKey](#sethotkey)|Hot key 컨트롤에 대 한 바로 가기 키 조합을 설정합니다.|  
|[CHotKeyCtrl::SetRules](#setrules)|잘못 된 조합 및 바로 가기 키 컨트롤에 대 한 기본 한정자 조합 정의합니다.|  
  
## <a name="remarks"></a>주의  
 "바로 가기 키 컨트롤"는 바로 가기 키를 만드는 데 사용할 수 있는 창입니다. "바로 가기 키"는 사용자 작업을 신속 하 게 수행 하기를 누를 수 있는 키 조합입니다. (예를 들어 사용자 만들 수 지정된 된 창 활성화 및 Z 순서의 맨 위쪽에 표시 하는 바로 가기 키입니다.) Hot key 컨트롤 사용자의 선택 항목을 표시 하 고 사용자가 유효한 키 조합을 선택 하면 합니다.  
  
 이 컨트롤 (및 따라서는 `CHotKeyCtrl` 클래스)은 이상 Windows 95/98 및 Windows NT 버전 3.51에서 실행 중인 프로그램에만 사용할 수 있습니다.  
  
 응용 프로그램 컨트롤에서 지정 된 키 조합을 검색 하 고 사용할 수는 사용자가 키 조합의 선택한 경우는 **WM_SETHOTKEY** 시스템에서 바로 가기 키를 설정 하는 메시지입니다. 에 창 지정 된 사용자를 누를 때마다 바로 가기 키, 그 이후에 시스템의 모든 부분에서는 **WM_SETHOTKEY** 메시지 수신는 `WM_SYSCOMMAND` 메시지를 지정 하 **SC_HOTKEY**합니다. 이 메시지를 수신 하는 창을 활성화 합니다. 바로 가기 키 호출한 응용 프로그램까지 유효한 상태로 남아 **WM_SETHOTKEY** 종료 됩니다.  
  
 이 메커니즘에 의존 하는 바로 가기 키 지원와에서 다르면는 **WM_HOTKEY** 메시지와 Windows [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) 및 [UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327) 함수입니다.  
  
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
 Hot key 컨트롤을 만들고 연결 하는 `CHotKeyCtrl` 개체입니다.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwStyle`  
 바로 가기 키 컨트롤의 스타일을 지정합니다. 모든 조합의 컨트롤 스타일을 적용 합니다. 참조 [일반적인 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775498) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] 자세한 내용은 합니다.  
  
 `rect`  
 바로 가기 키 컨트롤의 크기와 위치를 지정합니다. 수 중 하나는 [CRect](../../atl-mfc-shared/reference/crect-class.md) 개체 또는 [RECT 구조체](../../mfc/reference/rect-structure1.md)합니다.  
  
 `pParentWnd`  
 일반적으로 부모 창의 바로 가기 키 컨트롤의 지정 된 [CDialog](../../mfc/reference/cdialog-class.md)합니다. 않아야 **NULL**합니다.  
  
 `nID`  
 바로 가기 키 컨트롤의 ID를 지정 합니다.  
  
### <a name="return-value"></a>반환 값  
 0이 아닌 경우 초기화에 성공 하면 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 생성 한 `CHotKeyCtrl` 두 단계에서는 개체입니다. 먼저, 생성자를 호출 하 고 다음 호출 **만들기**, 바로 가기 키 컨트롤을 만들고 연결 하는 `CHotKeyCtrl` 개체입니다.  
  
 컨트롤 확장된 창 스타일을 사용 하는 경우 호출할 [CreateEx](#createex) 대신 **만들기**합니다.  
  
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
 생성 되는 컨트롤의 확장된 스타일을 지정 합니다. 확장된 창 스타일의 목록에 대 한 참조는 `dwExStyle` 에 대 한 매개 변수 [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `dwStyle`  
 바로 가기 키 컨트롤의 스타일을 지정합니다. 모든 조합의 컨트롤 스타일을 적용 합니다. 자세한 내용은 참조 [일반적인 컨트롤 스타일](http://msdn.microsoft.com/library/windows/desktop/bb775498) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
 `rect`  
 에 대 한 참조는 [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) 크기와의 클라이언트 좌표에서 만든 창 위치를 설명 하는 구조 `pParentWnd`합니다.  
  
 `pParentWnd`  
 컨트롤의 부모 창에 대 한 포인터입니다.  
  
 `nID`  
 컨트롤의 자식 창 id입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 사용 하 여 `CreateEx` 대신 [만들기](#create) Windows 확장된 스타일 앞에 지정 된 Windows 확장된 스타일을 적용 하려면 **WS_EX_**합니다.  
  
##  <a name="gethotkey"></a>CHotKeyCtrl::GetHotKey  
 Hot key 컨트롤에서 가상 키 코드 및 한정자 플래그의 바로 가기 키를 검색합니다.  
  
```  
DWORD GetHotKey() const;  
  
void GetHotKey(
    WORD& wVirtualKeyCode,  
    WORD& wModifiers) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 [out] `wVirtualKeyCode`  
 바로 가기 키의 가상 키 코드입니다. 표준 가상 키 코드 목록은 Winuser.h를 참조 하십시오.  
  
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
 첫 번째에서 메서드를 오버 로드는 `DWORD` 가상 키 코드 및 한정자 플래그를 포함 하는 합니다. 가상 키 코드를 포함 하는 하위 단어의 하위 바이트, 보조키 플래그를 포함 하는 하위 단어의 상위 바이트 및 상위 word은&0;입니다.  
  
### <a name="remarks"></a>주의  
 가상 키 코드와 함께 한정자 키 바로 가기 키를 정의합니다.  
  
##  <a name="gethotkeyname"></a>CHotKeyCtrl::GetHotKeyName  
 바로 가기 키의 지역화 된 이름을 가져오려면이 함수를 호출 합니다.  
  
```  
CString GetHotKeyName() const;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 선택 된 바로 가기 키의 지역화 된 이름입니다. 선택한 바로 가기 키를가 하는 경우 `GetHotKeyName` 빈 문자열을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 이 멤버 함수를 반환 하는 이름은 키보드 드라이버에서 가져옵니다. 지역화 된 버전의 Windows에서 지역화 되지 않은 키보드 드라이버를 설치할 수 또는 그 반대로 합니다.  
  
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
 가상 키 코드 확장 키인 경우 **TRUE**고, 그렇지 않으면 **FALSE**합니다.  
  
### <a name="return-value"></a>반환 값  
 지정 된 키의 지역화 된 이름을 `vk` 매개 변수입니다. 키에 매핑된 이름이 없는 경우 `GetKeyName` 빈 문자열을 반환 합니다.  
  
### <a name="remarks"></a>주의  
 Windows의 지역화 된 버전의 지역화 되지 않은 키보드 드라이버를 설치할 수 있도록 키보드 드라이버에서이 함수를 반환 하는 키 이름을 제공 하거나 그 반대로 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCControlLadenDialog #&69;](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]  
  
##  <a name="sethotkey"></a>CHotKeyCtrl::SetHotKey  
 Hot key 컨트롤에 대 한 바로 가기 키를 설정합니다.  
  
```  
void SetHotKey(
    WORD wVirtualKeyCode,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>매개 변수  
 [in] `wVirtualKeyCode`  
 바로 가기 키의 가상 키 코드입니다. 표준 가상 키 코드 목록은 Winuser.h를 참조 하십시오.  
  
 [in] `wModifiers`  
 바로 가기 키의 보조 키를 나타내는 플래그의 비트 조합 (OR)입니다.  
  
 보조키 플래그는 다음과 같습니다.  
  
|플래그|해당 키|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|Alt 키|  
|`HOTKEYF_CONTROL`|CTRL 키|  
|`HOTKEYF_EXT`|확장 된 키|  
|`HOTKEYF_SHIFT`|Shift 키|  
  
### <a name="remarks"></a>주의  
 가상 키 코드와 함께 한정자 키 바로 가기 키를 정의합니다.  
  
##  <a name="setrules"></a>CHotKeyCtrl::SetRules  
 잘못 된 조합 및 바로 가기 키 컨트롤에 대 한 기본 한정자 조합을 정의 하려면이 함수를 호출 합니다.  
  
```  
void SetRules(
    WORD wInvalidComb,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>매개 변수  
 `wInvalidComb`  
 잘못 된 키 조합을 지정 하는 플래그의 배열입니다. 다음 값의 조합 수 있습니다.  
  
- `HKCOMB_A`ALT 키  
  
- `HKCOMB_C`CTRL  
  
- `HKCOMB_CA`CTRL + ALT  
  
- `HKCOMB_NONE`수정 되지 않은 키  
  
- `HKCOMB_S`SHIFT 키  
  
- `HKCOMB_SA`SHIFT + ALT  
  
- `HKCOMB_SC`SHIFT + CTRL  
  
- `HKCOMB_SCA`SHIFT + CTRL + ALT  
  
 `wModifiers`  
 사용자가 잘못 된 조합이 입력을 사용 하 여 키 조합을 지정 하는 플래그의 배열입니다. 보조키 플래그에 대 한 자세한 내용은 참조 하십시오. [GetHotKey](#gethotkey)합니다.  
  
### <a name="remarks"></a>주의  
 에 지정 된 플래그에 정의 된 대로 사용자에 잘못 된 키 조합이 포함 될 때 `wInvalidComb`, 시스템 OR 연산자를 사용 하 여 키에 지정 된 플래그를 사용 하 여 사용자가 입력을 결합 하 여 `wModifiers`합니다. 결과 키 조합은 문자열로 변환 하 고 바로 가기 키 컨트롤에 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)




