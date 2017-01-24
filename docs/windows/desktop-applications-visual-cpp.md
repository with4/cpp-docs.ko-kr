---
title: "Windows 데스크톱 응용 프로그램(Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
caps.latest.revision: 17
caps.handback.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Windows 데스크톱 응용 프로그램(Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

창 기반 사용자 인터페이스가 있고 Windows 데스크톱의 Windows XP부터 Windows 10까지의 Windows 버전에서 실행될 수 있는 네이티브 데스크톱 응용 프로그램을 만들려는 경우 Windows 데스크톱 응용 프로그램을 만들 수 있습니다.  
  
 *Windows 데스크톱 응용 프로그램*\(이전에는 Win32 응용 프로그램이라고도 함\)은 MFC\(Microsoft Foundation Class\), ATL\(Active Template Library\) 또는 .NET Framework 등의 프레임워크를 사용하는 대신에 메시지 루프를 사용하여 Windows 메시지를 직접 처리하는 응용 프로그램을 의미하는 일반적인 용어입니다. C\+\+의 Windows 데스크톱 응용 프로그램은 CRT\(C 런타임\)와 STL\(표준 템플릿 라이브러리\) 클래스 및 함수, COM 개체 및 공용 Windows 함수를 사용할 수 있으며, 이들을 Windows API라고 통칭합니다. C\+\+의 Windows 데스크톱 응용 프로그램에 대한 소개는 [C\+\+의 Windows용 프로그램 알아보기](http://go.microsoft.com/fwlink/p/?LinkId=262281)\(영문\)를 참조하세요.  
  
 Windows 데스크톱 응용 프로그램은 Windows용 네이티브 데스크톱 응용 프로그램을 만드는 한 가지 방법이며, 다른 방법으로 MFC 응용 프로그램이 있습니다. MFC는 많은 사용자 인터페이스 컨트롤이나 사용자 지정 사용자 정의 컨트롤을 포함하는 응용 프로그램\(특히 엔터프라이즈형 응용 프로그램\)에 기본적으로 사용됩니다. MFC는 리본과 같은 최신 사용자 인터페이스 요소, 인쇄, 텍스트 조작 및 serialization을 위한 편리한 도우미 클래스를 제공합니다. 이러한 클래스는 Windows 데스크톱 응용 프로그램에 사용할 수 없습니다.  
  
## 관련 문서  
  
|제목|설명|  
|--------|--------|  
|[Windows Development](http://go.microsoft.com/fwlink/p/?LinkId=262282)|Windows API 및 COM에 대한 정보를 제공합니다. 일부 Windows API 및 타사 DLL이 COM 개체로 구현됩니다.|  
|[Hilo: Developing C\+\+ Applications for Windows 7](http://go.microsoft.com/fwlink/p/?LinkId=262284)|Windows Animation 및 Direct2D를 사용하는 리치 클라이언트 Windows 데스크톱 응용 프로그램을 만들어서 캐러셀 기반 사용자 인터페이스를 만드는 방법에 대해 설명합니다.|  
|[콘솔 응용 프로그램](../windows/console-applications-in-visual-cpp.md)|콘솔 앱에 대한 정보가 들어 있습니다. Win32 또는 Win64 콘솔 응용 프로그램에는 고유의 창이나 메시지 루프가 없습니다. 콘솔 창에서 실행되고 입력 및 출력이 명령줄을 통해 처리됩니다.|  
|[Visual C\+\+](../top/visual-cpp-in-visual-studio-2015.md)|Visual Studio에 포함된 Visual C\+\+의 주요 기능을 설명하고 Visual C\+\+ 설명서의 나머지 부분에 연결합니다.|  
|MSDN 웹 사이트의 [Visual C\+\+ 개발자 센터](http://go.microsoft.com/fwlink/p/?LinkId=252885)|Windows 데스크톱 응용 프로그램과 관련된 자습서, 블로그 게시물 및 문서가 포함되어 있습니다.|  
|[방법: Windows 데스크톱 응용 프로그램에서 Windows 10 SDK 사용](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK를 사용하여 빌드할 프로젝트를 설정하는 단계를 설명합니다.|