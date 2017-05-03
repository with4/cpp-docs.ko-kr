---
title: "DLL(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5b8bcc57-64dd-4c54-9f24-26a25bd5dddd
caps.latest.revision: 21
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 21
---
# DLL(C++/CX)
Visual Studio를 사용하여 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 응용 프로그램에서 사용할 수 있는 표준 Win32 DLL 또는 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 구성 요소 DLL을 만들 수 있습니다. 특정 버전의 Visual Studio 또는 [!INCLUDE[vs_dev11_long](../cppcx/includes/vs-dev11-long-md.md)] 이전 버전의 Visual C\+\+ 컴파일러를 사용하여 만든 표준 DLL은 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 응용 프로그램에서 올바르게 로드되지 않을 수 있으며 [!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)]의 응용 프로그램 확인 테스트를 통과하지 않을 수 있습니다.  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소 DLL  
 거의 모든 경우에 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 응용 프로그램에서 사용할 DLL을 만들려면 해당 이름의 프로젝트 이름을 사용하여 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소로 만듭니다. 공용 또는 전용 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식이 있는 DLL에 대한 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소 프로젝트를 만들 수 있습니다.[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소는 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 호환 언어로 작성된 응용 프로그램에서 액세스할 수 있습니다. 기본적으로 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소 프로젝트의 컴파일러 설정은 **\/ZW** 스위치를 사용합니다. .winmd 파일은 루트 네임스페이스와 이름이 같아야 합니다. 예를 들어 이름이 A.B.C.MyClass인 클래스는 이름이 A.winmd, A.B.winmd 또는 A.B.C.winmd인 메타데이터 파일에 정의된 경우에만 인스턴스화될 수 있습니다. DLL의 이름은 .winmd 파일 이름과 일치하지 않아도 됩니다.  
  
 자세한 내용은 [C\+\+로 Windows Runtime 구성 요소 만들기](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md)을 참조하세요.  
  
#### 프로젝트에서 타사 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소 이진 파일을 참조하려면  
  
1.  DLL을 사용하게 될 프로젝트에 대한 바로 가기 메뉴를 연 다음 **속성**을 선택합니다.**공용 속성** 페이지에서 **새 참조 추가** 단추를 선택합니다.  
  
2.  [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소는 DLL 파일과 메타데이터가 포함된 .winmd 파일로 구성됩니다. 일반적으로 이러한 파일은 동일한 폴더에 있습니다.**참조 추가** 대화 상자의 왼쪽 창에서 **찾아보기** 단추를 선택한 다음 DLL 및 .winmd 파일의 위치로 이동합니다. 자세한 내용은 [자습서: 확장 SDK 만들기 및 사용](http://msdn.microsoft.com/ko-kr/001e2fca-3d56-43ab-a5e0-0561d085679f)을 참조하세요.  
  
## 표준 DLL  
 공용 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식을 사용하거나 생성하지 않는 C\+\+ 코드용 표준 DLL을 만들고 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 앱에서 사용할 수 있습니다. 기존 DLL을 마이그레이션하여 이 버전의 Visual Studio를 컴파일하되 코드를 Windows 런타임 구성 요소 프로젝트로 변환하지 않으려면 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] DLL 프로젝트 형식을 사용합니다. 다음 단계를 사용할 때 DLL은 .appx 패키지의 앱 실행 파일과 함께 배포됩니다.  
  
#### Visual Studio에서 표준 DLL을 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택한 다음 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] DLL 템플릿을 선택합니다.  
  
2.  프로젝트의 이름을 입력한 다음 **확인** 단추를 선택합니다.  
  
3.  코드를 추가합니다. 내보내려는 함수\(예: `__declspec(dllexport)`\)에 대해 `__declspec(dllexport) Add(int I, in j);`를 사용하세요.  
  
4.  `#include winapifamily.h`를 추가하여 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 응용 프로그램용 Windows SDK의 헤더 파일을 포함하고 매크로 `WINAPI_FAMILY=WINAPI_PARTITION_APP`를 설정합니다.  
  
#### 동일한 솔루션의 표준 DLL 프로젝트를 참조하려면  
  
1.  DLL을 사용하게 될 프로젝트에 대한 바로 가기 메뉴를 연 다음 **속성**을 선택합니다.**공용 속성** 페이지에서 **새 참조 추가** 단추를 선택합니다.  
  
2.  왼쪽 창에서 **솔루션**을 선택한 다음 오른쪽 창에서 적절한 확인란을 선택합니다.  
  
3.  소스 코드 파일에서 필요에 따라 DLL 헤더 파일에 대해 `#include` 문을 추가합니다.  
  
#### 표준 DLL 이진 파일을 참조하려면  
  
1.  DLL 파일, .lib 파일 및 헤더 파일을 복사하고 현재 프로젝트 폴더와 같이 알려진 위치에 붙여 넣습니다.  
  
2.  DLL을 사용하게 될 프로젝트에 대한 바로 가기 메뉴를 연 다음 **속성**을 선택합니다.**구성 속성**, **링커**, **입력** 페이지에서 .lib 파일을 종속성으로 추가합니다.  
  
3.  소스 코드 파일에서 필요에 따라 DLL 헤더 파일에 대해 `#include` 문을 추가합니다.  
  
#### [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 응용 프로그램과의 호환을 위해 기존의 Win32 DLL을 마이그레이션하려면  
  
1.  [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] DLL 형식의 프로젝트를 만들고 기존 소스 코드를 추가합니다.  
  
2.  `#include winapifamily.h`를 추가하여 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 응용 프로그램용 Windows SDK의 헤더 파일을 포함하고 매크로 `WINAPI_FAMILY=WINAPI_PARTITION_APP`를 설정합니다.  
  
3.  소스 코드 파일에서 필요에 따라 DLL 헤더 파일에 대해 `#include` 문을 추가합니다.  
  
## 참고 항목  
 [\(NOTINBUILD\) 고급 항목](http://msdn.microsoft.com/ko-kr/1ccff0cf-a6cc-47ef-a05f-eba6307b3ced)