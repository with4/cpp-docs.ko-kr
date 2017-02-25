---
title: "TN001: 창 클래스 등록 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.registration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxRegisterClass 함수"
  - "TN001"
  - "WNDCLASS"
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# TN001: 창 클래스 등록
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 부분에서는 Microsoft Windows를 필요로 하는 특수한 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) 레지스터에 대한 MFC 루틴을 설명합니다.  MFC와 Windows에 의해 사용되는 특정 `WNDCLASS` 특성을 설명합니다.  
  
## 문제  
 Windows에서 `HWND` 처리기처럼, [CWnd](../mfc/reference/cwnd-class.md) 개체의 특성은 두 위치에 저정됩니다: window 개체와 `WNDCLASS`.  [CWnd::Create](../Topic/CWnd::Create.md) 와 `lpszClassName` 에서 [CFrameWnd::Create](../Topic/CFrameWnd::Create.md) 처럼 `WNDCLASS` 의 이름이 windows생성함수들로 전달됩니다.  
  
 이 `WNDCLASS` 는 네 가지 방법 중 하나를 통해 등록되어야 합니다:  
  
-   암시적으로 MFC를 사용하여 `WNDCLASS`를 제공합니다.  
  
-   암시적으로 Windows 컨트롤 \(또는 다른 컨트롤\)을 서브클래싱합니다.  
  
-   명시적으로 MFC [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) 또는 [AfxRegisterClass](../Topic/AfxRegisterClass.md) 을 호출합니다.  
  
