---
title: "연습: 기존의 Windows 데스크톱 응용 프로그램 (c + +) 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 1/11/2018
ms.reviewer: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce3c18abbace2181b2d31e0621b6e376021be68a
ms.sourcegitcommit: c2e990450ccd528d85b2783fbc63042612987cfd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2018
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>연습: 기존의 Windows 데스크톱 응용 프로그램 (c + +) 만들기

이 연습에서는 Visual Studio에서 기존 Windows 데스크톱 응용 프로그램을 만드는 방법을 보여 줍니다. 예제 응용 프로그램을 만듭니다는 Windows API를 사용 하 여 "Hello, Windows 바탕 화면!"을 표시 하려면 줍니다. 이 연습에서 개발하는 코드를 패턴으로 사용하여 다른 Windows 데스크톱 응용 프로그램을 만들 수 있습니다.

Windows API (라고도: Win32 API, Windows 데스크톱 API 및 Windows 클래식 API)는 Windows 응용 프로그램을 만들기 위한 C 언어를 기반으로 합니다. 그 1980 이후 존재 있었고 년 Windows 응용 프로그램을 만드는 데 사용 된 합니다. .NET 프레임 워크, MFC 및 ATL 등이 API를 기반으로 빌드되어 더 고급 및 프로그램을 보다 쉽게 프레임 워크입니다. C +로 작성 된 UWP 및 스토어 앱에 대 한 가장 최신 코드 + WinRT 아래이 API를 사용 합니다. Windows API에 대 한 자세한 내용은 참조 [Windows API 지](https://msdn.microsoft.com/library/windows/desktop/ff818516.aspx)합니다. 여러 가지 방법으로 Windows 응용 프로그램을 만드는 첫 번째 했습니다.

> [!IMPORTANT]
> 간단히 하기 위해 텍스트에는 일부 코드 문은 생략 됩니다. [코드](#build-the-code) 섹션 끝이 문서에는 전체 코드를 보여 줍니다.

## <a name="prerequisites"></a>필수 구성 요소

- Microsoft Windows 7 이상을 실행 하는 컴퓨터입니다. 개발 환경을 최적화 하려면 Windows 10이 좋습니다.

- Visual Studio 2017의 복사본입니다. 다운로드 하 고 Visual Studio를 설치 하는 방법에 대 한 정보를 참조 하십시오. [Visual Studio 설치 2017](/visualstudio/install/install-visual-studio)합니다. 설치 관리자를 실행 하는 경우 다음 사항을 확인는 **c + + 데스크톱 개발** 작업을 선택 합니다. Visual Studio를 설치할 때이 작업을 설치 하지 않은 경우 걱정 하지 마십시오. 설치 프로그램을 다시 실행 하 고 지금 설치 수 있습니다.

   ![C + + 데스크톱 개발](../build/media/desktop-development-with-cpp.png "c + + 데스크톱 개발")

- Visual Studio IDE를 사용 하 여 기본적인 이해 해야 합니다. 하기 전에 Windows 데스크톱 앱을 사용한 경우 아마도 유지할 수 있습니다. 참조에 대 한 소개 [Visual Studio IDE 기능 둘러보기](/visualstudio/ide/visual-studio-ide)합니다.

- 충분히 진행 하는 c + + 언어의 기본적인 사항을 이해 합니다. 스 러 너무 복잡 하는 아무 것도 안 합니다.

## <a name="create-a-windows-desktop-project"></a>Windows 데스크톱 프로젝트 만들기

다음 단계를 첫 번째 Windows 데스크톱 프로젝트를 만들고 작동 하는 Windows 데스크톱 응용 프로그램에 대 한 코드를 입력 합니다. 버전의 Visual Studio 2017 15.3 버전 보다 오래 된 Visual Studio를 사용 하는 경우으로 바로 이동 [Visual Studio 2017 RTM에서 Windows 데스크톱 프로젝트를 만들려면](#create-in-vs2017-rtm)합니다.

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017-update-153-and-later"></a>Visual Studio 2017 업데이트 15.3 및 이후 버전 Windows 데스크톱 프로젝트를 만들려면

1. **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택합니다.

1. 에 **새 프로젝트** 대화 상자의 왼쪽된 창에서 **설치 됨**, **Visual c + +**을 선택한 후 **Windows 바탕 화면**합니다. 가운데 창에서 선택 **Windows 바탕 화면 마법사**합니다.

   에 **이름** 상자 예를 들어 프로젝트에 대 한 이름을 입력 합니다 *DesktopApp*합니다. **확인**을 선택합니다.

   ![DesktopApp 프로젝트 이름을](../build/media/desktop-app-new-project-name-153.png "DesktopApp 프로젝트 이름을")

1. 에 **Windows 데스크톱 프로젝트** 대화 아래 **응용 프로그램 종류**선택, **Windows 응용 프로그램 (.exe)**합니다. **추가 옵션**에서 **빈 프로젝트**를 선택합니다. 선택 **확인** 프로젝트를 만듭니다.

   ![Windows 데스크톱 프로젝트 마법사에서 DesktopApp 만들기](../build/media/desktop-app-new-project-wizard-153.png "DesktopApp Windows 데스크톱 프로젝트 마법사에서 만들기")

1. **솔루션 탐색기**, 마우스 오른쪽 단추로 클릭는 **DesktopApp** 프로젝트 **추가**를 선택한 후 **새 항목**합니다.

   ![DesktopApp 프로젝트에 새 항목 추가](../build/media/desktop-app-project-add-new-item-153.gif "DesktopApp 프로젝트에 새 항목 추가")

1. **새 항목 추가** 대화 상자에서 **C++ 파일(.cpp)**을 선택합니다. 에 **이름** 상자 예를 들어 파일에 대 한 이름을 입력 합니다 *HelloWindowsDesktop.cpp*합니다. **추가**를 선택합니다.

   ![추가.cpp 파일을 DesktopApp 프로젝트](../build/media/desktop-app-add-cpp-file-153.png "DesktopApp 프로젝트에.cpp 파일 추가")

프로젝트가 이제 만들어지고 프로그램 소스 파일은 편집기에서 열립니다. 계속 하려면으로 바로 이동 [코드를 만들](#create-the-code)합니다.

### <a id="create-in-vs2017-rtm"></a>Visual Studio 2017 RTM에서 Windows 데스크톱 프로젝트를 만들려면

1. **파일** 메뉴에서 **새로 만들기**, **프로젝트**를 차례로 선택합니다.

1. 에 **새 프로젝트** 대화 상자의 왼쪽된 창에서 **설치 됨**, **템플릿**, **Visual c + +**를 선택한 후 **Win32**합니다. 가운데 창에서 **Win32 프로젝트**를 선택합니다.

   에 **이름** 상자 예를 들어 프로젝트에 대 한 이름을 입력 합니다 *DesktopApp*합니다. **확인**을 선택합니다.

   ![DesktopApp 프로젝트 이름을](../build/media/desktop-app-new-project-name-150.png "DesktopApp 프로젝트 이름을")

1. 에 **개요** 의 페이지는 **Win32 응용 프로그램 마법사**, 선택 **다음**합니다.

   ![Win32 응용 프로그램 마법사 개요에서 DesktopApp 만들기](../build/media/desktop-app-win32-wizard-overview-150.png "DesktopApp Win32 응용 프로그램 마법사 개요에서 만들기")

1. 에 **응용 프로그램 설정** 페이지의 **응용 프로그램 종류**선택, **Windows 응용 프로그램**합니다. **추가 옵션**에서 **빈 프로젝트**를 선택합니다. 선택 **마침** 프로젝트를 만듭니다.

   ![Win32 응용 프로그램 마법사 설정에서 DesktopApp 만들기](../build/media/desktop-app-win32-wizard-settings-150.png "DesktopApp Win32 응용 프로그램 마법사 설정에서 만들기")

1. **솔루션 탐색기**DesktopApp 프로젝트를 마우스 오른쪽 단추로 선택 **추가**를 선택한 후 **새 항목**합니다.

   ![DesktopApp 프로젝트에 새 항목 추가](../build/media/desktop-app-project-add-new-item-150.gif "DesktopApp 프로젝트에 새 항목 추가")

1. **새 항목 추가** 대화 상자에서 **C++ 파일(.cpp)**을 선택합니다. 에 **이름** 상자 예를 들어 파일에 대 한 이름을 입력 합니다 *HelloWindowsDesktop.cpp*합니다. **추가**를 선택합니다.

   ![추가.cpp 파일을 DesktopApp 프로젝트](../build/media/desktop-app-add-cpp-file-150.png "DesktopApp 프로젝트에.cpp 파일 추가")

프로젝트가 이제 만들어지고 프로그램 소스 파일은 편집기에서 열립니다.

## <a name="create-the-code"></a>코드 만들기

다음으로, Visual Studio의 Windows 데스크톱 응용 프로그램에 대 한 코드를 작성 하는 방법을 설명 합니다.

### <a name="to-start-a-windows-desktop-application"></a>Windows 데스크톱 응용 프로그램을 시작하려면

1. 모든 C와 마찬가지로 응용 프로그램 및 c + + 응용 프로그램 해야는 `main` 모든 Windows 데스크톱 응용 프로그램을 시작 점으로 함수는 `WinMain` 함수입니다. `WinMain` 에는 다음 구문이 있습니다.

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   매개 변수 및 반환 값이 함수에 대 한 정보를 참조 하십시오. [WinMain 진입점](https://msdn.microsoft.com/library/windows/desktop/ms633559)합니다.

   > [!NOTE]
   > 와 같은 모든 여분의 단어, 사용 이란 **콜백**, 또는 **HINSTANCE**, 또는  **\_에\_**? 기존의 Windows API에서 typedef를 사용 하 고 전처리기 매크로 추상화를 광범위 하 게 형식 및 플랫폼 관련 세부 정보 중 일부 코딩, 호출 규칙을 같은 **__declspec** 선언과 pragma는 컴파일러입니다. Visual Studio에서 IntelliSense를 사용할 수 있습니다 [요약 정보](/visualstudio/ide/using-intellisense#quick-info) 이러한 typedefs 및 매크로 정의 기능을 표시할 기능을 합니다. 관심 있는 단어 마우스 포인터로 또는 선택한 ctrl-K, ctrl 키를 눌러-I는 정의 포함 하는 작은 팝업 창인 합니다. 자세한 내용은 [IntelliSense 사용](/visualstudio/ide/using-intellisense)을 참조하세요. 매개 변수 및 반환 형식을 자주 사용할 *SAL 주석을* 수 있도록 프로그래밍 오류가 catch 합니다. 자세한 내용은 참조 [줄일 C/c + + 코드 오류를 SAL 주석을 사용 하 여](/visualstudio/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects)합니다.

1. Windows 데스크톱 프로그램에서 필요한 &lt;. h >입니다. &lt;tchar.h > 정의 `TCHAR` 궁극적으로 확인 되는 매크로를 `wchar_t` 유니코드 기호가 프로젝트에 정의 된 경우 그렇지 않으면으로 확인 `char`합니다.  항상를 빌드하는 경우 사용 하도록 설정 하는 유니코드를 사용한 TCHAR 필요 하지 않은 하 고 수만 직접 wchar_t를 사용 합니다.

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. `WinMain` 함수 이외에 모든 Windows 데스크톱 응용 프로그램에는 창 프로시저 함수도 있어야 합니다. 이 함수 이름은 일반적으로 `WndProc` 바꾸는 이름 수 있습니다. `WndProc` 에는 다음 구문이 있습니다.

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hwnd,
      _In_ UINT   uMsg,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   이 함수에서 처리 하는 코드를 작성 *메시지* Windows에서 응용 프로그램을 수신 하는 경우 *이벤트* 발생 합니다. 예를 들어 응용 프로그램에서 확인 단추를 선택한 경우에 Windows에서 메시지를 보내고 내부에서 코드를 작성할 수 있습니다 프로그램 `WndProc` 적절 한 모든 작업을 수행 하는 함수입니다. 이 라고 *처리* 이벤트입니다. 응용 프로그램에 대 한 관련 된 이벤트를 처리 합니다.

   자세한 내용은 참조 [창 프로시저](https://msdn.microsoft.com/library/windows/desktop/ms632593)합니다.

### <a name="to-add-functionality-to-the-winmain-function"></a>WinMain 함수에 기능을 추가하려면

1. 에 `WinMain` 함수 형식의 구조를 채울 [WNDCLASSEX](https://msdn.microsoft.com/library/windows/desktop/ms633577)합니다. 이 구조는 예를 들어 응용 프로그램 아이콘, 창 프로시저에 대 한 함수 포인터 및 매우 중요 한 것은 제목 표시줄에 표시할 이름 창의 배경색 창에 대 한 정보를 포함 합니다. 다음 예제에서는 일반적인 `WNDCLASSEX` 구조를 보여 줍니다.

   ```cpp
   WNDCLASSEX wcex;

   wcex.cbSize         = sizeof(WNDCLASSEX);
   wcex.style          = CS_HREDRAW | CS_VREDRAW;
   wcex.lpfnWndProc    = WndProc;
   wcex.cbClsExtra     = 0;
   wcex.cbWndExtra     = 0;
   wcex.hInstance      = hInstance;
   wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
   wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
   wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
   wcex.lpszMenuName   = NULL;
   wcex.lpszClassName  = szWindowClass;
   wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);
   ```

   이 구조의 필드에 대 한 정보를 참조 하십시오. [WNDCLASSEX](https://msdn.microsoft.com/library/windows/desktop/ms633577)합니다.

1. 등록 해야 합니다는 `WNDCLASSEX` windows 한다는 창 및 메시지를 보내는 방법에 대 한 알 수 있도록 합니다. 사용 하 여는 [RegisterClassEx](https://msdn.microsoft.com/library/windows/desktop/ms633587) 작동 하 고 창 클래스 구조를 인수로 전달 합니다. `_T` 매크로 사용 하 여 사용 된 `TCHAR` 형식입니다.

   ```cpp
   if (!RegisterClassEx(&wcex))
   {
      MessageBox(NULL,
         _T("Call to RegisterClassEx failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

1. 이제 창을 만들 수 있습니다. 사용 하 여 [CreateWindow](https://msdn.microsoft.com/library/windows/desktop/ms632679) 함수입니다.

   ```cpp
   static TCHAR szWindowClass[] = _T("DesktopApp");
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   // The parameters to CreateWindow explained:
   // szWindowClass: the name of the application
   // szTitle: the text that appears in the title bar
   // WS_OVERLAPPEDWINDOW: the type of window to create
   // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
   // 500, 100: initial size (width, length)
   // NULL: the parent of this window
   // NULL: this application does not have a menu bar
   // hInstance: the first parameter from WinMain
   // NULL: not used in this application
   HWND hWnd = CreateWindow(
      szWindowClass,
      szTitle,
      WS_OVERLAPPEDWINDOW,
      CW_USEDEFAULT, CW_USEDEFAULT,
      500, 100,
      NULL,
      NULL,
      hInstance,
      NULL
   );
   if (!hWnd)
   {
      MessageBox(NULL,
         _T("Call to CreateWindow failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

   이 함수는 반환 된 `HWND`, 창에 대 한 핸들 인 합니다. 핸들은 열려 있는 창을 추적 하기 위해 Windows에서 사용 하는 포인터 라고 합니다. 자세한 내용은 참조 [Windows 데이터 형식](https://msdn.microsoft.com/library/windows/desktop/aa383751)합니다.

1. 이 시점에서 창, 만들어졌지만 Windows에서 표시 되도록 할 작업을 계속 합니다. 즉,이 코드에서 수행 하는 작업:

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   표시 된 창 아직 구현 되지 때문에 많은 내용을 포함 하지 않습니다는 `WndProc` 함수입니다. 즉, 응용 프로그램을 Windows에 보내는 이제 메시지를 아직 처리 하지 않는 합니다.

1. 메시지를 처리 하려면 먼저 Windows에서 전송 하는 메시지를 수신 하는 메시지 루프를 추가 합니다. 응용 프로그램이 메시지를 받으면이 루프가를 디스패치합니다 프로그램 `WndProc` 함수를 처리 합니다. 메시지 루프는 다음 코드와 유사합니다.

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   구조 및 메시지 루프의 함수에 대 한 자세한 내용은 참조 [MSG](https://msdn.microsoft.com/library/windows/desktop/ms644958), [GetMessage](https://msdn.microsoft.com/library/windows/desktop/ms644936), [TranslateMessage](https://msdn.microsoft.com/library/windows/desktop/ms644955), 및 [DispatchMessage ](https://msdn.microsoft.com/library/windows/desktop/ms644934).

   이때 `WinMain` 함수는 다음 코드와 유사합니다.

   ```cpp
   int WINAPI WinMain(HINSTANCE hInstance,
                      HINSTANCE hPrevInstance,
                      LPSTR lpCmdLine,
                      int nCmdShow)
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application dows not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }
   ```

### <a name="to-add-functionality-to-the-wndproc-function"></a>WndProc 함수에 기능을 추가하려면

1. `WndProc` 함수에서 응용 프로그램이 받는 메시지를 처리하게 하려면 switch 문을 구현합니다.

   한 중요 한 메시지를 처리 하는 [WM_PAINT](https://msdn.microsoft.com/library/windows/desktop/dd145213) 메시지입니다. 응용 프로그램은 표시된 창 일부를 업데이트해야 할 때 이 메시지를 받습니다. 이 이벤트는 사용자가 창을 이동 하 여 창 앞에 다음 이동 번 다시 발생할 수 있습니다. 응용 프로그램이이 같은 이벤트가 발생할 때; 모릅니다. 창만 알고 있는 알리는 하므로 `WM_PAINT`합니다. 창이 처음 표시 된 해당 내용을 모두 업데이트 되어야 합니다.

   처리 하는 `WM_PAINT` 메시지, 첫 번째 호출 [BeginPaint](https://msdn.microsoft.com/library/windows/desktop/dd183362), 텍스트, 단추 및 창에서 다른 컨트롤의 레이아웃에 모든 논리를 처리 하 고 호출 [EndPaint](https://msdn.microsoft.com/library/windows/desktop/dd162598)합니다. 이 응용 프로그램에 대 한 시작 호출과 종료 호출 간의 논리 문자열 "Hello, Windows 바탕 화면!"을 표시 하는 것입니다. 다음 코드를 알 수 있듯이 [TextOut](https://msdn.microsoft.com/library/windows/desktop/dd145133) 함수를 사용 하는 문자열을 표시 합니다.

   ```cpp
   PAINTSTRUCT ps;
   HDC hdc;
   TCHAR greeting[] = _T("Hello, Windows desktop!");

   switch (message)
   {
   case WM_PAINT:
      hdc = BeginPaint(hWnd, &ps);

      // Here your application is laid out.
      // For this introduction, we just print out "Hello, Windows desktop!"
      // in the top left corner.
      TextOut(hdc,
         5, 5,
         greeting, _tcslen(greeting));
      // End application-specific layout section.

      EndPaint(hWnd, &ps);
      break;
   }
   ```

   `HDC`이 코드는 장치 컨텍스트에 그래픽 하위 시스템과 통신 하는 응용 프로그램을 사용 하도록 설정 하려면 Windows에서 사용 하는 데이터 구조에 대 한 핸들입니다. `BeginPaint` 및 `EndPaint` 함수 확인 응용 프로그램이 수행 하 게 작동 하 고 필요한 것 보다 더 이상에 대 한 장치 컨텍스트를 사용 하지 않습니다. 이렇게 하면 그래픽 하위 시스템은 다른 응용 프로그램에서 사용할 수 있습니다.

1. 응용 프로그램 일반적으로 많은 기타 메시지 처리, 예를 들어 [WM_CREATE](https://msdn.microsoft.com/library/windows/desktop/ms632619) 창이 처음 만들어질 때 및 [WM_DESTROY](https://msdn.microsoft.com/library/windows/desktop/ms632620) 은 창이 닫힐 때. 다음 코드에서는 기본적인 전체 `WndProc` 함수를 보여 줍니다.

   ```cpp
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

## <a name="build-the-code"></a>코드 작성

보낼 작업 응용 프로그램에 대 한 전체 코드는 다음과 같습니다.

### <a name="to-build-this-example"></a>이 예제를 빌드하려면

1. HelloWindowsDesktop.cpp에을 입력 하면 편집기에서 코드를 삭제 합니다. 이 예제 코드를 복사한 HelloWindowsDesktop.cpp에 붙여 넣습니다.

   ```cpp
   // HelloWindowsDesktop.cpp
   // compile with: /D_UNICODE /DUNICODE /DWIN32 /D_WINDOWS /c

   #include <windows.h>
   #include <stdlib.h>
   #include <string.h>
   #include <tchar.h>

   // Global variables

   // The main window class name.
   static TCHAR szWindowClass[] = _T("DesktopApp");

   // The string that appears in the application's title bar.
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   HINSTANCE hInst;

   // Forward declarations of functions included in this code module:
   LRESULT CALLBACK WndProc(HWND, UINT, WPARAM, LPARAM);

   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   )
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application does not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }

   //  FUNCTION: WndProc(HWND, UINT, WPARAM, LPARAM)
   //
   //  PURPOSE:  Processes messages for the main window.
   //
   //  WM_PAINT    - Paint the main window
   //  WM_DESTROY  - post a quit message and return
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application-specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

1. **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다. 컴파일 결과에 표시 됩니다는 **출력** Visual Studio의 창.

   ![DesktopApp 프로젝트 빌드](../build/media/desktop-app-project-build-150.gif "DesktopApp 프로젝트 빌드")

1. 키를 눌러 응용 프로그램을 실행 하려면 **F5**합니다. "Hello, Windows 바탕 화면!" 텍스트가 있는 창 디스플레이의 왼쪽 위에 표시됩니다.

   ![DesktopApp 프로젝트 실행](../build/media/desktop-app-project-run-150.gif "DesktopApp 프로젝트 실행")

지금까지 이 연습을 완성 하 고 기존 Windows 데스크톱 응용 프로그램을 작성 합니다.

## <a name="see-also"></a>참고 항목

[Windows 데스크톱 응용 프로그램](../windows/windows-desktop-applications-cpp.md)
