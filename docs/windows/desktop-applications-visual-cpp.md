---
title: 데스크톱 응용 프로그램 (Visual c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
caps.latest.revision: 17
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 61f52dead8ca7ecad52b1cef4f1d87ffc5830386
ms.sourcegitcommit: 78e5e5cdbafd29e2a6ccf68d4cce215136952907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2018
---
# <a name="desktop-applications-visual-c"></a>데스크톱 응용 프로그램 (Visual c + +)
A *데스크톱 응용 프로그램* c + + Windows Api 집합과 나 시스템 콘솔 창에서 실행 되거나 전체 집합에 액세스할 수 있는 네이티브 응용 프로그램입니다. Windows XP부터 Windows 10 (Windows XP은 더 이상 공식적으로 지원 되며 그 이후 도입 된 많은 Windows Api) 하지만 c + +에서 데스크톱 응용 프로그램 실행할 수 없습니다.   데스크톱 응용 프로그램은 Windows 10을 실행 하는 Pc에 및 XBox, Windows Phone, Surface Hub 및 기타 장치에서 실행할 수 있는 한 유니버설 Windows 플랫폼 (UWP) 앱과에서 다릅니다. 데스크톱 vs에 대 한 자세한 내용은 합니다. UWP 응용 프로그램 참조 [기술 선택](https://msdn.microsoft.com/en-us/library/windows/desktop/dn614993\(v=vs.85\).aspx)합니다.  
  
 **Terminology**  
  
-   A *Win32* 응용 프로그램은 네이티브 데스크톱 응용 프로그램에서 만들 수 있는 c + +를 사용 하는 Windows [Windows C Api 및/또는 COM Api](https://msdn.microsoft.com/en-us/library/windows/desktop/ff818516\(v=vs.85\).aspx) CRT 및 표준 라이브러리 Api 및 타사 라이브러리입니다. 창에서를 실행 하는 Win32 응용 프로그램 개발자가 Windows 프로시저 함수 내 Windows 메시지를 명시적으로 작업할 수 필요 합니다. 이름이 32 비트 (x86) 또는 64 비트 (x64) 이진으로 Win32 응용 프로그램을 컴파일할 수 있습니다. Visual Studio IDE에서 x86 용어 및 Win32는 동의어입니다.  
  
-   [구성 요소 개체 모델 (COM)](https://msdn.microsoft.com/en-us/library/windows/desktop/ms694363\(v=vs.85\).aspx) 서로 통신할 수 있는 서로 다른 언어로 작성 된 프로그램을 수 있는 사양입니다. 많은 Windows 구성 요소를 COM 개체로 구현 및 개체 만들기에 대 한 표준 COM 규칙에 따라 검색 및 개체 소멸을 인터페이스입니다.  C + + 데스크톱 응용 프로그램의 COM 개체를 사용 하는 것은 비교적 간단 하지만 고유한 COM 개체를 작성 합니다. 더 높은 수준의 합니다. [라이브러리 ATL (액티브 템플릿)](../atl/atl-com-desktop-components.md) 매크로 및 COM 개발을 간소화 하는 도우미 함수를 제공 합니다.  
  
-   MFC 응용 프로그램은 사용 하는 Windows 데스크톱 응용 프로그램의 [Microsoft Foundation Classes](../mfc/mfc-desktop-applications.md) 사용자 인터페이스를 만들 수 있습니다. MFC 응용 프로그램 COM 구성 요소 뿐만 아니라 CRT 및 표준 라이브러리 Api 사용할 수도 있습니다. MFC는 창 메시지 루프 및 Windows Api를 통해 씬 c + + 개체 지향 래퍼를 제공합니다. MFC는 응용 프로그램에 대 한 기본 선택-특히 엔터프라이즈 형 응용 프로그램-많은 사용자 인터페이스 컨트롤이 나 사용자 지정 컨트롤을 포함 하는 합니다. MFC 창 관리, 직렬화, 텍스트 조작, 인쇄 및 리본과 같은 최신 사용자 인터페이스 요소에 대 한 편리한 도우미 클래스를 제공합니다. MFC와 함께 적용 하려면 Win32에 잘 알고 있어야 합니다.  
  
-   C + + /CLI 응용 프로그램 또는 구성 요소를 사용 하 여 c + + 구문에 대 한 확장 (c + + 사양에서 허용 됨) 처럼 간의 상호 작용.NET 및 네이티브 C + + 코드를 사용 하도록 설정 합니다.  C + + /CLI 응용 프로그램은 기본적으로 실행 하는 파트 및.NET 기본 클래스 라이브러리에 액세스할 수 있는.NET Framework에서 실행 되는 부분 있을 수 있습니다. C + + /cli CLI C# 또는 Visual Basic로 작성 된 코드를 사용 하는 네이티브 c + + 코드를 있는 경우 기본 옵션입니다. 사용자 인터페이스 코드 아닌.NET Dll에서 사용 하기 위해 주로 됩니다. 자세한 내용은 참조 [.NET 프로그래밍 C + + /cli CLI (Visual c + +)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)합니다.  
  
 CRT (C 런타임) 및 표준 라이브러리 클래스 및 함수, COM 개체 및 공용 Windows 함수 라고 통칭 Windows API 모든 데스크톱 응용 프로그램 c + +에서 사용할 수 있습니다. C++의 Windows 데스크톱 응용 프로그램에 대한 소개는 [C++의 Windows용 프로그램 알아보기](http://go.microsoft.com/fwlink/p/?LinkId=262281)(영문)를 참조하세요.  
  
## <a name="in-this-section"></a>단원 내용  
  
|제목|설명|  
|-----------|-----------------|  
|[콘솔 응용 프로그램](../windows/console-applications-in-visual-cpp.md)|콘솔 앱에 대한 정보가 들어 있습니다. Win32 또는 Win64 콘솔 응용 프로그램에는 고유의 창이나 메시지 루프가 없습니다. 콘솔 창에서 실행되고 입력 및 출력이 명령줄을 통해 처리됩니다.|  
|[Windows 데스크톱 응용 프로그램](../windows/windows-desktop-applications-cpp.md)|콘솔 아닌 windows에서 실행 되는 데스크톱 응용 프로그램을 만드는 방법.|  
|[DirectX (c + +)를 사용 하 여 게임을 만들기 위한 리소스](../windows/resources-for-creating-a-game-using-directx.md)|C + +에서 게임을 만들기에 대 한 콘텐츠 연결 되어 있습니다.|  
|[연습: 만들기 및 정적 라이브러리 사용](../windows/walkthrough-creating-and-using-a-static-library-cpp.md)|.Lib 이진 파일을 만드는 방법입니다.|  
|[방법: Windows 데스크톱 응용 프로그램에서 Windows 10 SDK 사용](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK를 사용하여 빌드할 프로젝트를 설정하는 단계를 설명합니다.|  
  
## <a name="related-articles"></a>관련 문서  
  
|제목|설명|  
|-----------|-----------------|  
|[Windows Development](http://go.microsoft.com/fwlink/p/?LinkId=262282)|Windows API 및 COM에 대한 정보를 제공합니다. 일부 Windows API 및 타사 DLL이 COM 개체로 구현됩니다.|  
|[Hilo: Developing C++ Applications for Windows 7](http://go.microsoft.com/fwlink/p/?LinkId=262284)|Windows Animation 및 Direct2D를 사용하는 리치 클라이언트 Windows 데스크톱 응용 프로그램을 만들어서 캐러셀 기반 사용자 인터페이스를 만드는 방법에 대해 설명합니다.  이 자습서에서는 Windows 7 이후 업데이트 되지 않은 있지만 여전히 Win32 프로그래밍에 대 한 철저 한 소개를 제공 합니다.|  
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual Studio에 포함된 Visual C++의 주요 기능을 설명하고 Visual C++ 설명서의 나머지 부분에 연결합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++](../visual-cpp-in-visual-studio.md)
