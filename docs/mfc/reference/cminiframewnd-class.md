---
title: "CMiniFrameWnd 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMiniFrameWnd
dev_langs:
- C++
helpviewer_keywords:
- CMiniFrameWnd class
- mini-frame windows
- toolbars [C++]
ms.assetid: b8f534ed-0532-4d8e-9657-5595cf677749
caps.latest.revision: 21
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1229f5405c9eeb90abcdc54108ed26e28d94f0e0
ms.lasthandoff: 02/24/2017

---
# <a name="cminiframewnd-class"></a>CMiniFrameWnd 클래스
일반적으로 부동 도구 모음에 있는 절반 높이의 프레임 창을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMiniFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMiniFrameWnd::CMiniFrameWnd](#cminiframewnd)|`CMiniFrameWnd` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMiniFrameWnd::Create](#create)|만듭니다는 `CMiniFrameWnd` 생성 후 개체입니다.|  
|[CMiniFrameWnd::CreateEx](#createex)|만듭니다는 `CMiniFrameWnd` 생성 후 추가 옵션) (포함 개체입니다.|  
  
## <a name="remarks"></a>주의  
 이러한 미니 프레임 창을 최대화/최소화 단추를 갖지 않습니다 또는 메뉴와 사용자를 한 번 클릭 하 고 해제 시스템 메뉴에서 하기만 한다는 점을 제외 하면 기본 프레임 창 처럼 작동 합니다.  
  
 사용 하는 `CMiniFrameWnd` 개체, 개체를 먼저 정의 합니다. 그런 다음 호출에서 [만들기](#create) 미니 프레임 창을 표시 하려면 멤버 함수입니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 `CMiniFrameWnd` 개체, 문서를 참조 하십시오. [도킹 및 부동 도구 모음](../../mfc/docking-and-floating-toolbars.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMiniFrameWnd`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="a-namecminiframewnda--cminiframewndcminiframewnd"></a><a name="cminiframewnd"></a>CMiniFrameWnd::CMiniFrameWnd  
 생성 된 `CMiniFrameWnd` 개체, 하지만 창을 만들지 않습니다.  
  
```  
CMiniFrameWnd();
```  
  
### <a name="remarks"></a>주의  
 호출 하는 창을 만들기 위해 [CMiniFrameWnd::Create](#create)합니다.  
  
##  <a name="a-namecreatea--cminiframewndcreate"></a><a name="create"></a>CMiniFrameWnd::Create  
 Windows 미니 프레임 창을 만들고이에 연결 된 `CMiniFrameWnd` 개체입니다.  
  
```  
virtual BOOL Create(
    LPCTSTR lpClassName,  
    LPCTSTR lpWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd = NULL,  
    UINT nID = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpClassName`  
 Windows 클래스의 이름을 지정 하는 null로 끝나는 문자열을 가리킵니다. 클래스 이름은 전역에 등록 되는 이름 수 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 함수입니다. 경우 **NULL**, 창 클래스를 프레임 워크에 의해 등록 됩니다. MFC는 다음과 같은 스타일 및 특성 기본 클래스를 제공합니다.  
  
-   집합 스타일 비트 **CS_DBLCLKS**, 어떤 보냅니다 마우스를 두 번 클릭할 때 메시지 창 프로시저를 두 번 클릭 합니다.  
  
-   집합 스타일 비트 **CS_HREDRAW** 및 **CS_VREDRAW**, 창의 크기가 변경 될 때 다시 그릴 클라이언트 영역의 내용을 직접입니다.  
  
-   Windows 표준 클래스 커서 설정 **IDC_ARROW**합니다.  
  
-   클래스 배경 브러시 설정 하는 **NULL**이므로 창 배경을 지우지 것입니다.  
  
-   클래스 아이콘 표준, 손 흔드는 플래그 Windows 로고 아이콘을 설정 합니다.  
  
-   Windows에서 표시 된 대로 창의 기본 크기 및 위치를 설정 합니다.  
  
 `lpWindowName`  
 창 이름이 포함 된 null로 끝나는 문자열을 가리킵니다.  
  
 `dwStyle`  
 창 스타일 특성을 지정합니다. 이러한 특수 스타일의 표준 창 스타일 및 하나 이상의 포함할 수 있습니다.  
  
- **MFS_MOVEFRAME** 미니 프레임 창의 캡션 뿐 아니라 창의 가장자리를 클릭 하 여 이동할 수 있습니다.  
  
- **MFS_4THICKFRAME** 미니 프레임 창의 크기를 조정 하지 않도록 설정 합니다.  
  
- **MFS_SYNCACTIVE** 부모 창의 활성화 미니 프레임 창의 정품 인증을 동기화 합니다.  
  
- **MFS_THICKFRAME** 미니 프레임 창의 클라이언트 영역 내용이 허용 작은 규모의 허용 합니다.  
  
- **MFS_BLOCKSYSMENU** 시스템 메뉴 및 컨트롤 메뉴에 대 한 액세스를 비활성화 하 고 캡션 (제목 표시줄)의 일부를 변환 합니다.  
  
 참조 [CWnd::Create](../../mfc/reference/cwnd-class.md#create) 에 대 한 설명은 가능한 창 스타일 값입니다. 미니 프레임 창에 사용 되는 일반적인 조합이 **WS_POPUP | WS_CAPTION | WS_SYSMENU**합니다.  
  
 `rect`  
 A `RECT` 창의 원하는 크기를 지정 하는 구조입니다.  
  
 `pParentWnd`  
 부모 창을 가리킵니다. 사용 하 여 **NULL** 최상위 창에 있습니다.  
  
 `nID`  
 이 값은 자식 컨트롤의 식별자 미니 프레임 창의 자식 창으로 만들어질 경우 그렇지 않으면 0입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 **만들** 창 클래스 이름 및 창 이름을 초기화 하 고 해당 스타일과 부모에 대 한 기본값을 등록 합니다.  
  
##  <a name="a-namecreateexa--cminiframewndcreateex"></a><a name="createex"></a>CMiniFrameWnd::CreateEx  
 
          `CMiniFrameWnd` 개체를 만듭니다.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    LPCTSTR lpClassName,  
    LPCTSTR lpWindowName,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd = NULL,  
    UINT nID = 0);
```  
  
### <a name="parameters"></a>매개 변수  
 `dwExStyle`  
 확장된 스타일을 지정 된 `CMiniFrameWnd` 만들어지는 합니다. 적용 하는 [확장 된 창 스타일](../../mfc/reference/extended-window-styles.md) 창에 있습니다.  
  
 `lpClassName`  
 Windows 클래스의 이름을 지정 하는 null로 끝나는 문자열을 가리키는 (한 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) 구조). 클래스 이름은 전역에 등록 되는 이름 수 [AfxRegisterWndClass](http://msdn.microsoft.com/library/62c7d4b1-7a29-4abb-86f7-dec541659db0) 함수 또는 미리 정의 된 컨트롤 클래스 이름 중입니다. 않아야 **NULL**합니다.  
  
 `lpWindowName`  
 창 이름이 포함 된 null로 끝나는 문자열을 가리킵니다.  
  
 `dwStyle`  
 창 스타일 특성을 지정합니다. 참조 [창 스타일](../../mfc/reference/window-styles.md) 및 [CWnd::Create](../../mfc/reference/cwnd-class.md#create) 에 대 한 설명은 사용할 수 있는 값입니다.  
  
 `rect`  
 크기와의 클라이언트 좌표에서 창의 위치 `pParentWnd`합니다.  
  
 `pParentWnd`  
 부모 창 개체를 가리킵니다.  
  
 `nID`  
 자식 창의 식별자입니다.  
  
### <a name="return-value"></a>반환 값  
 성공 시 TRUE를 반환 합니다. 실패 한 경우 FALSE입니다.  
  
### <a name="remarks"></a>주의  
 `CreateEx` 매개 변수를 지정 된 **WNDCLASS**, 창 스타일 (선택 사항) 초기 위치 및 창 크기입니다. `CreateEx`또한 창의 부모 (있는 경우) 및 ID를 지정  
  
 때 `CreateEx` Windows 보냅니다 실행 되는 [WM_GETMINMAXINFO](../../mfc/reference/cwnd-class.md#ongetminmaxinfo), [WM_NCCREATE](../../mfc/reference/cwnd-class.md#onnccreate), [WM_NCCALCSIZE](../../mfc/reference/cwnd-class.md#onnccalcsize), 및 [WM_CREATE](../../mfc/reference/cwnd-class.md#oncreate) 메시지를 창입니다.  
  
 기본 메시지 처리를 확장 하려면에서 클래스를 파생 `CMiniFrameWnd`, 새 클래스에 메시지 맵에 추가 하 고 위의 메시지에 대 한 멤버 함수를 제공 합니다. 재정의 `OnCreate`예를 들어, 새 클래스에 대 한 필요한 초기화를 수행 하도록 합니다.  
  
 더 이상 재정의 **에***메시지* 메시지 파생된 클래스에 추가 기능을 추가 하는 처리기.  
  
 하는 경우는 **WS_VISIBLE** 스타일은 지정, Windows는 창을 활성화 하 고 창을 표시 하는 데 필요한 모든 메시지를 보냅니다. 창 스타일 제목 표시줄을 지정 하는 경우 창 제목은 가리키는 `lpszWindowName` 매개 변수는 제목 표시줄에 표시 됩니다.  
  
 `dwStyle` 매개 변수의 조합이 포함 될 수 [창 스타일](../../mfc/reference/window-styles.md)합니다.  
  
 이전 스타일 팔레트 도구 상자 창 이상 지원 되지 않습니다. 이전 버전의 Windows에는 MFC 응용 프로그램을 실행 하는 경우 "X" 닫기 단추 없는 이전 스타일을 지원 하 던 있지만 더 이상 Visual c + +.NET에서 지원 됩니다. 만 새 `WS_EX_TOOLWINDOW` 스타일 대해서도 지원 됩니다;이 스타일에 대 한 참조 [확장 창 스타일](../../mfc/reference/extended-window-styles.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)

