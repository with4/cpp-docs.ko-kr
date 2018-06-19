---
title: 'TN001: 창 클래스 등록 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.registration
dev_langs:
- C++
helpviewer_keywords:
- TN001
- WNDCLASS [MFC]
- AfxRegisterClass function
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 245ffcb66223813c7146c50c964cd97203ed8d53
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383856"
---
# <a name="tn001-window-class-registration"></a>TN001: 창 클래스 등록
이 노트는 특수를 등록 하는 MFC 루틴에 설명 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)es Microsoft Windows에서 필요 합니다. 특정 `WNDCLASS` MFC 및 Windows에서 사용 하는 특성은 설명 합니다.  
  
## <a name="the-problem"></a>문제  
 특성은 [CWnd](../mfc/reference/cwnd-class.md) 개체와 같이 `HWND` Windows에서 처리할 두 장소에 저장 됩니다: 창 개체 및 `WNDCLASS`합니다. 이름에서 `WNDCLASS` 등 일반 창 만들기 함수에 전달 됩니다 [CWnd::Create](../mfc/reference/cwnd-class.md#create) 및 [CFrameWnd::Create](../mfc/reference/cframewnd-class.md#create) 에 `lpszClassName` 매개 변수입니다.  
  
 이 `WNDCLASS` 네 가지 의미 중 하나를 통해 등록 되어야 합니다.  
  
-   제공 된 MFC를 사용 하 여 암시적으로 `WNDCLASS`합니다.  
  
-   Windows 컨트롤 (또는 다른 일부 컨트롤)를 서브클래싱에 의해 암시적으로 합니다.  
  
-   MFC를 호출 하 여 명시적으로 [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass) 또는 [AfxRegisterClass](../mfc/reference/application-information-and-management.md#afxregisterclass)합니다.  
  
-   Windows 루틴을 호출 하 여 명시적으로 [RegisterClass](http://msdn.microsoft.com/library/windows/desktop/ms633586)합니다.  
  
## <a name="wndclass-fields"></a>WNDCLASS 필드  
 `WNDCLASS` 창 클래스를 설명 하는 다양 한 필드의 구조 구성 됩니다. 다음 표에서 필드가 표시 하 고 MFC 응용 프로그램에서 사용 하는 방법을 지정 합니다.  
  
|필드|설명|  
|-----------|-----------------|  
|`lpfnWndProc`|창 프로시저 여야는 `AfxWndProc`|  
|`cbClsExtra`|사용 되지 않습니다 (0 이어야 함)|  
|`cbWndExtra`|사용 되지 않습니다 (0 이어야 함)|  
|`hInstance`|자동으로 채워진 [AfxGetInstanceHandle](../mfc/reference/application-information-and-management.md#afxgetinstancehandle)|  
|`hIcon`|프레임 창에 대 한 아이콘 아래를 참조 하세요|  
|`hCursor`|아래 창 위에 마우스가 시기에 대 한 커서를 참조 하십시오.|  
|`hbrBackground`|배경색, 아래 참조|  
|`lpszMenuName`|사용 되지 않습니다 (NULL 이어야 함)|  
|`lpszClassName`|클래스 이름, 아래 참조|  
  
## <a name="provided-wndclasses"></a>WNDCLASSes 제공  
 이전 버전의 MFC (MFC 4.0의 경우) 하기 전에 몇 가지 미리 정의 된 창 클래스를 제공 합니다. 이러한 창 클래스는 더 이상 기본적으로 제공 됩니다. 응용 프로그램 사용 해야 `AfxRegisterWndClass` 적절 한 매개 변수를 사용 합니다.  
  
 지정 된 리소스 ID (예를 들어 AFX_IDI_STD_FRAME)를 사용 하 여 리소스를 제공 하는 응용 프로그램, MFC는 해당 리소스를 사용 합니다. 그렇지 않으면 기본 리소스를 사용 합니다. 아이콘에 대 한 표준 응용 프로그램 아이콘이 사용 하 고는 커서에 대 한 표준 화살표 커서 사용 됩니다.  
  
 단일 문서 형식과 MDI 응용 프로그램을 지원 하는 두 개의 아이콘: 즉, 아이콘 문서/MDIChild windows에 대 한 다른 아이콘은 주 응용 프로그램에 대 한 아이콘 중 하나입니다. 서로 다른 아이콘으로 여러 문서 형식에 대해 추가 등록 해야 `WNDCLASS`(예) 또는 사용 하 여는 [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) 함수입니다.  
  
 `CFrameWnd::LoadFrame` 등록 된 `WNDCLASS` 첫 번째 매개 변수 및 다음과 같은 표준 속성으로 지정 하는 아이콘 ID를 사용 하 여:  
  
-   클래스 스타일: CS_DBLCLKS &#124; CS_HREDRAW &#124; CS_VREDRAW;  
  
-   AFX_IDI_STD_FRAME 아이콘  
  
-   화살표 커서  
  
-   COLOR_WINDOW 배경색  
  
 배경색 및에 대 한 커서에 대 한 값은 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) 의 클라이언트 영역 이후 사용 되지 않습니다는 `CMDIFrameWnd` 가 완전히 포함는 **MDICLIENT** 창. Microsoft는 서브클래싱 것을 권장 하지는 **MDICLIENT** 표준 색과 가능한 경우 커서 유형 창을 사용 합니다.  
  
## <a name="subclassing-and-superclassing-controls"></a>슈퍼 클 래 싱 컨트롤과 서브클래싱  
 Windows 슈퍼 클래스 또는 서브 클래스를 만들 제어 하는 경우 (예를 들어 [CButton](../mfc/reference/cbutton-class.md)) 클래스에 자동으로 가져옵니다. 그런 다음는 `WNDCLASS` 해당 컨트롤의 Windows 구현에 제공 된 특성입니다.  
  
## <a name="the-afxregisterwndclass-function"></a>AfxRegisterWndClass 함수  
 MFC 창 클래스 등록 하기 위한 도우미 함수를 제공 합니다. 특성 (예: 창 클래스 스타일, 커서, 배경 브러시 및 아이콘) 집합이 들어 가상 이름이 생성 되 고 결과 창 클래스를 등록 합니다. 예를 들어 개체에 적용된  
  
```  
const char* AfxRegisterWndClass(UINT nClassStyle,
    HCURSOR hCursor,
    HBRUSH hbrBackground,
    HICON hIcon);
```  
  
 이 함수는 임시 생성 된 등록 된 창 클래스 이름 문자열을 반환합니다. 이 함수에 대 한 자세한 내용은 참조 [AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass)합니다.  
  
 반환 된 문자열에는 정적 문자열 버퍼에 임시 포인터입니다. 다음에 호출할 때까지 올바른지 `AfxRegisterWndClass`합니다. 이 문자열 주위를 유지 하려는 경우에 저장 한 [CString](../atl-mfc-shared/using-cstring.md) 다음이 예제와 같이 변수:  
  
```  
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);

...  
CWnd* pWnd = new CWnd;  
pWnd->Create(strWndClass, ...);

...  
```  
  
 `AfxRegisterWndClass` throw 합니다는 [CResourceException](../mfc/reference/cresourceexception-class.md) 창 클래스 등록 (인해 잘못 된 매개 변수 또는 Windows 메모리 부족)에 실패 하는지 합니다.  
  
## <a name="the-registerclass-and-afxregisterclass-functions"></a>RegisterClass 및 AfxRegisterClass 함수  
 수행 하려는 경우 아무 것도 더 복잡 한 기능 보다 `AfxRegisterWndClass` 제공, Windows API를 호출할 수 `RegisterClass` 또는 MFC 함수 `AfxRegisterClass`합니다. `CWnd`, [CFrameWnd](../mfc/reference/cframewnd-class.md) 및 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) `Create` 함수는 `lpszClassName` 첫 번째 매개 변수로 창 클래스에 대 한 문자열 이름입니다. 등록에 사용 되는 방법에 관계 없이 등록 된 창 클래스 이름에 사용할 수 있습니다.  
  
 사용 해야 `AfxRegisterClass` (또는 `AfxRegisterWndClass`)에서 Win32 DLL에 있습니다. Win32 하므로 명시적으로 등록을 취소 해야 클래스 DLL 종료 될 때 DLL을 등록 하는 클래스 자동으로 등록 해제 하지 않습니다. 사용 하 여 `AfxRegisterClass` 대신 `RegisterClass` 이를 자동으로 처리 됩니다. `AfxRegisterClass` 고유 클래스 목록이 DLL에서 등록 하 고는 자동으로 등록을 취소 하는 DLL 종료 될 때 유지 관리 합니다. 사용 하는 경우 `RegisterClass` DLL 종료 될 때 모든 클래스는 등록 된 수 있는지 확인 해야 DLL에서 (에서 프로그램 [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583) 함수). 이렇게 하지 않으면 발생할 수 있습니다 `RegisterClass` 다른 클라이언트 응용 프로그램이 DLL을 사용 하려고 할 때 예기치 않게 실패할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)

