---
title: "IDE 및 Visual C++ 개발 도구 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Visual C++, 개발 도구"
ms.assetid: 56eabafb-1956-4f0f-bec5-29b887763559
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDE 및 Visual C++ 개발 도구
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C++는 Visual Studio IDE(통합 개발 환경)의 일부로서 다른 언어와 공통된 다양한 창과 도구를 공유합니다. **솔루션 탐색기**, 코드 편집기, 디버거를 비롯한 이러한 창과 도구에 대해서는 MSDN 라이브러리의 [Visual Studio IDE](../Topic/Visual%20Studio%20IDE.md)에서 설명합니다. 공유 도구 또는 창에 있는 C++용 기능 집합과 .NET 언어 또는 Javascript용 기능 집합이 약간 다른 경우가 자주 있습니다. 일부 창이나 도구는 Visual Studio Pro 또는 Visual Studio Enterprise에서만 사용할 수 있습니다. 이 항목에서는 Visual C++의 관점에서 Visual Studio IDE를 소개하고 Visual C++와 관련된 다른 항목에 대한 링크를 제공합니다.  
  
 Visual Studio IDE에 있는 공유 도구 외에도, Visual C++에는 네이티브 코드 개발 전용으로 사용되는 여러 도구가 있습니다. 이러한 도구의 목록도 이 문서에서 제공합니다. Visual Studio의 각 버전에서 사용할 수 있는 도구 목록은 [Visual C++ Tools and Templates in Visual Studio Editions](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md)을 참조하세요.  
  
## <a name="creating-a-solution-and-projects"></a>솔루션 및 프로젝트 만들기  
 모든 버전의 Visual C++에서 .exe, .dll 또는 .lib와 같은 실행 파일에 대한 소스 코드 및 관련 파일을 프로젝트에 구성합니다. 프로젝트에는 프로그램을 컴파일하는 데 필요한 모든 파일 및 리소스를 지정하는 XML 형식의 프로젝트 파일(.vcxproj)뿐만 아니라 대상 플랫폼(x86, x64 또는 ARM)과 같은 구성 설정 및 프로그램의 릴리스 버전 또는 디버그 버전을 빌드하는지 여부와 같은 다른 구성 설정이 포함됩니다. 한 프로젝트(또는 여러 프로젝트)가 *솔루션*에 포함됩니다. 예를 들어 솔루션에는 몇 개의 Win32 DLL 프로젝트 및 이러한 DLL을 사용하는 단일 Win32 콘솔 응용 프로그램이 포함될 수 있습니다. 프로젝트를 빌드하면 MSBuild 엔진에서 프로젝트 파일을 사용하고 실행 파일 및/또는 다른 모든 사용자 지정 출력을 생성합니다.  
  
 **프로젝트 템플릿**  
  
 Visual C++에는 다양한 기본 프로그램 형식에 필요한 시작 코드와 설정이 포함되어 있는 몇 개의 프로젝트 템플릿이 함께 제공됩니다. 선택 하 여 시작 하는 일반적으로 **파일 및 #124; 새 프로젝트** 프로젝트 템플릿에서 프로젝트를 만들려면 다음 해당 프로젝트에 새 소스 코드 파일을 추가 하거나 제공 된 파일이 코딩을 시작 합니다. C++ 프로젝트 및 프로젝트 마법사에 대한 자세한 내용은 [Creating and Managing Visual C++ Projects](../ide/creating-and-managing-visual-cpp-projects.md)를 참조하세요.  
  
 **응용 프로그램 마법사**  
  
 Visual C++에서는 일부 프로젝트 형식에 대해 마법사를 제공합니다. 마법사는 새 프로젝트를 만드는 과정을 단계별로 안내합니다. 이러한 마법사는 옵션 및 설정이 많은 프로젝트 형식에 유용합니다. 자세한 내용은 [Creating Desktop Projects By Using Application Wizards](../ide/creating-desktop-projects-by-using-application-wizards.md)을 참조하세요.  
  
