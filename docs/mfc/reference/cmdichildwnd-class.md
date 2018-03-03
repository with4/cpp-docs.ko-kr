---
title: "CMDIChildWnd 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMDIChildWnd
- AFXWIN/CMDIChildWnd
- AFXWIN/CMDIChildWnd::CMDIChildWnd
- AFXWIN/CMDIChildWnd::Create
- AFXWIN/CMDIChildWnd::GetMDIFrame
- AFXWIN/CMDIChildWnd::MDIActivate
- AFXWIN/CMDIChildWnd::MDIDestroy
- AFXWIN/CMDIChildWnd::MDIMaximize
- AFXWIN/CMDIChildWnd::MDIRestore
- AFXWIN/CMDIChildWnd::SetHandles
dev_langs:
- C++
helpviewer_keywords:
- CMDIChildWnd [MFC], CMDIChildWnd
- CMDIChildWnd [MFC], Create
- CMDIChildWnd [MFC], GetMDIFrame
- CMDIChildWnd [MFC], MDIActivate
- CMDIChildWnd [MFC], MDIDestroy
- CMDIChildWnd [MFC], MDIMaximize
- CMDIChildWnd [MFC], MDIRestore
- CMDIChildWnd [MFC], SetHandles
ms.assetid: 6d07f5d4-9a3e-4723-9fa5-e65bb669fdd5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: deca38c7c1fdaf9523e4186b801e5ed25042e46e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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
|[CMDIChildWnd::Create](#create)|와 연결 된 Windows MDI 자식 창을 만듭니다.는 `CMDIChildWnd` 개체입니다.|  
|[CMDIChildWnd::GetMDIFrame](#getmdiframe)|MDI 프레임 MDI 클라이언트 창의 부모를 반환합니다.|  
|[CMDIChildWnd::MDIActivate](#mdiactivate)|이 MDI 자식 창을 활성화합니다.|  
|[CMDIChildWnd::MDIDestroy](#mdidestroy)|이 MDI 자식 창을 제거합니다.|  
|[CMDIChildWnd::MDIMaximize](#mdimaximize)|이 MDI 자식 창을 최대화합니다.|  
|[CMDIChildWnd::MDIRestore](#mdirestore)|최대화 또는 최소화 된 크기에서이 MDI 자식 창을 복원합니다.|  
|[CMDIChildWnd::SetHandles](#sethandles)|메뉴 및 바로 가기 리소스에 대 한 핸들을 설정합니다.|  
  
## <a name="remarks"></a>설명  
 MDI 자식 창을 제외 하 고 바탕 화면이 아니라 MDI 프레임 창 안에 MDI 자식 창이 표시 되는 일반적인 프레임 창과 매우 유사 하지만 찾습니다. MDI 자식 창에는 자체의 메뉴 모음 없지만 대신 MDI 프레임 창의 메뉴를 공유 합니다. 프레임 워크를 나타내는 현재 활성 MDI 자식 창을 MDI 프레임 메뉴를 자동으로 변경 합니다.  
  
 응용 프로그램에 대 한 유용한 MDI 자식 창을 만들기 위해에서 클래스를 파생 `CMDIChildWnd`합니다. 응용 프로그램에 관련 데이터를 저장 하 고 파생된 클래스에 멤버 변수를 추가 합니다. 파생 클래스에서 메시지 처리기 멤버 함수 및 메시지 맵을 구현하여 메시지가 창에 전달될 때 수행되는 작업을 지정합니다.  
  
 MDI 자식 창에 생성 하는 방법은 세 가지가 있습니다.  
  
-   사용 하 여이 직접 생성할 **만들기**합니다.  
  
-   사용 하 여이 직접 생성할 `LoadFrame`합니다.  
  
-   직접 생성 하지는 문서 템플릿을 통해 합니다.  
  
 호출 하기 전에 **만들기** 또는 `LoadFrame`, c + +를 사용 하 여 힙에 프레임 창 개체를 생성 해야 **새** 연산자입니다. 호출 하기 전에 **만들기** 사용 하는 창 클래스를 등록할 수도 있습니다는 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 프레임에 대 한 아이콘 및 클래스 스타일을 설정 하려면 전역 함수입니다.  
  
 사용 하 여는 **만들기** 같이 즉시 인수 프레임의 생성 매개 변수를 전달 하는 멤버 함수입니다.  
  
 `LoadFrame`보다 적은 인수를 사용 해야 **만들기**, 대신 프레임의 캡션, 아이콘, 액셀러레이터 키 테이블 및 메뉴를 포함 하 여 리소스에서 대부분의 해당 기본 값을 검색 합니다. 액세스할 수 있도록 `LoadFrame`, 이러한 모든 리소스에는 동일한 리소스 ID를 사용 해야 합니다. (예를 들어 **IDR_MAINFRAME**).  
  
 경우는 `CMDIChildWnd` 만들어질 하지 직접은 프로그래머가 직접 대신 프레임 워크에서 보기 및 문서 개체에 포함 되어 있습니다. `CDocTemplate` 프레임의 만들기, 포함 하는 뷰를 만들고 적절 한 문서에 뷰 연결 개체를 조정 합니다. 매개 변수는 `CDocTemplate` 생성자 지정는 `CRuntimeClass` 세 개의 클래스 (문서, 프레임 및 보기)를 포함 합니다. A `CRuntimeClass` 개체를 동적으로 만드는 새 프레임 (예를 들어 새 파일 명령 또는 MDI 창의 새 명령 사용)에서 사용자가 지정 하는 경우 프레임 워크에서 사용 됩니다.  
  
 프레임 창 클래스에서 파생 된 `CMDIChildWnd` 로 선언 되어야 합니다 `DECLARE_DYNCREATE` 하려면 위의 `RUNTIME_CLASS` 제대로 작동 하는 메커니즘입니다.  
  
 `CMDIChildWnd` 대부분의 기본 구현에서 클래스 상속 `CFrameWnd`합니다. 이러한 기능의 자세한 목록은 참조 하십시오는 [CFrameWnd](../../mfc/reference/cframewnd-class.md) 클래스 설명 합니다. `CMDIChildWnd` 클래스에 다음과 같은 추가 기능:  
  
-   와 함께에서 `CMultiDocTemplate` 클래스, 여러 `CMDIChildWnd` 동일한 문서 서식 파일에서 개체를 Windows 시스템 리소스를 저장 하 고 동일한 메뉴를 공유 합니다.  
  
-   현재 활성 MDI 자식 창 메뉴에는 완전히 MDI 프레임 창의 메뉴, 대체 하 고 현재 활성 MDI 자식 창의 캡션을 MDI 프레임 창 캡션의에 추가 됩니다. 함께 MDI 프레임 창 구현 되는 MDI 자식 창 함수의 추가 예제를 참조 하십시오.는 `CMDIFrameWnd` 클래스 설명 합니다.  
  
 C + +를 사용 하지 마십시오 **삭제** 연산자를 프레임 창을 삭제 합니다. 대신 `CWnd::DestroyWindow`를 사용하세요. `CFrameWnd` 구현의 `PostNcDestroy` 창이 소멸 될 때에 c + + 개체를 삭제 합니다. 사용자 프레임 창에 기본값을 닫을 때 `OnClose` 처리기를 호출 하는 `DestroyWindow`합니다.  
  
 대 한 자세한 내용은 `CMDIChildWnd`, 참조 [프레임 창](../../mfc/frame-windows.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 `CMDIChildWnd`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** afxwin.h  
  
##  <a name="cmdichildwnd"></a>CMDIChildWnd::CMDIChildWnd  
 생성 하는 호출을 `CMDIChildWnd` 개체입니다.  
  
```  
CMDIChildWnd();
```  
  
### <a name="remarks"></a>설명  
 호출 **만들기** 표시 창을 만들 수 있습니다.  
  
### <a name="example"></a>예  
  예를 참조 [CMDIChildWnd::Create](#create)합니다.  
  
##  <a name="create"></a>CMDIChildWnd::Create  
 Windows MDI 자식 창을 만들고에 연결 하려면이 함수 호출의 `CMDIChildWnd` 개체입니다.  
  
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
 Windows 클래스의 이름을 지정 하는 null로 끝나는 문자열을 가리키는 (한 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) 구조). 클래스 이름에 등록 된 모든 이름일 수 있습니다는 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) 전역 함수입니다. 해야 **NULL** 표준 `CMDIChildWnd`합니다.  
  
 `lpszWindowName`  
 창 이름을 나타내는 null로 끝나는 문자열을 가리킵니다. 제목 표시줄에 대 한 텍스트로 사용합니다.  
  
 `dwStyle`  
 창을 지정 [스타일](../../mfc/reference/styles-used-by-mfc.md#window-styles) 특성입니다. **WS_CHILD** 스타일을 사용 해야 합니다.  
  
 `rect`  
 크기와 창의 위치를 포함합니다. `rectDefault` 값 허용 되는 크기와 새 위치를 지정 하는 Windows `CMDIChildWnd`합니다.  
  
 `pParentWnd`  
 창의 부모를 지정합니다. 경우 **NULL**, 주 응용 프로그램 창을 사용 합니다.  
  
 `pContext`  
 지정 된 [CCreateContext](../../mfc/reference/ccreatecontext-structure.md) 구조입니다. 이 매개 변수 수 **NULL**합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 0이 아니고, 그렇지 않으면 0입니다.  
  
### <a name="remarks"></a>설명  
 현재 활성 MDI 자식 프레임 창에는 부모 프레임 창의 캡션을 결정할 수 있습니다. 이 기능을 해제 하면 비활성화는 **FWS_ADDTOTITLE** 자식 프레임 창의 스타일 비트입니다.  
  
 프레임 워크 자식 창을 만들 수는 사용자 명령에 대 한 응답에서이 멤버 함수를 호출 하 고 사용 하 여 프레임 워크는 `pContext` 자식 창 응용 프로그램에 연결 하도록 매개 변수입니다. 호출 하는 경우 **만들기**, `pContext` 수 **NULL**합니다.  
  
### <a name="example"></a>예  
 예제 1:  
  
 [!code-cpp[NVC_MFCWindowing#7](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_1.cpp)]  
  
### <a name="example"></a>예  
 예제 2:  
  
 [!code-cpp[NVC_MFCWindowing#8](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_2.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#9](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_3.cpp)]  
  
##  <a name="getmdiframe"></a>CMDIChildWnd::GetMDIFrame  
 MDI 부모 프레임을 반환 하려면이 함수를 호출 합니다.  
  
```  
CMDIFrameWnd* GetMDIFrame();
```  
  
### <a name="return-value"></a>반환 값  
 MDI 부모 프레임 창에 대 한 포인터입니다.  
  
### <a name="remarks"></a>설명  
 반환 하는 프레임은 두 명의 부모에서 제거 된 `CMDIChildWnd` 이 유형의 창의 부모인 **MDICLIENT** 을 관리 하는 `CMDIChildWnd` 개체입니다. 호출의 [GetParent](../../mfc/reference/cwnd-class.md#getparent) 반환할 멤버 함수는 `CMDIChildWnd` 개체의 직계 **MDICLIENT** 임시 파일로 부모 `CWnd` 포인터입니다.  
  
### <a name="example"></a>예  
  예를 참조 [CMDIFrameWnd::MDISetMenu](../../mfc/reference/cmdiframewnd-class.md#mdisetmenu)합니다.  
  
##  <a name="mdiactivate"></a>CMDIChildWnd::MDIActivate  
 MDI 프레임 창 독립적으로 MDI 자식 창이 활성화 하려면이 함수를 호출 합니다.  
  
```  
void MDIActivate();
```  
  
### <a name="remarks"></a>설명  
 활성화 되는 프레임을 마지막으로 활성화 된 자식 창도 활성화 됩니다.  
  
### <a name="example"></a>예  
  예를 참조 [CMDIFrameWnd::GetWindowMenuPopup](../../mfc/reference/cmdiframewnd-class.md#getwindowmenupopup)합니다.  
  
##  <a name="mdidestroy"></a>CMDIChildWnd::MDIDestroy  
 MDI 자식 창을 삭제 하려면이 멤버 함수를 호출 합니다.  
  
```  
void MDIDestroy();
```  
  
### <a name="remarks"></a>설명  
 멤버 함수 프레임 창에서 자식 창의 제목을 제거 및 자식 창을 비활성화 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#10](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_4.cpp)]  
  
##  <a name="mdimaximize"></a>CMDIChildWnd::MDIMaximize  
 MDI 자식 창을 최대화 하려면이 함수를 호출 합니다.  
  
```  
void MDIMaximize();
```  
  
### <a name="remarks"></a>설명  
 자식 창이 최대화 되었을 때 Windows 프레임 창의 클라이언트 영역 채우기의 클라이언트 영역을 찾을 수 있도록 크기가 조정 됩니다. 복원 하거나 자식 창을 닫을 수 있도록 Windows 프레임의 메뉴 모음에서 자식 창 컨트롤 메뉴를 배치 하 고 프레임 창 제목에 자식 창의 제목을 추가 합니다.  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#11](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_5.cpp)]  
  
##  <a name="mdirestore"></a>CMDIChildWnd::MDIRestore  
 MDI 자식 창에 최대화 또는 최소화 된 크기에서 복원 하려면이 함수를 호출 합니다.  
  
```  
void MDIRestore();
```  
  
### <a name="example"></a>예  
 [!code-cpp[NVC_MFCWindowing#12](../../mfc/reference/codesnippet/cpp/cmdichildwnd-class_6.cpp)]  
  
##  <a name="sethandles"></a>CMDIChildWnd::SetHandles  
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
 액셀러레이터 키 리소스의 핸들입니다.  
  
### <a name="remarks"></a>설명  
 MDI 자식 창 개체에서 사용 하는 메뉴 및 바로 가기 리소스를 설정 하려면이 함수를 호출 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MDI MFC 샘플](../../visual-cpp-samples.md)   
 [MFC 샘플 MDIDOCVW](../../visual-cpp-samples.md)   
 [MFC 샘플 SNAPVW](../../visual-cpp-samples.md)   
 [CFrameWnd 클래스](../../mfc/reference/cframewnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [CMDIFrameWnd 클래스](../../mfc/reference/cmdiframewnd-class.md)