-   명시적으로 Windows [RegisterClass](http://msdn.microsoft.com/library/windows/desktop/ms633586) 루틴을 호출합니다.  
  
## WNDCLASS 필드  
 `WNDCLASS` 구조체는 window 클래스를 설명하는 다양한 필드로 구성됩니다.  다음 표는 필드를 보여주고 MFC 응용프로그램에서 어떻게 그들을 사용하는지를 지정합니다.  
  
|필드|설명|  
|--------|--------|  
|`lpfnWndProc`|창 프로시져는 `AfxWndProc` 이 되어야만 합니다.|  
|`cbClsExtra`|사용되지 않습니다\(0 이되어야합니다.\).|  
|`cbWndExtra`|사용되지 않습니다\(0 이되어야합니다.\).|  
|`hInstance`|자동으로 [AfxGetInstanceHandle](../Topic/AfxGetInstanceHandle.md) 을 사용하여 채워집니다.|  
|`hIcon`|프레임 창에 대한 아이콘은, 아래를 참고하세요.|  
|`hCursor`|마우스가 창 위에 있을 때, 커서에 대해서는 아래를 참고하세요.|  
|`hbrBackground`|배경색은 아래를 참고하세요.|  
|`lpszMenuName`|사용되지 않습니다\(NULL이 되어야합니다.\)|  
|`lpszClassName`|클래스 이름은 아래를 참고하세요.|  
  
## WNDCLASSes를 제공합니다.  
 이전 버전의 MFC \(MFC 4.0 이전\)에, 미리 정의된 몇몇 Windows를 제공합니다.  이러한 창 클래스는 더 이상 기본적으로 제공되지 않습니다.  응용 프로그램은 적절한 매개변수와 함께 `AfxRegisterWndClass` 사용해야합니다.  
  
 만일 응용프로그램이 지정된 리소스 ID\(예를들어, AFX\_IDI\_STD\_FRAME\)를 사용하여 제공한다면, MFC는 이런 리소스를 사용합니다.  그렇지 않으면, 기본 리소스가 사용됩니다.  아이콘에 대해, 표준 응용 프로그램 아이콘이 사용되고, 커서의 경우, 표준 화살표 커서가 사용됩니다.  
  
 두 개의 아이콘이 단일 문서 형식을 사용하는 MDI응용프로그램들에서 지원됩니다: 한 아이콘은 메인 응용프로그램에 대한것이고, 다른 하나는 문서\/MDIChild 창에 대한 다른 아이콘입니다.  다른 아이콘들을 사용하는 다중 문서 형식들에서, 추가적인 `WNDCLASS`es 를 등록해야 하거나 [CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md) 사용해야 합니다.  
  
 `CFrameWnd::LoadFrame` 은 첫번째 매개변수로써 지정한 아이콘 ID과 다음 표준 특성들을 사용하여 `WNDCLASS` 을 등록합니다:  
  
-   클래스 스타일: CS\_DBLCLKS &#124; CS\_HREDRAW &#124; CS\_VREDRAW;  
  
-   AFX\_IDI\_STD\_FRAME 아이콘  
  
-   화살표 커서입니다.  
  
-   COLOR\_WINDOW 배경 색상  
  
 [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) 에 대한 커서와 배경색상의 값은 **MDICLIENT** 창으로 완벽하게 가려지는 `CMDIFrameWnd` 의 클라이언트 영역때문에 사용되지 않습니다.  Microsoft는 **MDICLIENT** 창의 서브클래싱을 권장 하지 않기 때문에 표준 색상을 사용하고, 가능하다면 커서 형식들을 사용합니다.  
  
## 서브클래싱과 컨트롤 슈퍼클래싱.  
 만일 창 컨트롤을 슈퍼클래스 또는 서브클래스 한다음,\(예를 들어, [CButton](../mfc/reference/cbutton-class.md)\) 클래스는 자동적으로 컨트롤의 Windows 구현에서 제공되는 `WNDCLASS` 특성을 얻습니다.  
  
## AfxRegisterWndClass 함수  
 MFC 창 클래스를 등록하기 위한 helper함수를 제공합니다.  특성의 집합\(창 클래스 스타일, 커서, 배경 브러쉬, 아이콘\)을 제공하고 종합적인 이름을 생성되고, 결과 창 클래스가 등록됩니다.  예를 들면 다음과 같습니다.  
  
```  
const char* AfxRegisterWndClass(UINT nClassStyle, HCURSOR hCursor, HBRUSH hbrBackground, HICON hIcon);  
```  
  
 함수는 등록된 창 클래스 이름으로 생성된 임시 문자열을 반환합니다.  이 함수에 관한 자세한 내용은 [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md)을 참고하세요.  
  
 반환된 문자열은 정적 문자열 버퍼에 대한 임시 포인터입니다.  이것은 `AfxRegisterWndClass` 에 대해 다음 호출까지 유효합니다.  만일 이 문자열에 대해 유지하길 원한다면, 다음 예제처럼, [CString](../atl-mfc-shared/using-cstring.md) 변수 에 이것을 저장합니다:  
  
```  
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);  
...  
CWnd* pWnd = new CWnd;  
pWnd->Create(strWndClass, ...);  
...  
```  
  
 만일 창 클래스의 등록이 실패한다면,\(잘못된 매개변수 또는 Windows 메모리를 벗어나기때문에\) `AfxRegisterWndClass` 는 [CResourceException](../mfc/reference/cresourceexception-class.md) 를 발생시킵니다.  
  
## RegisterClass 및 AfxRegisterClass 함수들  
 만일 `AfxRegisterWndClass` 이 제공하는 것보다 정교한 것을 원한다면, Windows API `RegisterClass` 또는 MFC 함수 `AfxRegisterClass` 을 호출할 수 있습니다.  `CWnd`, [CFrameWnd](../mfc/reference/cframewnd-class.md) 와 [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) `Create` 함수들은 첫 번째 매개변수로써 창 클래스에 대한 `lpszClassName` 문자열 이름을 사용합니다.  등록에 사용되는 방법에 관계 없이, 등록된 창 클래스 이름을 사용할 수 있습니다.  
  
 Win32에서 DLL에 `AfxRegisterClass`\(또는 `AfxRegisterWndClass`\) 을 사용하는 것은 중요합니다.  Win32는 DLL에 의해 등록된 클래스들이 자동적으로 등록이 해제되지 않으므로, DLL이 종료될때 명시적으로 등록을 해제해야합니다.  `RegisterClass` 대신 `AfxRegisterClass` 을 사용함으로써 이것은 자동적으로 처리됩니다.  `AfxRegisterClass` DLL에 의해 등록된 유일한 클래스들의 목록을 유지하고 DLL이 종료될때 자동적으로 등록을 해제합니다.  DLL에서 `RegisterClass` 을 사용하는 경우, DLL이 종료될 때\([DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583) 함수에서\) 모든 클래스들의 등록이 해제되는지 확인해야 합니다.  DLL을 사용하기 위해 다른 클라이언트 어플리케이션을 사용할 때, 예기치않은 실패에 대한 `RegisterClass` 을 야기할 수 있습니다.  
  
## 참고 항목  
 [번호별 기술 참고 사항](../mfc/technical-notes-by-number.md)   
 [범주별 기술 참고 사항](../mfc/technical-notes-by-category.md)