## <a name="creating-user-interfaces-with-designers"></a>디자이너를 사용하여 사용자 인터페이스 만들기  
 프로그램에 사용자 인터페이스가 있는 경우 처음으로 수행할 작업 중 하나로 사용자 인터페이스를 단추, 목록 상자 등의 컨트롤로 채웁니다. Visual Studio에는 시각적 디자인 화면과 각 C++ 응용 프로그램의 특성에 맞는 도구 상자가 있습니다. 어떤 앱 유형을 만들든 간에 관계없이 기본적인 개념은 같습니다. 즉, 도구 상자 창에서 컨트롤을 끌어 디자인 화면의 원하는 위치에 놓으면 됩니다. 백그라운드에서 이러한 모든 작업이 이루어지는 데 필요한 리소스와 코드가 생성됩니다.  
  
 유니버설 Windows 플랫폼 앱에 대 한 사용자 인터페이스를 디자인 하는 방법에 대 한 자세한 내용은 참조  [디자인 및 UI](https://developer.microsoft.com/en-us/windows/design)합니다.  
  
 MFC 응용 프로그램의 사용자 인터페이스 만들기에 대한 자세한 내용은 [MFC Desktop Applications](../mfc/mfc-desktop-applications.md)을 참조하세요. Win32 Windows 프로그램에 대 한 정보를 참조 하십시오. [Windows 데스크톱 응용 프로그램](../windows/windows-desktop-applications-cpp.md)합니다.  
  
 C++/CLI를 사용한 Windows Forms 응용 프로그램에 대한 자세한 내용은 [.NET Framework를 사용하여 Windows Forms 응용 프로그램 만들기](http://msdn.microsoft.com/ko-kr/8e007885-6c8b-4fb2-a41d-91febd114a9b)를 참조하세요.  
  
## <a name="writing-and-editing-code"></a>코드 작성 및 편집  
 **의미 체계 색 지정**  
  
 프로젝트를 만든 후에는 모든 프로젝트 파일이 솔루션 탐색기 창에 표시됩니다. 솔루션 탐색기에서 .h 또는 .cpp 파일을 클릭하면 파일이 코드 편집기에서 열립니다. 코드 편집기는 C++ 소스 코드용 특수 워드 프로세서입니다. 언어 키워드, 메서드 및 변수 이름, 기타 코드 요소 등을 색으로 구분하여 코드를 더 쉽게 읽고 이해할 수 있도록 해 줍니다.  
  
 **Intellisense**  
  
 코드 편집기는 또한 전체적으로 IntelliSense라고 하는 몇 가지 기능을 지원합니다. 메서드를 포인터로 가리키면 일부 기본 설명을 볼 수 있습니다. 클래스 변수 이름을 입력한 다음 . 또는 ->를 입력하면 해당 클래스의 인스턴스 멤버의 목록이 표시됩니다. 클래스 이름을 입력한 다음 ::을 입력하면 정적 멤버의 목록이 표시됩니다. 클래스 또는 메서드 이름을 입력하기 시작하면 문을 완료할 제안이 표시됩니다. 자세한 내용은 [Using IntelliSense](../Topic/Using%20IntelliSense.md)을 참조하세요.  
  
 **코드 조각**  
  
 IntelliSense 코드 조각을 사용하면 일반적으로 사용되거나 복잡한 코드 구문을 바로 가기 키 입력으로 생성할 수 있습니다. 자세한 내용은 [Code Snippets](../Topic/Code%20Snippets.md)을 참조하세요.  
  
## <a name="navigating-code"></a>코드 탐색  
 보기 메뉴에서는 코드 파일에서 탐색하기 위한 여러 창 및 도구에 액세스할 수 있습니다. 이러한 창에 대한 자세한 내용은 [Viewing the Structure of Code](../Topic/Viewing%20the%20Structure%20of%20Code.md)를 참조하세요.  
  
 **솔루션 탐색기**  
  
 모든 버전의 Visual Studio에서 솔루션 탐색기 창을 사용하여 프로젝트 내의 파일 사이를 탐색할 수 있습니다. .h 또는 .cpp 파일 아이콘을 확장하면 파일의 해당 클래스를 볼 수 있습니다. 클래스를 확장하면 해당 멤버가 표시됩니다. 멤버를 두 번 클릭하면 파일 내에서 해당 멤버의 정의 또는 구현으로 이동합니다.  
  
 **클래스 뷰 및 코드 정의 창**  
  
 클래스 뷰 창을 사용하면 부분 클래스를 비롯하여 전체 파일의 네임스페이스 및 클래스를 볼 수 있습니다. 각 네임스페이스 또는 클래스를 확장하여 해당 멤버를 표시하고, 이러한 멤버를 두 번 클릭하여 소스 파일 내의 해당 위치로 이동할 수 있습니다. 코드 정의 창을 여는 경우 클래스 뷰에서 선택한 유형의 정의 또는 구현을 볼 수 있습니다.  
  
 **개체 브라우저**  
  
 개체 브라우저를 사용하여 Windows 런타임 구성 요소(.winmd 파일), .NET 어셈블리, COM 형식 라이브러리에서 형식 정보를 탐색합니다. Win32 DLL에는 사용되지 않습니다.  
  
 **정의/선언으로 이동**  
  
 API 이름 또는 멤버 변수에서 F12 키를 누르면 해당 정의로 이동합니다. 정의가 .winmd 파일( [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 앱용)에 포함된 경우 개체 브라우저에 형식 정보가 표시됩니다. 변수 또는 형식 이름을 마우스 오른쪽 단추로 클릭하거나 상황에 맞는 메뉴에서 옵션을 선택하여 정의로 이동하거나 선언으로 이동할 수도 있습니다.  
  
 **모든 참조 찾기**  
  
 소스 코드 파일에서 형식 이름이나 변수의 메서드 위에 마우스 커서를 놓고 마우스 오른쪽 단추를 클릭한 후에 모든 참조 찾기를 선택하면 파일, 프로젝트 또는 솔루션 내에서 해당 형식이 사용된 모든 위치의 목록이 반환됩니다. 모든 참조 찾기는 지능형이므로 다른 범위의 다른 변수에 동일한 이름이 있더라도 동일한 변수의 인스턴스만 반환합니다.  
  
 **아키텍처 탐색기 및 종속성 그래프 (Ultimate)**  
  
 아키텍처 탐색기를 사용하여 코드 내의 다양한 요소 간의 관계를 볼 수 있습니다. 자세한 내용은 [아키텍처 탐색기로 코드 찾기](http://msdn.microsoft.com/ko-kr/b1707926-ef73-47f9-92cd-e00d0fac7e76)를 참조하세요. 종속성 그래프를 사용하여 종속성 관계를 볼 수 있습니다. 자세한 내용은 [How to: Generate Dependency Graphs for C and C++ Code](http://msdn.microsoft.com/ko-kr/3bd5cf9f-62f6-41d0-9f35-d4b2637cba3c)을 참조하세요.  
  
## <a name="adding-and-editing-resources"></a>리소스 추가 및 편집  
 Visual Studio 데스크톱 프로젝트의 컨텍스트에서 "리소스"라는 용어에는 대화 상자, 아이콘, 지역화 가능한 문자열, 시작 화면, 데이터베이스 연결 문자열 또는 실행 파일에 포함하려는 임의 데이터가 포함됩니다.  
  
 네이티브 데스크톱 C++ 프로젝트에서 리소스 추가 및 편집에 대한 자세한 내용은 [Working with Resource Files](../mfc/working-with-resource-files.md)을 참조하세요.  
  
## <a name="building-compiling-and-linking"></a>빌드(컴파일 및 연결)  
 **Ctrl + Shift + B** 를 누르면 프로젝트를 컴파일하고 연결합니다. Visual Studio에서는 실행 코드를 만드는 데 [MSBuild](MSBuild1.md) 를 사용합니다. 아래에서 일반 빌드 옵션을 설정할 수 **도구 및 #124; 옵션 &#124; 프로젝트 및 솔루션** 에서 특정 프로젝트에 대 한 속성을 설정할 수 있습니다 **프로젝트 &#124; 속성**합니다. 빌드 오류 및 경고는 오류 목록에 보고 됩니다 (**Ctrl +\\, E**). 때때로 추가 정보가 출력 창에 표시됩니다(**Alt + 2**). 자세한 내용은 참조  [프로젝트 속성](../ide/working-with-project-properties.md) 및 [Visual Studio에서 c + + 프로젝트 빌드](../ide/building-cpp-projects-in-visual-studio.md)합니다.  
  
 Visual C++ 컴파일러(cl.exe) 및 다양한 빌드 관련 독립 실행형 도구(예: NMAKE 및 LIB)를 명령줄에서 바로 사용할 수도 있습니다. 자세한 내용은 [Building on the Command Line](../build/building-on-the-command-line.md) 및 [C/C++ Building Reference](../build/reference/c-cpp-building-reference.md)를 참조하세요.  
  
## <a name="testing"></a>테스트  
 Visual Studio에는 네이티브 C++ 및 C++/CLI에 대한 단위 테스트 프레임워크가 들어 있습니다. 자세한 내용은 [단위 테스트를 사용하여 코드 확인](../Topic/Unit%20Test%20Your%20Code.md) 및 [C++용 Microsoft 단위 테스트 프레임워크를 사용하여 C/C++용 단위 테스트 작성](../Topic/Writing%20Unit%20tests%20for%20C-C++%20with%20the%20Microsoft%20Unit%20Testing%20Framework%20for%20C++.md)을 참조하세요.  
  
## <a name="debugging"></a>디버깅  
 프로젝트 구성이 디버그로 설정된 경우 F5 키를 눌러 프로그램을 디버그할 수 있습니다. 디버그하는 동안 F9 키를 눌러 중단점을 설정하고, F10 키를 눌러 코드를 단계별로 진행하고, 지정된 변수 또는 레지스터의 값을 확인하고, 일부 경우에는 코드 변경 후 다시 컴파일하지 않고 디버깅을 계속할 수도 있습니다. 자세한 내용은 [Debugging in Visual Studio](../Topic/Debugging%20in%20Visual%20Studio.md)을 참조하세요.  
  
## <a name="deploying-completed-applications"></a>완성된 응용 프로그램 배포  
 배포는 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 를 통해 Windows 스토어를 통해 고객에 게는 **프로젝트 &#124; 저장소** 메뉴 옵션입니다. CRT 배포는 백그라운드에서 자동으로 처리됩니다. 자세한 내용은 [앱 판매](http://go.microsoft.com/fwlink/p/?LinkId=262280)를 참조하세요.  
  
 네이티브 C++ 데스크톱 응용 프로그램을 다른 컴퓨터에 배포할 때는 응용 프로그램 자체 및 이 응용 프로그램이 종속되는 라이브러리 파일을 설치해야 합니다. 중앙 배포, 로컬 배포 또는 정적 연결의 세 가지 방법으로 응용 프로그램과 함께 Visual C++ 런타임을 배포할 수 있습니다. 자세한 내용은 참조 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)합니다.  
  
 C + 배포에 대 한 자세한 내용은 + CLI 프로그램 참조 [개발자를 위한 배포 가이드](../Topic/.NET%20Framework%20Deployment%20Guide%20for%20Developers.md),  
  
## <a name="other-tools"></a>기타 도구  
  
## <a name="related-articles"></a>관련 문서  
  
|||  
|-|-|  
|[Visual Studio 버전의 visual c + + 도구 및 템플릿](../ide/visual-cpp-tools-and-templates-in-visual-studio-editions.md)|다양한 Visual Studio 버전에서 사용할 수 있는 기능을 보여 줍니다.|  
|[Visual c + + 둘러보기](http://msdn.microsoft.com/ko-kr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)|Visual Studio 개발 환경 및 만들 수 있는 C++ 앱 종류에 대한 개요를 제공합니다.|  
|[Visual c + + 프로젝트 만들기 및 관리](../ide/creating-and-managing-visual-cpp-projects.md)|Visual Studio의 C++ 프로젝트 및 이러한 프로젝트를 만들고 관리하는 방법을 설명하는 다른 문서 링크에 대한 개요를 제공합니다.|  
|[C/c + + 프로그램 빌드](../build/building-c-cpp-programs.md)|C++ 프로젝트를 빌드하는 방법을 설명합니다.|  
|[데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)|C++ 앱 및 배포에 대해 자세히 설명하는 다른 문서로 연결되는 링크에 대한 개요를 제공합니다.|  
|[프로그램 이식 및 업그레이드](http://msdn.microsoft.com/ko-kr/c36c44b3-5a9b-4bb4-9b7a-469aa770ed00)|이전 버전의 Visual Studio에서 만들어진 C++ 앱을 여는 방법 및 Visual Studio 이외의 다른 도구를 사용해서 만들어진 응용 프로그램을 여는 방법을 설명하는 문서의 링크입니다.|  
|||  
|[Visual C++](../top/visual-cpp-in-visual-studio-2015.md)|Visual Studio에 포함된 Visual C++의 주요 기능을 설명하고 Visual C++ 설명서의 나머지 부분에 연결합니다.|