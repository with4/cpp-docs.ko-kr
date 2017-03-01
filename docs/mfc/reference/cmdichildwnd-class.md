---
title: "CMDIChildWnd 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDIChildWnd
dev_langs:
- C++
helpviewer_keywords:
- MDI [C++], child windows
- windows [C++], MDI
- CMDIChildWnd class
- child windows, CMDIChildWnd class
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
caps.latest.revision: 22
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
ms.openlocfilehash: 240af1fe5f3afa4cdb7d4d585dc74cc4836799cc
ms.lasthandoff: 02/24/2017

---
# <a name="cmdichildwnd-class"></a>CMDIChildWnd 클래스
창 관리 멤버와 함께 Windows MDI(다중 문서 인터페이스) 자식 창 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class CMDIChildWnd : public CFrameWnd  
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CMDIChildWnd::CMDIChildWnd](#cmdichildwnd)|`CMDIChildWnd` 개체를 생성합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CMDIChildWnd::Create](#create)|와 연결 된 Windows MDI 자식 창을 만듭니다는 `CMDIChildWnd` 개체입니다.|  
|[CMDIChildWnd::GetMDIFrame](#getmdiframe)|MDI 클라이언트 창의 MDI 프레임의 부모를 반환 합니다.|  
|[CMDIChildWnd::MDIActivate](#mdiactivate)|이 MDI 자식 창을 활성화합니다.|  
|[CMDIChildWnd::MDIDestroy](#mdidestroy)|이 MDI 자식 창을 소멸 시킵니다.|  
|[CMDIChildWnd::MDIMaximize](#mdimaximize)|이 MDI 자식 창을 최대화합니다.|  
|[CMDIChildWnd::MDIRestore](#mdirestore)|이 MDI 자식 창을 최대화 또는 최소화 된 크기에서 복원합니다.|  
|[CMDIChildWnd::SetHandles](#sethandles)|메뉴 및 바로 가기 리소스에 대 한 핸들을 설정합니다.|  
  
## <a name="remarks"></a>주의  
 MDI 자식 창에 MDI 자식 창을 MDI 프레임 창 내 아니라 바탕 화면에 표시 된다는 유사한 형태는 일반적인 프레임 창입니다. MDI 자식 창에는 자체의 메뉴 모음 없지만 대신 MDI 프레임 창의 메뉴를 공유 합니다. 프레임 워크를 현재 활성 상태인 MDI 자식 창을 나타내는 MDI 프레임 메뉴를 자동으로 변경 합니다.  
  
 응용 프로그램에 대 한 유용한 MDI 자식 창을 만들려면에서 클래스를 파생 `CMDIChildWnd`합니다. 응용 프로그램에 데이터를 저장 하 고 파생된 클래스에 멤버 변수를 추가 합니다. 파생 클래스에서 메시지 처리기 멤버 함수 및 메시지 맵을 구현하여 메시지가 창에 전달될 때 수행되는 작업을 지정합니다.  
  
 MDI 자식 창에 생성 하는 방법은 세 가지가 있습니다.  
  
-   사용 하 여이 직접 생성할 **만들기**합니다.  
  
-   사용 하 여이 직접 생성할 `LoadFrame`합니다.  
  
-   직접 생성 하지는 문서 템플릿을 통해.  
  
 호출 하기 전에 **만들기** 또는 `LoadFrame`, c + +를 사용 하 여 힙에 프레임 창 개체를 생성 해야 **새** 연산자입니다. 호출 하기 전에 **만들기** 사용 하는 창 클래스를 등록할 수도 있습니다는 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 프레임에 대 한 아이콘 및 클래스 스타일을 설정 하려면 전역 함수입니다.  
  
 사용 된 **만들기** 인수를 전달 하는 프레임의 생성 매개 변수: 즉시 멤버 함수입니다.  
  
 `LoadFrame`보다 적은 인수가 필요 **만들기**, 대신 프레임의 캡션, 아이콘, 액셀러레이터 키 테이블 및 메뉴를 포함 하 여 리소스에서 대부분의 기본 값을 검색 합니다. 액세스할 수 있도록 `LoadFrame`, 이러한 모든 리소스는 동일한 리소스 ID를 갖고 있어야 (예를 들어 **IDR_MAINFRAME**).  
  
 때는 `CMDIChildWnd` 만들어질 하지 직접은 프로그래머가 직접 대신 프레임 워크에서 개체의 뷰 및 문서를 포함 합니다. `CDocTemplate` 프레임의 만들기, 적절 한 문서 보기의 연결을 포함 하는 뷰를 만들고 개체를 오케스트레이션 합니다. 매개 변수는 `CDocTemplate` 생성자 지정는 `CRuntimeClass` 의 세 가지 클래스 (문서, 프레임 및 보기)를 포함 합니다. A `CRuntimeClass` 개체를 동적으로 (예를 들어 사용 하 여 새 파일 명령 또는 MDI 창 새 명령을) 사용자가 지정 하는 경우 새 프레임을 만드는 프레임 워크에서 사용 됩니다.  
  
 프레임 창 클래스에서 파생 된 `CMDIChildWnd` 함께 선언 되어야 `DECLARE_DYNCREATE` 위해 위의 `RUNTIME_CLASS` 메커니즘이 제대로 작동 하도록 합니다.  
  
 `CMDIChildWnd` 대부분의 기본 구현에서의 상속 `CFrameWnd`합니다. 이러한 기능의 자세한 목록은 참조 하십시오는 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 클래스 설명 합니다. `CMDIChildWnd` 클래스에 다음과 같은 추가 기능:  
  
-   와 함께에서 `CMultiDocTemplate` 클래스, 여러 `CMDIChildWnd` 동일한 문서 서식 파일에서 개체는 Windows 시스템 리소스 절약 같은 메뉴를 공유 합니다.  
  
-   MDI 프레임 창의 메뉴를 완전히 대체 하는 현재 활성 상태인 MDI 자식 창 메뉴 및 캡션을 현재 활성 상태인 MDI 자식 창의 MDI 프레임 창의 캡션에 추가 됩니다. MDI 프레임 창 함께에서 구현 되는 MDI 자식 창 기능의 자세한 예제를 참조 하십시오.는 `CMDIFrameWnd` 클래스 설명 합니다.  
  
 C + +를 사용 하지 않는 **삭제** 연산자를 프레임 창을 삭제 합니다. 대신 `CWnd::DestroyWindow` 를 사용하세요. `CFrameWnd` 구현의 `PostNcDestroy` 창이 소멸 될 때 c + + 개체를 삭제 합니다. 사용자의 기본 프레임 창 닫을 때 `OnClose` 처리기를 호출 하는 `DestroyWindow`합니다.  
  
 대 한 자세한 내용은 `CMDIChildWnd`, 참조 [프레임 창](../../mfc/frame-windows.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIChildWnd`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="a-namecmdichildwnda--cmdichildwndcmdichildwnd"></a><a name="cmdichildwnd"></a>CMDIChildWnd::CMDIChildWnd  
 통화를 생성 하는 `CMDIChildWnd` 개체입니다.  
  
```  
CMDIChildWnd();
```  
  
### <a name="remarks"></a>주의  
 호출 **만들기** 표시 창을 만들 수 있습니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMDIChildWnd::Create](#create)합니다.  
  
##  <a name="a-namecreatea--cmdichildwndcreate"></a><a name="create"></a>CMDIChildWnd::Create  
 Windows MDI 자식 창을 만들고에 연결 하려면이 멤버 함수를 호출 하 여 `CMDIChildWnd` 개체입니다.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszClassName,  
    LPCTSTR lpszWindowName,  
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | WS_OVERLAPPEDWINDOW,  
    const RECT& rect = rectDefault,  
    CMDIFrameWnd* pParentWnd = NULL,  
    CCreateContext* pContext = NULL);
```  
  
### <a name="parameters"></a>매개 변수  
 `lpszClassName`  
 Windows 클래스의 이름을 지정 하는 null로 끝나는 문자열을 가리키는 (한 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) 구조). 클래스 이름에 등록 되는 이름 수는 [AfxRegisterWndClass](http://msdn.microsoft.com/library/62c7d4b1-7a29-4abb-86f7-dec541659db0) 전역 함수입니다. 해야 **NULL** 표준 `CMDIChildWnd`합니다.  
  
 `lpszWindowName`  
 창 이름을 나타내는 null로 끝나는 문자열을 가리킵니다. 제목 표시줄에 대 한 텍스트로 사용합니다.  
  
 `dwStyle`  
 창을 지정 [스타일](../../mfc/reference/window-styles.md) 특성입니다. **WS_CHILD** 스타일을 사용 해야 합니다.  
  
 `rect`  
 크기와 창의 위치를 포함합니다. `rectDefault` 값을 사용 하면 크기와 새 위치를 지정 하는 Windows `CMDIChildWnd`합니다.  
  
 `pParentWnd`  
 창의 부모를 지정합니다. 경우 **NULL**, 주 응용 프로그램 창을 사용 합니다.  
  
 `pContext`  
 지정 된 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) 구조입니다. 이 매개 변수 수 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>주의  
 현재 활성 상태인 MDI 자식 프레임 창에는 부모 프레임 창의 캡션을 결정할 수 있습니다. 이 기능은 해제 하 여 비활성화 되어는 **FWS_ADDTOTITLE** 자식 프레임 창의 스타일 비트입니다.  
  
 프레임 워크에는 자식 창을 만드는 데는 사용자 명령에 대 한 응답으로이 멤버 함수를 호출 하 고 사용 하 여 프레임 워크는 `pContext` 매개 변수를 제대로 자식 창에는 응용 프로그램에 연결 합니다. 호출 하는 경우 **만들기**, `pContext` 수 **NULL**합니다.  
  
### <a name="example"></a>예제  
 예제 1:  
  
 [!code-cpp[NVC_MFCWindowing #&7;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]  
  
### <a name="example"></a>예제  
 예제 2:  
  
 [!code-cpp[NVC_MFCWindowing #&8;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing #&9;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]  
  
##  <a name="a-namegetmdiframea--cmdichildwndgetmdiframe"></a><a name="getmdiframe"></a>CMDIChildWnd::GetMDIFrame  
 MDI 부모 프레임을 반환 하려면이 함수를 호출 합니다.  
  
```  
CMDIFrameWnd* GetMDIFrame();
```  
  
### <a name="return-value"></a>반환 값  
 MDI 부모 프레임 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 반환 하는 프레임은 두 명의 부모에서 제거는 `CMDIChildWnd` 는 형식의 창의 부모 **MDICLIENT** 을 관리 하는 `CMDIChildWnd` 개체입니다. 호출의 [GetParent](../../mfc/reference/cwnd-class.md#getparent) 반환할 멤버 함수는 `CMDIChildWnd` 개체의 직계 **MDICLIENT** 임시 파일로 부모 `CWnd` 포인터입니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMDIFrameWnd::MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu)합니다.  
  
##  <a name="a-namemdiactivatea--cmdichildwndmdiactivate"></a><a name="mdiactivate"></a>CMDIChildWnd::MDIActivate  
 MDI 프레임 창 독립적으로 MDI 자식 창을 활성화 하려면이 멤버 함수를 호출 합니다.  
  
```  
void MDIActivate();
```  
  
### <a name="remarks"></a>주의  
 프레임 활성화 되 면 마지막으로 활성화 되는 자식 창도 활성화 됩니다.  
  
### <a name="example"></a>예제  
  예를 참조 [CMDIFrameWnd::GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup)합니다.  
  
##  <a name="a-namemdidestroya--cmdichildwndmdidestroy"></a><a name="mdidestroy"></a>CMDIChildWnd::MDIDestroy  
 MDI 자식 창을 삭제 하려면이 멤버 함수를 호출 합니다.  
  
```  
void MDIDestroy();
```  
  
### <a name="remarks"></a>주의  
 프레임 창에서 자식 창의 제목을 제거 하 고 자식 창 비활성화 하는 멤버 함수.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&10;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]  
  
##  <a name="a-namemdimaximizea--cmdichildwndmdimaximize"></a><a name="mdimaximize"></a>CMDIChildWnd::MDIMaximize  
 MDI 자식 창을 최대화 하기 위해이 함수를 호출 합니다.  
  
```  
void MDIMaximize();
```  
  
### <a name="remarks"></a>주의  
 자식 창을 최대화 하는 경우 Windows 프레임 창의 클라이언트 영역 채우기의 클라이언트 영역을 찾을 수 있도록 크기가 조정 됩니다. Windows 사용자를 복원 하거나 자식 창을 닫을 수 있도록 프레임의 메뉴 모음에서 자식 창의 컨트롤 메뉴를 배치 하 고 자식 창의 제목을 프레임 창 제목에 추가 합니다.  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&11;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]  
  
##  <a name="a-namemdirestorea--cmdichildwndmdirestore"></a><a name="mdirestore"></a>CMDIChildWnd::MDIRestore  
 MDI 자식 창을 최대화 또는 최소화 된 크기에서 복원 하려면이 멤버 함수를 호출 합니다.  
  
```  
void MDIRestore();
```  
  
### <a name="example"></a>예제  
 [!code-cpp[NVC_MFCWindowing #&12;](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]  
  
##  <a name="a-namesethandlesa--cmdichildwndsethandles"></a><a name="sethandles"></a>CMDIChildWnd::SetHandles  
 메뉴 및 바로 가기 리소스에 대 한 핸들을 설정합니다.  
  
```  
void SetHandles(
    HMENU hMenu,  
    HACCEL hAccel);
```  
  
### <a name="parameters"></a>매개 변수  
 `hMenu`  
 메뉴 리소스의 핸들입니다.  
  
 `hAccel`  
 엑셀 러 레이 터 리소스의 핸들입니다.  
  
### <a name="remarks"></a>주의  
 MDI 자식 창 개체에 의해 사용 되는 메뉴 및 바로 가기 리소스를 설정 하려면이 함수를 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 샘플 MDI](../../visual-cpp-samples.md)   
 [MFC 샘플 MDIDOCVW](../../visual-cpp-samples.md)   
 [MFC 샘플 SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd 클래스](../../mfc/reference/cmdiframewnd-class.md)

