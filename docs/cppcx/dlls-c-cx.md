---
title: Dll (C + + /cli CX) | Microsoft Docs
ms.custom: 
ms.date: 02/03/2017
ms.prod: windows-client-threshold
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b8bcc57-64dd-4c54-9f24-26a25bd5dddd
caps.latest.revision: "21"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a759541dd31121f12283f9b2b0c5b468da477554
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dlls-ccx"></a>DLL(C++/CX)
Visual Studio를 사용 하 여 표준 Win32 DLL 또는 유니버설 Windows 플랫폼 앱에서 사용할 수 있는 DLL Windows 런타임 구성 요소를 만들 수 있습니다. Visual Studio 또는 Visual Studio 2012는 유니버설 Windows 플랫폼 앱에서 올바르게 로드 되지 않을 수 있습니다 및에서 응용 프로그램 확인 테스트를 통과 하지 않을 수 있습니다 보다 이전 Visual c + + 컴파일러의 버전을 사용 하 여 만든 표준 DLL은 [!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)]합니다.  
  
## <a name="windows-runtime-component-dlls"></a>Windows 런타임 구성 요소 Dll  
 거의 모든 경우에는 유니버설 Windows 플랫폼 앱에서 사용할 DLL을 만들려는 경우으로 만들어야 Windows 런타임 구성 요소를 해당 이름의 프로젝트 템플릿을 사용 하 여 합니다. 공용 또는 개인 Windows 런타임 형식이 있는 Dll에 대 한 Windows 런타임 구성 요소 프로젝트를 만들 수 있습니다. Windows 런타임 구성 요소는 모든 Windows 런타임 호환 언어로 작성 된 응용 프로그램에서 액세스할 수 있습니다. 기본적으로 Windows 런타임 구성 요소에 대 한 컴파일러 설정을 사용 하 여를 프로젝트는 **/ZW** 전환 합니다. .winmd 파일은 루트 네임스페이스와 이름이 같아야 합니다. 예를 들어 이름이 A.B.C.MyClass인 클래스는 이름이 A.winmd, A.B.winmd 또는 A.B.C.winmd인 메타데이터 파일에 정의된 경우에만 인스턴스화될 수 있습니다. DLL의 이름은 .winmd 파일 이름과 일치하지 않아도 됩니다.  
  
 자세한 내용은 [Creating Windows Runtime Components in C++](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md)을 참조하세요.  
  
#### <a name="to-reference-a-third-party-windows-runtime-component-binary-in-your-project"></a>프로젝트의 이진 제 3 자 Windows 런타임 구성 요소를 참조 하려면  
  
1.  DLL을 사용하게 될 프로젝트에 대한 바로 가기 메뉴를 연 다음 **속성**을 선택합니다. **공용 속성** 페이지에서 **새 참조 추가** 단추를 선택합니다.  
  
2.  Windows 런타임 구성 요소는 DLL 파일과 메타 데이터가 포함 된.winmd 파일로 구성 됩니다. 일반적으로 이러한 파일은 동일한 폴더에 있습니다. **참조 추가** 대화 상자의 왼쪽 창에서 **찾아보기** 단추를 선택한 다음 DLL 및 .winmd 파일의 위치로 이동합니다. 자세한 내용은 [자습서: 확장 SDK 만들기 및 사용](http://msdn.microsoft.com/en-us/001e2fca-3d56-43ab-a5e0-0561d085679f)을 참조하세요.  
  
## <a name="standard-dlls"></a>표준 DLL  
 사용 또는 공개 Windows 런타임 형식을 생성 하 고는 유니버설 Windows 플랫폼 앱에서 사용 하지 않는 c + + 코드용 표준 DLL을 만들 수 있습니다. 기존 DLL이이 버전의 Visual Studio에서 컴파일하는 Windows 런타임 구성 요소 프로젝트에 코드를 변환 하지 않으려면을 마이그레이션하여 하 려 할 때 유니버설 Windows 플랫폼 DLL 프로젝트 형식을 사용 합니다. 다음 단계를 사용할 때 DLL은 .appx 패키지의 앱 실행 파일과 함께 배포됩니다.  
  
#### <a name="to-create-a-standard-dll-in-visual-studio"></a>Visual Studio에서 표준 DLL을 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로**, **프로젝트**, 유니버설 Windows 플랫폼 DLL 템플릿을 선택 합니다.  
  
2.  프로젝트의 이름을 입력한 다음 **확인** 단추를 선택합니다.  
  
3.  코드를 추가합니다. 내보내려는 함수(예: `__declspec(dllexport)` )에 대해 `__declspec(dllexport) Add(int I, in j);`를 사용하세요.  
  
4.  추가 `#include winapifamily.h` 매크로 설정 및 유니버설 Windows 플랫폼 앱 용 Windows SDK의 헤더 파일을 포함 하도록 `WINAPI_FAMILY=WINAPI_PARTITION_APP`합니다.  
  
#### <a name="to-reference-a-standard-dll-project-from-the-same-solution"></a>동일한 솔루션의 표준 DLL 프로젝트를 참조하려면  
  
1.  DLL을 사용하게 될 프로젝트에 대한 바로 가기 메뉴를 연 다음 **속성**을 선택합니다. **공용 속성** 페이지에서 **새 참조 추가** 단추를 선택합니다.  
  
2.  왼쪽 창에서 **솔루션**을 선택한 다음 오른쪽 창에서 적절한 확인란을 선택합니다.  
  
3.  소스 코드 파일에서 필요에 따라 DLL 헤더 파일에 대해 `#include` 문을 추가합니다.  
  
#### <a name="to-reference-a-standard-dll-binary"></a>표준 DLL 이진 파일을 참조하려면  
  
1.  DLL 파일, .lib 파일 및 헤더 파일을 복사하고 현재 프로젝트 폴더와 같이 알려진 위치에 붙여 넣습니다.  
  
2.  DLL을 사용하게 될 프로젝트에 대한 바로 가기 메뉴를 연 다음 **속성**을 선택합니다. **구성 속성**, **링커**, **입력** 페이지에서 .lib 파일을 종속성으로 추가합니다.  
  
3.  소스 코드 파일에서 필요에 따라 DLL 헤더 파일에 대해 `#include` 문을 추가합니다.  
  
#### <a name="to-migrate-an-existing-win32-dll-for-universal-windows-platform-app-compatibility"></a>유니버설 Windows 플랫폼 앱 호환성을 위해 기존의 Win32 DLL을 마이그레이션하려면  
  
1.  유니버설 Windows 플랫폼 DLL 형식의 프로젝트를 만들고 기존 소스 코드를 추가 합니다.  
  
2.  추가 `#include winapifamily.h` 매크로 설정 및 유니버설 Windows 플랫폼 앱 용 Windows SDK의 헤더 파일을 포함 하도록 `WINAPI_FAMILY=WINAPI_PARTITION_APP`합니다.  
  
3.  소스 코드 파일에서 필요에 따라 DLL 헤더 파일에 대해 `#include` 문을 추가합니다.  
  

