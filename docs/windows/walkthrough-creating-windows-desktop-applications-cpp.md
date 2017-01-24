---
title: "연습: Windows 데스크톱 응용 프로그램 만들기(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Windows 응용 프로그램[C++], Win32"
  - "WinMain"
  - "Win32 응용 프로그램[C++]"
  - "Windows API[C++]"
ms.assetid: a247a9af-aff1-4899-9577-5f8104a0afbb
caps.latest.revision: 27
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 연습: Windows 데스크톱 응용 프로그램 만들기(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 연습에서는 창에 "Hello, World\!"를 표시하는 기본 Windows 데스크톱 응용 프로그램을 만드는 방법을 보여 줍니다. 이 연습에서 개발하는 코드를 패턴으로 사용하여 다른 Windows 데스크톱 응용 프로그램을 만들 수 있습니다.  
  
 Win32 API\(Windows API라고도 함\)는 Windows 응용 프로그램을 만들기 위한 C 기반 프레임워크입니다. Win32 API에 대한 자세한 내용은 [Windows API](https://msdn.microsoft.com/en-us/library/cc433218.aspx)를 참조하세요.  
  
> [!IMPORTANT]
>  이 문서의 단계에서 특정 세그먼트를 더 분명히 설명할 수 있도록 작업 응용 프로그램에 필요한 일부 코드 문을 생략할 수 있습니다\(예: include 지시문 및 전역 변수 선언\). 이 문서의 끝에 있는 **예제** 섹션에서는 전체 코드를 보여 줍니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 C\+\+ 언어의 기본적인 사항을 알고 있어야 합니다.  
  
 비디오 데모를 보려면 Visual Studio 2008 설명서에서 [비디오 방법: Win32 응용 프로그램 만들기\(C\+\+\)](http://go.microsoft.com/fwlink/?LinkId=102471)\(영문\)를 참조하세요.  
  
### Win32 기반 프로젝트를 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자의 왼쪽 창에서 **설치된 템플릿**, **Visual C\+\+**를 차례로 클릭하고 **Win32**를 선택합니다. 가운데 창에서 **Win32 프로젝트**를 선택합니다.  
  
     **이름** 상자에 프로젝트 이름을 입력합니다\(예: `win32app`\).**확인**을 클릭합니다.  
  
3.  **Win32 응용 프로그램 마법사**의 시작 페이지에서 **다음**을 클릭합니다.  
  
4.  응용 프로그램 설정 페이지의 **응용 프로그램 종류** 아래에서 **Windows 응용 프로그램**을 선택합니다.**추가 옵션**에서 **빈 프로젝트**를 선택합니다.**마침**을 클릭하여 프로젝트를 만듭니다.  
  
5.  **솔루션 탐색기**에서 Win32app 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**를 클릭한 다음 **새 항목**을 클릭합니다.**새 항목 추가** 대화 상자에서 **C\+\+ 파일\(.cpp\)**을 선택합니다.**이름** 상자에 파일 이름을 입력합니다\(예: `GT_HelloWorldWin32.cpp`\).**추가**를 클릭합니다.  
  
### Windows 데스크톱 응용 프로그램을 시작하려면  
  
1.  모든 C 응용 프로그램 및 C\+\+ 응용 프로그램에 시작 지점으로 `main` 함수가 있어야 하는 것처럼 모든 Win32 기반 응용 프로그램에는 `WinMain` 함수가 있어야 합니다.`WinMain`에는 다음 구문이 있습니다.  
  
    ```  
    int WINAPI WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nCmdShow);  
    ```  
  
     이 함수의 반환 값 및 매개 변수에 대한 자세한 내용은 [WinMain 함수](http://msdn.microsoft.com/library/windows/desktop/ms633559)를 참조하세요.  
  
2.  응용 프로그램 코드에는 기존 정의를 사용해야 하므로 파일에 include 문을 추가합니다.  
  
    ```  
    #include <windows.h> #include <stdlib.h> #include <string.h> #include <tchar.h>  
    ```  
  
3.  `WinMain` 함수 이외에 모든 Windows 데스크톱 응용 프로그램에는 창 프로시저 함수도 있어야 합니다. 일반적으로 이 함수를 `WndProc`라고 합니다.`WndProc`에는 다음 구문이 있습니다.  
  
    ```  
    LRESULT CALLBACK WndProc(HWND, UINT, WPARAM, LPARAM);  
    ```  
  
     이 함수는 응용 프로그램이 운영 체제에서 받는 대부분 *메시지*를 처리합니다. 예를 들어 **확인** 단추가 있는 대화 상자가 포함된 응용 프로그램에서 사용자가 단추를 클릭하면 운영 체제에서는 단추가 클릭되었다는 메시지를 응용 프로그램에 보냅니다.`WndProc`가 해당 이벤트에 응답해야 합니다. 예제에서 적절한 응답으로 대화 상자를 닫을 수 있습니다.  
  
     자세한 내용은 [창 프로시저](http://msdn.microsoft.com/library/windows/desktop/ms632593)를 참조하세요.  
  
### WinMain 함수에 기능을 추가하려면  
  
1.  `WinMain` 함수에서 [WNDCLASSEX](http://msdn.microsoft.com/library/windows/desktop/ms633577) 형식의 창 클래스 구조를 만듭니다. 이 구조에는 응용 프로그램 아이콘, 창 배경색, 제목 표시줄에 표시할 이름, 창 프로시저 함수 이름 등의 창에 대한 정보가 포함됩니다. 다음 예제에서는 일반적인 `WNDCLASSEX` 구조를 보여 줍니다.  
  
    ```  
    WNDCLASSEX wcex; wcex.cbSize = sizeof(WNDCLASSEX); wcex.style          = CS_HREDRAW | CS_VREDRAW; wcex.lpfnWndProc    = WndProc; wcex.cbClsExtra     = 0; wcex.cbWndExtra     = 0; wcex.hInstance      = hInstance; wcex.hIcon          = LoadIcon(hInstance, MAKEINTRESOURCE(IDI_APPLICATION)); wcex.hCursor        = LoadCursor(NULL, IDC_ARROW); wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1); wcex.lpszMenuName   = NULL; wcex.lpszClassName  = szWindowClass; wcex.hIconSm        = LoadIcon(wcex.hInstance, MAKEINTRESOURCE(IDI_APPLICATION));  
    ```  
  
     이 구조의 필드에 대한 자세한 내용은 [WNDCLASSEX](http://msdn.microsoft.com/library/windows/desktop/ms633577)를 참조하세요.  
  
2.  창 클래스를 만들었으므로 등록해야 합니다.[RegisterClassEx](http://msdn.microsoft.com/library/windows/desktop/ms633587) 함수를 사용하고 창 클래스 구조를 인수로 전달합니다.  
  
    ```  
    if (!RegisterClassEx(&wcex)) { MessageBox(NULL, _T("Call to RegisterClassEx failed!"), _T("Win32 Guided Tour"), NULL); return 1; }  
    ```  
  
3.  이제 창을 만들 수 있습니다.[CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) 함수를 사용합니다.  
  
    ```  
    static TCHAR szWindowClass[] = _T("win32app"); static TCHAR szTitle[] = _T("Win32 Guided Tour Application"); // The parameters to CreateWindow explained: // szWindowClass: the name of the application // szTitle: the text that appears in the title bar // WS_OVERLAPPEDWINDOW: the type of window to create // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y) // 500, 100: initial size (width, length) // NULL: the parent of this window // NULL: this application does not have a menu bar // hInstance: the first parameter from WinMain // NULL: not used in this application HWND hWnd = CreateWindow( szWindowClass, szTitle, WS_OVERLAPPEDWINDOW, CW_USEDEFAULT, CW_USEDEFAULT, 500, 100, NULL, NULL, hInstance, NULL ); if (!hWnd) { MessageBox(NULL, _T("Call to CreateWindow failed!"), _T("Win32 Guided Tour"), NULL); return 1; }  
    ```  
  
     이 함수는 창 핸들인 HWND를 반환합니다. 자세한 내용은 [Windows 데이터 형식](http://msdn.microsoft.com/library/windows/desktop/aa383751)을 참조하세요.  
  
4.  이제 다음 코드를 사용하여 창을 표시합니다.  
  
    ```  
    // The parameters to ShowWindow explained: // hWnd: the value returned from CreateWindow // nCmdShow: the fourth parameter from WinMain ShowWindow(hWnd, nCmdShow); UpdateWindow(hWnd);  
    ```  
  
     아직 `WndProc` 함수를 구현하지 않았으므로 이때 표시된 창에는 많은 콘텐츠가 없습니다.  
  
5.  이제 운영 체제에서 보내는 메시지를 받기 위한 메시지 루프를 추가합니다. 응용 프로그램이 메시지를 받으면 이 루프가 메시지를 처리하도록 `WndProc` 함수로 디스패치합니다. 메시지 루프는 다음 코드와 유사합니다.  
  
    ```  
    MSG msg; while (GetMessage(&msg, NULL, 0, 0)) { TranslateMessage(&msg); DispatchMessage(&msg); } return (int) msg.wParam;  
    ```  
  
     메시지 루프의 구조 및 함수에 대한 자세한 내용은 [MSG](http://msdn.microsoft.com/library/windows/desktop/ms644958), [GetMessage](http://msdn.microsoft.com/library/windows/desktop/ms644936), [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) 및 [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934)를 참조하세요.  
  
     이때 `WinMain` 함수는 다음 코드와 유사합니다.  
  
    ```  
    int WINAPI WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nCmdShow) { WNDCLASSEX wcex; wcex.cbSize = sizeof(WNDCLASSEX); wcex.style          = CS_HREDRAW | CS_VREDRAW; wcex.lpfnWndProc    = WndProc; wcex.cbClsExtra     = 0; wcex.cbWndExtra     = 0; wcex.hInstance      = hInstance; wcex.hIcon          = LoadIcon(hInstance, MAKEINTRESOURCE(IDI_APPLICATION)); wcex.hCursor        = LoadCursor(NULL, IDC_ARROW); wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1); wcex.lpszMenuName   = NULL; wcex.lpszClassName  = szWindowClass; wcex.hIconSm        = LoadIcon(wcex.hInstance, MAKEINTRESOURCE(IDI_APPLICATION)); if (!RegisterClassEx(&wcex)) { MessageBox(NULL, _T("Call to RegisterClassEx failed!"), _T("Win32 Guided Tour"), NULL); return 1; } hInst = hInstance; // Store instance handle in our global variable // The parameters to CreateWindow explained: // szWindowClass: the name of the application // szTitle: the text that appears in the title bar // WS_OVERLAPPEDWINDOW: the type of window to create // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y) // 500, 100: initial size (width, length) // NULL: the parent of this window // NULL: this application dows not have a menu bar // hInstance: the first parameter from WinMain // NULL: not used in this application HWND hWnd = CreateWindow( szWindowClass, szTitle, WS_OVERLAPPEDWINDOW, CW_USEDEFAULT, CW_USEDEFAULT, 500, 100, NULL, NULL, hInstance, NULL ); if (!hWnd) { MessageBox(NULL, _T("Call to CreateWindow failed!"), _T("Win32 Guided Tour"), NULL); return 1; } // The parameters to ShowWindow explained: // hWnd: the value returned from CreateWindow // nCmdShow: the fourth parameter from WinMain ShowWindow(hWnd, nCmdShow); UpdateWindow(hWnd); // Main message loop: MSG msg; while (GetMessage(&msg, NULL, 0, 0)) { TranslateMessage(&msg); DispatchMessage(&msg); } return (int) msg.wParam; }  
    ```  
  
### WndProc 함수에 기능을 추가하려면  
  
1.  `WndProc` 함수에서 응용 프로그램이 받는 메시지를 처리하게 하려면 switch 문을 구현합니다.  
  
     처리할 첫 번째 메시지는 [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) 메시지입니다. 응용 프로그램은 표시된 창 일부를 업데이트해야 할 때 이 메시지를 받습니다. 창이 처음 표시된 경우 창을 모두 업데이트해야 합니다.  
  
     `WM_PAINT` 메시지를 처리하려면 먼저 [BeginPaint](http://msdn.microsoft.com/library/windows/desktop/dd183362)를 호출하고, 모든 논리를 처리하여 창에 텍스트, 단추 및 기타 컨트롤을 배치하고, [EndPaint](http://msdn.microsoft.com/library/windows/desktop/dd162598)를 호출합니다. 이 응용 프로그램에 대한 시작 호출과 종료 호출 간의 논리는 창에 문자열 "Hello, World\!"를 표시하는 것입니다. 다음 코드에서 [TextOut](http://msdn.microsoft.com/library/windows/desktop/dd145133) 함수는 문자열을 표시하는 데 사용됩니다.  
  
    ```  
    PAINTSTRUCT ps; HDC hdc; TCHAR greeting[] = _T("Hello, World!"); switch (message) { case WM_PAINT: hdc = BeginPaint(hWnd, &ps); // Here your application is laid out. // For this introduction, we just print out "Hello, World!" // in the top left corner. TextOut(hdc, 5, 5, greeting, _tcslen(greeting)); // End application-specific layout section. EndPaint(hWnd, &ps); break; }  
    ```  
  
2.  일반적으로 응용 프로그램에서는 [WM\_CREATE](http://msdn.microsoft.com/library/windows/desktop/ms632619) 및 [WM\_DESTROY](http://msdn.microsoft.com/library/windows/desktop/ms632620)와 같은 많은 기타 메시지를 처리합니다. 다음 코드에서는 기본적인 전체 `WndProc` 함수를 보여 줍니다.  
  
    ```  
    LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam) { PAINTSTRUCT ps; HDC hdc; TCHAR greeting[] = _T("Hello, World!"); switch (message) { case WM_PAINT: hdc = BeginPaint(hWnd, &ps); // Here your application is laid out. // For this introduction, we just print out "Hello, World!" // in the top left corner. TextOut(hdc, 5, 5, greeting, _tcslen(greeting)); // End application specific layout section. EndPaint(hWnd, &ps); break; case WM_DESTROY: PostQuitMessage(0); break; default: return DefWindowProc(hWnd, message, wParam, lParam); break; } return 0; }  
    ```  
  
##  <a name="example"></a> 예제  
  
#### 이 예제를 빌드하려면  
  
1.  이 연습의 앞부분에 있는 "Win32 기반 프로젝트를 만들려면"에 표시된 대로 Win32 기반 프로젝트를 만듭니다.  
  
2.  이 단계에 따라 코드를 복사하고 GT\_HelloWorldWin32.cpp 소스 파일에 붙여넣습니다.  
  
3.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
4.  응용 프로그램을 실행하려면 F5 키를 누릅니다. 텍스트 "Hello World\!"가 포함된 창이 디스플레이의 왼쪽 위에 표시됩니다.  
  
### 코드  
  
```  
// GT_HelloWorldWin32.cpp // compile with: /D_UNICODE /DUNICODE /DWIN32 /D_WINDOWS /c #include <windows.h> #include <stdlib.h> #include <string.h> #include <tchar.h> // Global variables // The main window class name. static TCHAR szWindowClass[] = _T("win32app"); // The string that appears in the application's title bar. static TCHAR szTitle[] = _T("Win32 Guided Tour Application"); HINSTANCE hInst; // Forward declarations of functions included in this code module: LRESULT CALLBACK WndProc(HWND, UINT, WPARAM, LPARAM); int WINAPI WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nCmdShow) { WNDCLASSEX wcex; wcex.cbSize = sizeof(WNDCLASSEX); wcex.style          = CS_HREDRAW | CS_VREDRAW; wcex.lpfnWndProc    = WndProc; wcex.cbClsExtra     = 0; wcex.cbWndExtra     = 0; wcex.hInstance      = hInstance; wcex.hIcon          = LoadIcon(hInstance, MAKEINTRESOURCE(IDI_APPLICATION)); wcex.hCursor        = LoadCursor(NULL, IDC_ARROW); wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1); wcex.lpszMenuName   = NULL; wcex.lpszClassName  = szWindowClass; wcex.hIconSm        = LoadIcon(wcex.hInstance, MAKEINTRESOURCE(IDI_APPLICATION)); if (!RegisterClassEx(&wcex)) { MessageBox(NULL, _T("Call to RegisterClassEx failed!"), _T("Win32 Guided Tour"), NULL); return 1; } hInst = hInstance; // Store instance handle in our global variable // The parameters to CreateWindow explained: // szWindowClass: the name of the application // szTitle: the text that appears in the title bar // WS_OVERLAPPEDWINDOW: the type of window to create // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y) // 500, 100: initial size (width, length) // NULL: the parent of this window // NULL: this application does not have a menu bar // hInstance: the first parameter from WinMain // NULL: not used in this application HWND hWnd = CreateWindow( szWindowClass, szTitle, WS_OVERLAPPEDWINDOW, CW_USEDEFAULT, CW_USEDEFAULT, 500, 100, NULL, NULL, hInstance, NULL ); if (!hWnd) { MessageBox(NULL, _T("Call to CreateWindow failed!"), _T("Win32 Guided Tour"), NULL); return 1; } // The parameters to ShowWindow explained: // hWnd: the value returned from CreateWindow // nCmdShow: the fourth parameter from WinMain ShowWindow(hWnd, nCmdShow); UpdateWindow(hWnd); // Main message loop: MSG msg; while (GetMessage(&msg, NULL, 0, 0)) { TranslateMessage(&msg); DispatchMessage(&msg); } return (int) msg.wParam; } // //  FUNCTION: WndProc(HWND, UINT, WPARAM, LPARAM) // //  PURPOSE:  Processes messages for the main window. // //  WM_PAINT    - Paint the main window //  WM_DESTROY  - post a quit message and return // // LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam) { PAINTSTRUCT ps; HDC hdc; TCHAR greeting[] = _T("Hello, World!"); switch (message) { case WM_PAINT: hdc = BeginPaint(hWnd, &ps); // Here your application is laid out. // For this introduction, we just print out "Hello, World!" // in the top left corner. TextOut(hdc, 5, 5, greeting, _tcslen(greeting)); // End application-specific layout section. EndPaint(hWnd, &ps); break; case WM_DESTROY: PostQuitMessage(0); break; default: return DefWindowProc(hWnd, message, wParam, lParam); break; } return 0; }  
```  
  
## 참고 항목  
 [Windows 데스크톱 응용 프로그램](../windows/windows-desktop-applications-cpp.md)