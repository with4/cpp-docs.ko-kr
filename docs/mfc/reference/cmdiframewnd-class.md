---
title: "CMDIFrameWnd 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDIFrameWnd
- AFXWIN/CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CMDIFrameWnd
- AFXWIN/CMDIFrameWnd::CreateClient
- AFXWIN/CMDIFrameWnd::CreateNewChild
- AFXWIN/CMDIFrameWnd::GetWindowMenuPopup
- AFXWIN/CMDIFrameWnd::MDIActivate
- AFXWIN/CMDIFrameWnd::MDICascade
- AFXWIN/CMDIFrameWnd::MDIGetActive
- AFXWIN/CMDIFrameWnd::MDIIconArrange
- AFXWIN/CMDIFrameWnd::MDIMaximize
- AFXWIN/CMDIFrameWnd::MDINext
- AFXWIN/CMDIFrameWnd::MDIPrev
- AFXWIN/CMDIFrameWnd::MDIRestore
- AFXWIN/CMDIFrameWnd::MDISetMenu
- AFXWIN/CMDIFrameWnd::MDITile
dev_langs: C++
helpviewer_keywords:
- CMDIFrameWnd [MFC], CMDIFrameWnd
- CMDIFrameWnd [MFC], CreateClient
- CMDIFrameWnd [MFC], CreateNewChild
- CMDIFrameWnd [MFC], GetWindowMenuPopup
- CMDIFrameWnd [MFC], MDIActivate
- CMDIFrameWnd [MFC], MDICascade
- CMDIFrameWnd [MFC], MDIGetActive
- CMDIFrameWnd [MFC], MDIIconArrange
- CMDIFrameWnd [MFC], MDIMaximize
- CMDIFrameWnd [MFC], MDINext
- CMDIFrameWnd [MFC], MDIPrev
- CMDIFrameWnd [MFC], MDIRestore
- CMDIFrameWnd [MFC], MDISetMenu
- CMDIFrameWnd [MFC], MDITile
ms.assetid: fa8736e6-511b-4c51-8b4d-eba78378aeb9
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc40ac38d4f74848448b26284ad225faad04864e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cmdiframewnd-class"></a>CMDIFrameWnd 클래스
창 관리 멤버와 함께 Windows MDI(다중 문서 인터페이스) 프레임 창 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMDIFrameWnd : public CFrameWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMDIFrameWnd::CMDIFrameWnd](#cmdiframewnd)|`CMDIFrameWnd`를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMDIFrameWnd::CreateClient](#createclient)|Windows 만듭니다 **MDICLIENT** 이 대 한 창 `CMDIFrameWnd`합니다. 에 의해 호출 된 `OnCreate` 의 멤버 함수 `CWnd`합니다.|  
|[CMDIFrameWnd::CreateNewChild](#createnewchild)|새 자식 창을 만듭니다.|  
|[CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)|창 팝업 메뉴를 반환합니다.|  
|[CMDIFrameWnd::MDIActivate](#mdiactivate)|다른 MDI 자식 창을 활성화합니다.|  
|[CMDIFrameWnd::MDICascade](#mdicascade)|종속 연결 된 형식으로 모든 자식 창을 정렬합니다.|  
|[CMDIFrameWnd::MDIGetActive](#mdigetactive)|자식 최대화할지 여부를 나타내는 플래그와 함께 현재 활성 MDI 자식 창을 검색 합니다.|  
|[CMDIFrameWnd::MDIIconArrange](#mdiiconarrange)|모든 최소화 된 상태로 문서 자식 창을 정렬합니다.|  
|[CMDIFrameWnd::MDIMaximize](#mdimaximize)|MDI 자식 창을 최대화합니다.|  
|[CMDIFrameWnd::MDINext](#mdinext)|현재 활성 자식 창 바로 뒤에 있는 자식 창을 활성화 하 고 다른 모든 자식 창 뒤 현재 활성 자식 창을 배치 합니다.|  
|[CMDIFrameWnd::MDIPrev](#mdiprev)|이전 자식 창을 활성화 하 고 그 뒤에 즉시 현재 활성 자식 창을 배치 합니다.|  
|[CMDIFrameWnd::MDIRestore](#mdirestore)|MDI 자식 창에 최대화 또는 최소화 된 크기에서 복원합니다.|  
|[CMDIFrameWnd::MDISetMenu](#mdisetmenu)|MDI 프레임 창의 메뉴, 창 팝업 메뉴 또는 둘 다를 바꿉니다.|  
|[CMDIFrameWnd::MDITile](#mditile)|모든 자식 창을 바둑판식으로 배열 된 형식으로 정렬합니다.|  
  
## <a name="remarks"></a>설명  
 응용 프로그램에 대 한 유용한 MDI 프레임 창을 만들기 위해에서 클래스를 파생 `CMDIFrameWnd`합니다. 응용 프로그램에 관련 데이터를 저장 하 고 파생된 클래스에 멤버 변수를 추가 합니다. 파생 클래스에서 메시지 처리기 멤버 함수 및 메시지 맵을 구현하여 메시지가 창에 전달될 때 수행되는 작업을 지정합니다.  
  
 MDI 프레임 창에 호출 하 여 생성할 수 있습니다는 [만들기](../../mfc/reference/cframewnd-class.md#create) 또는 [LoadFrame](../../mfc/reference/cframewnd-class.md#loadframe) 의 멤버 함수 `CFrameWnd`합니다.  
  
 호출 하기 전에 **만들기** 또는 `LoadFrame`, c + +를 사용 하 여 힙에 프레임 창 개체를 생성 해야 **새** 연산자입니다. 호출 하기 전에 **만들기** 사용 하는 창 클래스를 등록할 수도 있습니다는 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 프레임에 대 한 아이콘 및 클래스 스타일을 설정 하려면 전역 함수입니다.  
  
 사용 하 여는 **만들기** 같이 즉시 인수 프레임의 생성 매개 변수를 전달 하는 멤버 함수입니다.  
  
 `LoadFrame`보다 적은 인수를 사용 해야 **만들기**, 대신 프레임의 캡션, 아이콘, 액셀러레이터 키 테이블 및 메뉴를 포함 하 여 리소스에서 대부분의 해당 기본 값을 검색 합니다. 에 액세스 하 여 `LoadFrame`, 이러한 모든 리소스에는 동일한 리소스 ID를 사용 해야 합니다. (예를 들어 **IDR_MAINFRAME**).  
  
 하지만 **MDIFrameWnd** 에서 파생 된 `CFrameWnd`, 프레임 창 클래스에서 파생 된 `CMDIFrameWnd` 로 선언 되지 필요 `DECLARE_DYNCREATE`합니다.  
  
 `CMDIFrameWnd` 대부분의 기본 구현에서 클래스 상속 `CFrameWnd`합니다. 이 기능 목록은 자세한에 대 한 참조는 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 클래스 설명 합니다. `CMDIFrameWnd` 클래스에 다음과 같은 추가 기능:  
  
-   MDI 프레임 창은 관리는 **MDICLIENT** 창, 컨트롤 막대와 함께에서 위치를 변경 합니다. MDI 클라이언트 MDI 자식 프레임 창의 직계 부모입니다. **WS_HSCROLL** 및 **WS_VSCROLL** 에 지정 된 창 스타일은 `CMDIFrameWnd` (예: Windows MDI 클라이언트 영역을 스크롤하여 볼 수 있도록 주 프레임 창 아니라 MDI 클라이언트 창에 적용 프로그램 관리자, 예를 들어) 합니다.  
  
-   MDI 프레임 창은 활성 MDI 자식 창이 없습니다 경우 메뉴 모음으로 사용 되는 기본 메뉴를 소유 합니다. 활성 MDI 자식 이면 MDI 프레임 창 메뉴 모음 MDI 자식 창 메뉴도 자동으로 바뀝니다.  
  
-   MDI 프레임 창에 있는 경우 현재 MDI 자식 창와 함께에서 작동 합니다. 예를 들어, 명령 메시지는 MDI 프레임 창 하기 전에 현재 활성 MDI 자식으로 위임 됩니다.  
  
-   MDI 프레임 창에는 다음과 같은 표준 창 메뉴 명령에 대 한 기본 처리기에 있습니다.  
  
    - **ID_WINDOW_TILE_VERT**  
  
    - **ID_WINDOW_TILE_HORZ**  
  
    - **ID_WINDOW_CASCADE**  
  
    - **ID_WINDOW_ARRANGE**  
  
-   MDI 프레임 창 구현 역시 **ID_WINDOW_NEW**, 새 프레임와 현재 문서에서 보기 생성 되어 있습니다. 응용 프로그램은 MDI 창을 처리 사용자 지정 하려면 이러한 기본 명령 구현 재정의할 수 있습니다.  
  
 C + +를 사용 하지 마십시오 **삭제** 연산자를 프레임 창을 삭제 합니다. 대신 `CWnd::DestroyWindow`를 사용하세요. `CFrameWnd` 구현의 `PostNcDestroy` 창이 소멸 될 때에 c + + 개체를 삭제 합니다. 사용자 프레임 창에 기본값을 닫을 때 `OnClose` 처리기를 호출 하는 `DestroyWindow`합니다.  
  
 대 한 자세한 내용은 `CMDIFrameWnd`, 참조 [프레임 창](../../mfc/frame-windows.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIFrameWnd`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="cmdiframewnd"></a>CMDIFrameWnd::CMDIFrameWnd  
 `CMDIFrameWnd` 개체를 생성합니다.  
  
```  
CMDIFrameWnd();
```  
  
### <a name="remarks"></a>설명  
 호출 된 **만들기** 또는 `LoadFrame` 멤버 함수를 표시 하는 MDI 프레임 창을 만듭니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#13](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_1.cpp)]  
  
##  <a name="createclient"></a>CMDIFrameWnd::CreateClient  
 관리 하는 MDI 클라이언트 창을 만듭니다.는 `CMDIChildWnd` 개체입니다.  
  
```  
virtual BOOL CreateClient(
    LPCREATESTRUCT lpCreateStruct,  
    CMenu* pWindowMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpCreateStruct`  
 에 대 한 긴 포인터는 [CREATESTRUCT](../../mfc/reference/createstruct-structure.md) 구조입니다.  
  
 `pWindowMenu`  
 창 팝업 메뉴에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 재정의 하는 경우이 멤버 함수를 호출 해야는 `OnCreate` 직접 멤버 함수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#14](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_2.cpp)]  
  
##  <a name="createnewchild"></a>CMDIFrameWnd::CreateNewChild  
 새 자식 창을 만듭니다.  
  
```  
CMDIChildWnd* CreateNewChild(
    CRuntimeClass* pClass,  
    UINT nResource,  
    HMENU hMenu = NULL,  
    HACCEL hAccel = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `pClass`  
 자식 창 만들의 런타임 클래스입니다.  
  
 *nResource*  
 자식 창에 연결 된 공유 리소스의 ID입니다.  
  
 `hMenu`  
 자식 창 메뉴입니다.  
  
 `hAccel`  
 자식 창 가속기입니다.  
  
### <a name="remarks"></a>설명  
 이 함수를 사용 하 여 자식 창을 MDI 프레임 창의 만든 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#15](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_3.cpp)]  
  
 이 예제는 Q201045, 기술 자료 문서에서 "방법: 여러 창 형식을 비-문서/뷰 MDI 응용 프로그램에 추가 합니다." 기술 자료 문서에서 사용할 수 있는 [http://support.microsoft.com](http://support.microsoft.com/)합니다.  
  
##  <a name="getwindowmenupopup"></a>CMDIFrameWnd::GetWindowMenuPopup  
 이름이 "창" (MDI 창 관리에 대 한 메뉴 항목을 사용 하 여 팝업 메뉴) 인 현재 팝업 메뉴에 핸들을 얻기 위해이 함수를 호출 합니다.  
  
```  
virtual HMENU GetWindowMenuPopup(HMENU hMenuBar);
```  
  
### <a name="parameters"></a>매개 변수  
 *hMenuBar*  
 현재 메뉴 모음입니다.  
  
### <a name="return-value"></a>반환 값  
 창 팝업 메뉴 하나 있습니다. 그렇지 않으면 **NULL**합니다.  
  
### <a name="remarks"></a>설명  
 기본 구현은 팝업 메뉴와 같은 표준 창 메뉴 명령을 찾고 **ID_WINDOW_NEW** 및 **ID_WINDOW_TILE_HORZ**합니다.  
  
 표준 메뉴 명령 Id를 사용 하지 않는 창 메뉴에 있는 경우이 멤버 함수를 재정의 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#16](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_4.cpp)]  
  
##  <a name="mdiactivate"></a>CMDIFrameWnd::MDIActivate  
 다른 MDI 자식 창을 활성화합니다.  
  
```  
void MDIActivate(CWnd* pWndActivate);
```  
  
### <a name="parameters"></a>매개 변수  
 *pWndActivate*  
 MDI 자식 창 활성화 될를 가리킵니다.  
  
### <a name="remarks"></a>설명  
 이 멤버 함수는 [WM_MDIACTIVATE](../../mfc/reference/cwnd-class.md#onmdiactivate) 자식 창이 활성화 되 고와 해제 하 고 자식 창에는 메시지입니다.  
  
 이 동일한 메시지를 수신한 사용자 마우스나 키보드를 사용 하 여 MDI 자식 창에 포커스를 변경 하는 경우 전송 됩니다.  
  
> [!NOTE]
>  MDI 자식 창은 MDI 프레임 창을 독립적으로 활성화 됩니다. 프레임 활성화 되 면 마지막으로 활성화 된 자식 창을 보내집니다는 [WM_NCACTIVATE](../../mfc/reference/cwnd-class.md#onncactivate) 를 활성 창 프레임 및 캡션 표시줄 하지만 그릴 메시지에서 다른 수신 하지 `WM_MDIACTIVATE` 메시지입니다.  
  
### <a name="example"></a>예  
 예를 참조 [CMDIFrameWnd::GetWindowMenuPopup](#getwindowmenupopup)합니다.  
  
##  <a name="mdicascade"></a>CMDIFrameWnd::MDICascade  
 계단식 배열 형식에서 모든 MDI 자식 창을 정렬합니다.  
  
```  
void MDICascade();  
void MDICascade(int nType);
```  
  
### <a name="parameters"></a>매개 변수  
 `nType`  
 Cascade 플래그를 지정합니다. 다음 플래그에만 지정할 수 있습니다: `MDITILE_SKIPDISABLED`에서 연계 되 고 비활성화 된 MDI 자식 창을 방지 하는 합니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 버전 `MDICascade`, 매개 변수 없이 비활성화 된 것을 비롯 한 모든 MDI 자식 창을 계단식으로 배열 합니다. 지정 하는 경우 필요에 따라 두 번째 버전은 사용 하지 않도록 설정 하는 cascade MDI 자식 창을 하지 않는 `MDITILE_SKIPDISABLED` 에 대 한는 `nType` 매개 변수입니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#17](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_5.cpp)]  
  
##  <a name="mdigetactive"></a>CMDIFrameWnd::MDIGetActive  
 현재 활성 MDI 자식 창, 자식 창을 최대화 되었는지 여부를 나타내는 플래그와 함께 검색 합니다.  
  
```  
CMDIChildWnd* MDIGetActive(BOOL* pbMaximized = NULL) const;  
```  
  
### <a name="parameters"></a>매개 변수  
 *pbMaximized*  
 에 대 한 포인터는 **BOOL** 값을 반환 합니다. 로 설정 **TRUE** 반환이 창이 최대화 상태가 아니면 **FALSE**합니다.  
  
### <a name="return-value"></a>반환 값  
 활성 MDI 자식 창에 대 한 포인터입니다.  
  
### <a name="example"></a>예  
 예를 참조 [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)합니다.  
  
##  <a name="mdiiconarrange"></a>CMDIFrameWnd::MDIIconArrange  
 모든 최소화 된 상태로 문서 자식 창을 정렬합니다.  
  
```  
void MDIIconArrange();
```  
  
### <a name="remarks"></a>설명  
 최소화 됩니다 자식 창에는 영향을 주지 않습니다.  
  
### <a name="example"></a>예  
 예를 참조 [CMDIFrameWnd::MDICascade](#mdicascade)합니다.  
  
##  <a name="mdimaximize"></a>CMDIFrameWnd::MDIMaximize  
 지정된 된 MDI 자식 창을 최대화 합니다.  
  
```  
void MDIMaximize(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 창 최대화 하기 위해를 가리킵니다.  
  
### <a name="remarks"></a>설명  
 자식 창을 최대화 하는 경우 Windows 클라이언트 창 채우기의 클라이언트 영역을 찾을 수 있도록 크기가 조정 됩니다. Windows는 사용자를 복원 하거나 자식 창 닫기 수 프레임의 메뉴 모음에서 자식 창 컨트롤 메뉴를 배치 합니다. 또한 프레임 창 제목에 자식 창의 제목을 추가합니다.  
  
 현재 활성 MDI 자식 창이 최대화 될 때 다른 MDI 자식 창이 활성화 되어 있으면 Windows 현재 활성 자식 복원 되 고 새로 활성화 된 자식 창을 최대화 하는.  
  
### <a name="example"></a>예  
 예를 참조 [CMDIChildWnd::MDIMaximize](../../mfc/reference/cmdichildwnd-class.md#mdimaximize)합니다.  
  
##  <a name="mdinext"></a>CMDIFrameWnd::MDINext  
 현재 활성 자식 창 바로 뒤에 있는 자식 창을 활성화 하 고 다른 모든 자식 창 뒤 현재 활성 자식 창을 배치 합니다.  
  
```  
void MDINext();
```  
  
### <a name="remarks"></a>설명  
 현재 활성 MDI 자식 창을 최대화 하는 경우 멤버 함수는 현재 활성 자식 복원 하 고 새로 활성화 된 자식 극대화 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#18](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_6.cpp)]  
  
##  <a name="mdiprev"></a>CMDIFrameWnd::MDIPrev  
 이전 자식 창을 활성화 하 고 그 뒤에 즉시 현재 활성 자식 창을 배치 합니다.  
  
```  
void MDIPrev();
```  
  
### <a name="remarks"></a>설명  
 현재 활성 MDI 자식 창을 최대화 하는 경우 멤버 함수는 현재 활성 자식 복원 하 고 새로 활성화 된 자식 극대화 합니다.  
  
##  <a name="mdirestore"></a>CMDIFrameWnd::MDIRestore  
 MDI 자식 창에 최대화 또는 최소화 된 크기에서 복원합니다.  
  
```  
void MDIRestore(CWnd* pWnd);
```  
  
### <a name="parameters"></a>매개 변수  
 `pWnd`  
 복원 하려면 창을 가리킵니다.  
  
### <a name="example"></a>예  
 예를 참조 [CMDIChildWnd::MDIRestore](../../mfc/reference/cmdichildwnd-class.md#mdirestore)합니다.  
  
##  <a name="mdisetmenu"></a>CMDIFrameWnd::MDISetMenu  
 MDI 프레임 창의 메뉴, 창 팝업 메뉴 또는 둘 다를 바꿉니다.  
  
```  
CMenu* MDISetMenu(
    CMenu* pFrameMenu,  
    CMenu* pWindowMenu);
```  
  
### <a name="parameters"></a>매개 변수  
 *pFrameMenu*  
 새 프레임 창 메뉴의 메뉴를 지정합니다. 경우 **NULL**, 메뉴는 변경 되지 않습니다.  
  
 `pWindowMenu`  
 새 창 팝업 메뉴의 메뉴를 지정합니다. 경우 **NULL**, 메뉴는 변경 되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 이 메시지에서 대체 프레임 창 메뉴에 대 한 포인터입니다. 해당 포인터는 임시적이며, 나중에 사용하려고 저장하면 안됩니다.  
  
### <a name="remarks"></a>설명  
 호출한 후 `MDISetMenu`를 호출 하는 응용 프로그램의 [DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar) 의 멤버 함수 `CWnd` 메뉴 모음을 업데이트 하려면.  
  
 이 호출은 대체 창 팝업 메뉴를 MDI 자식 창 메뉴 항목의 이전 창 메뉴에서 제거 되며이 새 창 팝업 메뉴에 추가 합니다.  
  
 MDI 자식 창을 최대화 하는 경우이 호출은 대체 MDI 프레임 창 메뉴 컨트롤 메뉴 및 복원 컨트롤 이전 프레임 창 메뉴에서 제거 하 고 새 메뉴에 추가 됩니다.  
  
 MDI 자식 창을 관리 하는 프레임 워크를 사용 하는 경우에이 멤버 함수를 호출 하지 마십시오.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#19](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_7.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#20](../../mfc/reference/codesnippet/cpp/cmdiframewnd-class_8.cpp)]  
  
##  <a name="mditile"></a>CMDIFrameWnd::MDITile  
 모든 자식 창을 바둑판식으로 배열 된 형식으로 정렬합니다.  
  
```  
void MDITile();  
void MDITile(int nType);
```  
  
### <a name="parameters"></a>매개 변수  
 `nType`  
 바둑판식 배열 플래그를 지정합니다. 이 매개 변수는 다음 플래그의 하나일 수 있습니다.  
  
- `MDITILE_HORIZONTAL`타일 MDI 자식 창이 한 창을 다른 위에 나타납니다.  
  
- `MDITILE_SKIPDISABLED`비활성화 된 MDI 자식 창을 바둑판식으로 배열 되 고에서 방지 합니다.  
  
- `MDITILE_VERTICAL`타일 MDI 자식 창을 므로 다른 옆에 있는 한 해당 창에 나타납니다.  
  
### <a name="remarks"></a>설명  
 첫 번째 버전 `MDITile`, 매개 변수 없이 Windows 버전 3.1 이상에서 세로로 창을 바둑판식으로 배열 합니다. 두 번째 버전 창을 바둑판식으로 배열 세로 또는 가로로 값에 따라는 `nType` 매개 변수입니다.  
  
### <a name="example"></a>예  
 예를 참조 [CMDIFrameWnd::MDICascade](#mdicascade)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MDI MFC 샘플](../../visual-cpp-samples.md)   
 [MFC 샘플 MDIDOCVW](../../visual-cpp-samples.md)   
 [MFC 샘플 SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CMDIChildWnd 클래스](../../mfc/reference/cmdichildwnd-class.md)
