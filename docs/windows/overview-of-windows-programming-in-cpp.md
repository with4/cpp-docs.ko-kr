---
title: "C + +의 Windows 프로그래밍 개요 | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b204783e3b2c418e5e719ca5c6efcf9c2d31c6df
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2018
---
# <a name="overview-of-windows-programming-in-c"></a>C++의 Windows 프로그래밍 개요

Visual C++을 사용하여 Windows 서버, 클라우드, Xbox, Windows PC(x86, x64 또는 ARM)에서 실행되는 다양한 프로그램을 작성할 수 있습니다. 잘 작성된 C++ 프로그램은 빠르고 효율적이고 전력 소비량 면에서 경제적이고 다중 코어 및 다중 코어 장치, GPGPU(그래픽 처리 장치)에서의 일반적인 컴퓨팅 및 기타 최근 하드웨어 발전을 최대한 활용할 수 있습니다.

Visual C++를 사용하여 광범위한 범주의 다양한 Windows 앱을 구현할 수 있습니다. 이들 범주에는 서로 다른 프로그래밍 모델 또는 앱 모델이 있고, 이는 플랫폼에 대한 액세스를 제공하고 사용자 인터페이스를 제공하는 서로 다른 라이브러리 및 API가 모델에 사용됨을 의미합니다.

- [Windows 유니버설 앱](#BK_WindowsUniversal). Windows 앱의 세 번째 범주는 Windows 8에 처음 추가되었고 이 앱 범주는 Windows 10에서 계속 지원됩니다. 이 앱을 "Windows 앱"이라고도 하며 다양한 장치를 대상으로 하는 데스크톱 및 모바일 앱을 포함합니다. C++/CX, Windows 런타임 개발 지원이 포함된 C++ 언어 또는 WRL(Windows 런타임 라이브러리)을 사용하는 COM을 통한 표준 C++로 이러한 앱을 작성할 수 있습니다. 이들 앱은 원래 전체 화면으로 실행되도록 디자인되었으나 Windows 10 사용자는 데스크톱 창에서 이들 앱을 실행할 수 있습니다. 이들 앱은 터치를 지향하지만 사용자가 원하거나 터치 화면이 없으면 마우스로 쉽게 작동할 수 있습니다. Microsoft 스토어에 앱 "Store" 라는 되 고 앱에서 이러한 응용 프로그램 배포 됩니다.

- [데스크톱, 서버 및 클라우드 응용 프로그램 및 게임](#BK_Native). 이 범주에는 Win32 API가 사용되어 Win32 응용 프로그램이라고도 하는 Windows 데스크톱 응용 프로그램이 포함됩니다. Windows 8 이전에는 모든 Windows 응용 프로그램이 이 범주에 속했습니다. 이 범주의 응용 프로그램에서는 보통 COM 개체인 Windows 구성 요소와 상호 작용할 사용자 인터페이스 및 ATL에 대해 MFC를 사용할 수 있습니다.

   표준 C++로 작성된 응용 프로그램, 구성 요소 또는 라이브러리도 이 범주에 맞춰집니다.

   이 범주에는 서버 및 클라우드 프로그래밍의 컨텍스트에서 핵심 구성 요소 및 계산 코드에 C++를 사용하는 경우도 포함됩니다. 경우에 따라 서버 또는 클라우드 응용 프로그램의 핵심 부분에서 성능 집중적인 코드를 C++로 작성하여 성능을 최대화합니다. 해당 코드를 DLL로 컴파일하고 C# 또는 Visual Basic에서 이 코드를 사용할 수 있습니다.

- **.NET Framework 응용 프로그램**. 대부분 .NET Framework 응용 프로그램은 C# 또는 Visual Basic으로 작성되지만 C++/CLI(Visual C++의 /clr 컴파일러 옵션)로 작성할 수도 있습니다. 관리되는 코드와 네이티브 코드를 포함하는 더 큰 응용 프로그램에서는 최소한 interop 레이어에 대해 C++/CLI를 사용하는 것이 좋습니다.

##  <a name="BK_WindowsUniversal"></a> Windows Universal Apps

Windows 10에서는 태블릿, 휴대폰 및 데스크톱과 같은 모든 Windows 10 장치에서 앱을 실행할 수 있습니다. 데스크톱에서는 항상 전체 화면으로 실행되지 않고 데스크톱 창으로 실행될 수 있습니다. 이러한 앱은 Xbox 및 앞으로 제공될 장치에서도 실행될 수 있습니다.  두 앱 형식에 대한 프로그래밍 모델은 Win32 데스크톱 응용 프로그램과 다릅니다. 이러한 Windows 앱은 사용자 인터페이스 요소, 이들 앱에 대한 필수 서비스 및 지원되는 다양한 하드웨어 장치에 대한 인터페이스를 제공하는 Windows 런타임에서 실행됩니다. 이들 앱은 네이티브 코드로 컴파일되고 XAML 사용자 인터페이스가 있거나 DirectX를 사용합니다. 다른 Windows 앱에서 사용할 수 있는 네이티브 코드에서 Windows 런타임 구성 요소를 작성할 수도 있습니다-C#, Visual Basic 또는 JavaScript로 작성 된 앱입니다. 자세한 내용은 참조 [c + + UWP "Hello world" 앱을 만들](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp), [DirectX로 간단한 UWP 게임을 만들](/windows/uwp/gaming/tutorial--create-your-first-uwp-directx-game), 및 [+로 만드는 Windows 런타임 구성 요소](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)합니다.

> [!TIP]
> Windows 10 용 Microsoft 스토어를 통해 배포에 대 한 기존 데스크톱 응용 프로그램을 패키지 하는 데스크톱 앱 변환기를 사용할 수 있습니다. 자세한 내용은 [Using Visual C++ Runtime in Centennial project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project)(Centennial 프로젝트에서 Visual C++ 런타임 사용) 및 [데스크톱 브리지를 사용하여 데스크톱 앱을 UWP(유니버설 Windows 플랫폼)로 가져오기](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root)를 참조하세요.

유니버설 Windows 플랫폼 샘플에 대한 자세한 내용은 [GitHub의 Windows 유니버설 샘플](https://github.com/Microsoft/Windows-universal-samples)을 참조하세요.

기존 프로젝트를 Windows 8.1 및 Windows 10으로 포팅 있으면 참조 [유니버설 Windows 플랫폼으로 포팅](../porting/porting-to-the-universal-windows-platform-cpp.md)합니다. UWP 앱에 통합, 참조 하려는 기존 클래식 Win32 데스크톱 라이브러리 및 코드가 있는 경우 [하는 방법: 유니버설 Windows 플랫폼 앱에서 사용 하 여 기존 c + + 코드](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md)합니다.

또한 없이 작성할 수 있습니다 유니버설 Windows 앱, 게임 및 구성 요소를 사용 하 여 C + + /cli CX; 대신, Windows 런타임 c + + 템플릿 라이브러리 (Windows 런타임 c + + 템플릿 라이브러리)을 사용할 수 있습니다. 자세한 내용은 참조 [Windows 런타임 c + + 템플릿 라이브러리 (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)합니다.

[!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서는 Windows 10 데스크톱 및 모바일 장치에서 실행되는 유니버설 Windows 앱을 개발할 수 있습니다. [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]에서 Windows 8.1 앱과 Windows Phone 8.1 앱을 개발할 수도 있지만, 이렇게 하려면 먼저 같은 컴퓨터에서 Visual Studio 2013을 설치하고 **Visual Studio 2013 (v120)** 도구 집합을 사용하도록 프로젝트를 구성해야 합니다. 프로젝트에서 이 설정을 구성하려면 프로젝트 속성을 열고 **일반** 섹션에서 **플랫폼 도구 집합** 을 **Visual Studio 2013(v120)**으로 설정합니다.

Visual Studio 설치 프로그램에서 Phone 8.0 도구를 설치하면 Windows Phone 8.0을 대상으로 지정할 수도 있습니다.

Windows 10에 도입된 API 계약이라는 새로운 개념은 특정 Windows 버전을 대상으로 지정하는 이전 사례를 대체합니다. 대신에 앱에 필요한 API 계약을 선택할 수 있고 이 앱은 해당 계약을 지원하는 Windows 장치에서 실행됩니다. API 계약은 플랫폼 또는 장치 리소스에 대한 액세스를 제공하는 안정적인 API 집합입니다. API 계약은 프로젝트 시스템에 참조로 포함될 수 있습니다. Visual Studio 프로젝트에서 특정 확장명 SDK에 대한 참조를 추가하면 Visual Studio에서 해당하는 API 계약이 추가됩니다.

이러한 모든 개념에 대 한 자세한 내용은 참조 하십시오. [Windows 유니버설 앱 가이드](http://go.microsoft.com/fwlink/p/?linkid=534605)합니다.

##  <a name="BK_Native"></a> 데스크톱, 서버 및 클라우드 응용 프로그램 및 게임

클라우드에서는 C++에서 Azure 네이티브 코드 어셈블리를 작성하고 C#에서 만든 웹 역할에서 호출할 수 있습니다. 자세한 내용은 [Azure SDK](http://go.microsoft.com/fwlink/p/?LinkId=256416)를 참조하세요.

데스크톱용 Windows 클라이언트 응용 프로그램 작성의 기본 사항을 알아보려면 [C++에서 Windows 응용 프로그램 개발](http://msdn.microsoft.com/vstudio//hh304489) 및 [C++에서 Windows 프로그래밍 소개](http://msdn.microsoft.com/library/windows/desktop/ff381398\(v=vs.85\).aspx)를 참조하세요.

Windows 10에서는 Visual C++를 사용하여 다양한 프로그램을 만들 수 있습니다.

- 명령줄 응용 프로그램 및 유틸리티 자세한 내용은 참조 [콘솔 응용 프로그램](../windows/console-applications-in-visual-cpp.md)합니다.

- PC 또는 Xbox에서 실행되는 DirectX 게임 자세한 내용은 [DirectX 개발자 센터](http://go.microsoft.com/fwlink/p/?LinkId=256418)를 참조하세요.

- 정교한 그래픽 사용자 인터페이스의 소비자 응용 프로그램 자세한 내용은 [Hilo: Windows용 C++ 응용 프로그램 개발](http://go.microsoft.com/fwlink/p/?LinkId=256417)을 참조하세요.

- .NET Framework에서 실행되거나 .NET Framework 응용 프로그램과 네이티브 코드에서 작성되는 응용 프로그램 또는 구성 요소를 연결하는 엔터프라이즈 및 LOB(line-of-business) 응용 프로그램 자세한 내용은 참조 [.NET 프로그래밍 C + + /cli CLI (Visual c + +)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)합니다.

- 네이티브 코드에서 실행되는 SQL 데이터베이스 클라이언트 자세한 내용은 [SQL Server Native Client](http://go.microsoft.com/fwlink/p/?LinkId=256419)를 참조하세요.

- Microsoft Office 응용 프로그램의 추가 기능 자세한 내용은 [Outlook 2010의 C++ 추가 기능 빌드](http://go.microsoft.com/fwlink/p/?LinkId=256420)를 참조하세요.

- 장치 드라이버 자세한 내용은 [WDK(Windows 드라이버 키트)](http://go.microsoft.com/fwlink/p/?LinkId=256421)를 참조하세요.

- Windows 서비스. 자세한 내용은 [Introduction to Windows Service Applications](/dotnet/framework/windows-services/introduction-to-windows-service-applications)을 참조하세요.

Visual C++를 사용하여 C++ 응용 프로그램이나 C# 또는 Visual Basic과 같은 다른 언어로 작성된 앱이 소비할 수 있는 Win32 DLL 또는 COM DLL에서 거의 모든 종류의 사용자 지정 고성능 기능을 패키지할 수 있습니다. WIn32 DLL에 대한 자세한 내용은 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)를 참조하세요. COM 개발에 대 한 자세한 내용은 참조 [구성 요소 개체 모델 (COM)](https://msdn.microsoft.com/library/windows/desktop/ms680573)합니다.

## <a name="sdks-and-header-files"></a>SDK 및 헤더 파일

Visual c + + C 런타임 라이브러리 (CRT), c + + 표준 라이브러리 및 다른 Microsoft 전용 라이브러리를 포함 합니다. 이러한 라이브러리에 대 한 헤더 파일이 포함 된 폴더 포함 폴더는 \VC\ 폴더 아래 또는 CRT, Windows SDK 설치 폴더에서 프로그램 파일의 예를 들어 Windows Kits\10의 경우 Visual Studio 설치 디렉터리 Windows 10 SDK에 대 한 폴더입니다.  Microsoft 라이브러리는 다음과 같습니다.

- MFC(Microsoft Foundation Class): 단추, 목록 상자, 트리 뷰 및 기타 컨트롤이 있는 다양한 기능의 사용자 인터페이스가 있는 일반적인 Windows 프로그램, 특히 엔터프라이즈 응용 프로그램을 만들기 위한 개체 지향 프레임워크입니다. 자세한 내용은 [MFC Desktop Applications](../mfc/mfc-desktop-applications.md)을 참조하세요.

- ATL(Active Template Library): COM 구성 요소를 만들기 위한 강력한 도우미 라이브러리입니다. 자세한 내용은 [ATL COM Desktop Components](../atl/atl-com-desktop-components.md)을 참조하세요.

- C++ AMP(C++ Accelerated Massive Parallelism): GPU에서 고성능 일반 계산 작업에 사용할 수 있는 라이브러리입니다. 자세한 내용은 [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)을 참조하세요.

- 동시성 런타임: 다중 코어 및 다중 코어 장치에 대한 병렬 및 비동기 프로그래밍 작업을 간소화하는 라이브러리입니다. 자세한 내용은 [Concurrency Runtime](../parallel/concrt/concurrency-runtime.md)을 참조하세요.

많은 Windows 프로그래밍 시나리오에는 Windows 운영 체제 구성 요소에 액세스할 수 있는 헤더 파일을 포함하는 Windows SDK도 필요합니다. 기본적으로 Visual Studio의 유니버설 Windows 앱 개발을 수행할 수는 Windows SDK를 설치 합니다. Windows 10용 유니버설 Windows 앱을 개발하려면 Windows SDK의 Windows 10 버전이 필요합니다. Windows 10 SDK에 대 한 정보를 참조 하십시오. [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk)합니다. (이전 버전의 Windows 용 Windows Sdk에 대 한 자세한 내용은 참조는 [Windows SDK 아카이브](https://developer.microsoft.com/windows/downloads/sdk-archive)).

Xbox, Azure 등 다른 플랫폼은 설치가 필요한 고유의 SDK가 있습니다. 자세한 내용은 DirectX 개발자 센터 및 Azure 개발자 센터를 참조하세요.

## <a name="development-tools"></a>개발 도구

Visual Studio는 네이티브 코드에 대한 강력한 디버거, 정적 분석 도구, 그래픽 디버깅 도구, 완벽한 기능을 갖춘 코드 편집기, 유닛 테스트 지원 및 다른 많은 도구와 유틸리티를 포함합니다. 자세한 내용은 참조 [Visual Studio와 함께 개발을 시작 하려면](/visualstudio/ide/get-started-developing-with-visual-studio), 및 [IDE 및 개발 도구](../ide/ide-and-tools-for-visual-cpp-development.md)합니다.

## <a name="related-articles"></a>관련 문서

|제목|설명|
|-----------|-----------------|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual c + + 개발자 콘텐츠에 대 한 부모 항목입니다.|