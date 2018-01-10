---
title: "Visual c + +의 Dll | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- executable files [C++]
- dynamic linking [C++]
- linking [C++], dynamic vs. static
- DLLs [C++]
- DLLs [C++], about DLLs
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed3679d29b8d181e2cbd9896d0322fea634bfbf0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="dlls-in-visual-c"></a>Visual C++의 DLL  
  
Windows에서 동적 연결 라이브러리 (DLL)는 함수 및 리소스의 공유 라이브러리로 사용 되는 실행 파일의 종류를 사용 합니다. 동적 링크는 함수를 호출 하거나 별도 파일에 저장 된 리소스를 사용 하 여 실행 파일 수 있도록 하는 운영 체제 기능입니다. 이러한 함수 및 리소스는 사용하는 실행 파일과 별도로 컴파일 및 배포할 수 있습니다. DLL; 독립형 실행 파일이 아닙니다. 이 클래스를 호출 하는 응용 프로그램의 컨텍스트에서 실행 됩니다. 응용 프로그램이 로드 될 때 운영 체제는 응용 프로그램의 메모리 공간에 DLL 로드할 수 (*암시적 링크*), 또는 런타임에 요청 시 (*명시적 링크*). DLL을 통해 실행 파일 간에 함수 및 리소스를 쉽게 공유할 수 있습니다. 즉, 여러 개의 응용 프로그램이 메모리에 있는 하나의 DLL 복사본 내용을 동시에 액세스할 수 있습니다.  
  
## <a name="differences-between-dynamic-linking-and-static-linking"></a>동적 링크와 정적 링크의 차이점  
  
작성 될 때 사용 하는 실행 파일에 정적 라이브러리에서 모든 개체 코드를 복사 정적 연결 합니다. 동적 링크 Windows에서 찾아 데이터 항목이 나 함수를 포함 하는 DLL을 로드 하기 위해 런타임에 필요한 정보만 포함 됩니다. DLL을 만들 때이 정보를 포함 하는 가져오기 라이브러리를 만들어야 합니다. DLL을 호출 하는 실행 파일을 빌드할 때 링커를 사용 하 여 내보낸된 기호 가져오기 라이브러리에서 Windows 로더를 위해이 정보를 저장 합니다. 로더가 DLL을 로드 DLL 응용 프로그램의 메모리 공간에 매핑됩니다. 특별 한 함수는 DLL에 있는 경우 `DllMain`, DLL 필요한 모든 초기화를 수행 하기 위해 호출 됩니다.  
  
<a name="differences-between-applications-and-dlls"></a>  
  
## <a name="differences-between-applications-and-dlls"></a>응용 프로그램과 Dll의 차이점  
  
Dll과 응용 프로그램은 모두 실행 모듈 하는 경우에 여러 가지 방법으로 다릅니다. 최종 사용자에 게는 가장 확실 한 차이점은 Dll은 직접 실행할 수 있는 응용 프로그램이 없습니다. 시스템의 관점에서 응용 프로그램과 Dll 사이의 기본적인 차이점 두 있습니다.  
  
-   DLL에는 하나의 인스턴스만 가질 수 있지만 응용 프로그램에서 시스템에서 동시에 실행의 여러 인스턴스를 가질 수 있습니다.  
  
-   응용 프로그램 등 스택, 실행, 글로벌 메모리, 파일 핸들, 메시지 큐의 스레드를 소유할 수 있는 프로세스 로드 될 수 있지만 DLL 수 없습니다.  
  
<a name="advantages-of-using-dlls"></a>  
  
## <a name="advantages-of-using-dlls"></a>Dll 사용의 장점  
  
코드 및 리소스에 정적 링크 대신 동적 링크는 여러 가지 이점을 제공 합니다. DLL을 사용하면 메모리 공간을 절약하고 교환을 줄일 수 있습니다. 여러 응용 프로그램이 DLL의 단일 복사본을 사용할 수 있는 경우 디스크 공간 및 다운로드 대역폭을 절약할 수 있습니다. 별도로 DLL을 배포 및 업데이트할 수 있으므로 모든 코드를 다시 빌드하여 배포하지 않고 출시 후 지원 및 소프트웨어 업데이트를 제공할 수 있습니다. DLL은 다중 언어 프로그램을 지원하고 쉽게 응용 프로그램의 국가별 버전을 만들 수 있게 해주는 로캘별 리소스를 제공하는 편리한 방법입니다. 명시적 링크 검색 하 고 런타임 시 같은 새로운 기능을 제공 하는 확장 Dll을 로드 하도록 응용 프로그램을 허용할 수 있습니다.  
  
동적 링크는 다음과 같은 이점이 있습니다.  
  
-   동적 링크 메모리에 저장 되 고 교환 줄어듭니다. 많은 프로세스 DLL 동시에 사용할 수, 메모리에서 DLL의 읽기 전용 부분의 단일 복사본을 공유 합니다. 반면, 정적으로 연결 된 라이브러리를 사용 하 여 작성 되는 모든 응용 프로그램에 Windows는 메모리에 로드 해야 하는 라이브러리 코드의 전체 복사본입니다.  
  
-   동적 연결 디스크 공간과 대역폭 절약 됩니다. 대부분의 응용 프로그램에는 디스크에 DLL의 단일 복사본을 공유할 수 있습니다. 반면, 정적 연결 라이브러리를 사용 하 여 작성 하는 각 응용 프로그램에는 더 많은 디스크 공간을 사용 하 여 더 많은 대역폭을 전송 하며 해당 실행 가능 이미지에 연결 된 라이브러리 코드를 있습니다.  
  
-   유지 관리, 보안 수정 하 고 업그레이드를 더 쉬워질 수 있습니다. DLL에서 일반 함수를 사용 하는 응용 프로그램, 다음 함수 인수 및 반환 값을 변경 하지 않는 상태로 버그 수정 구현 있고 DLL에 업데이트를 배포 합니다. Dll이 업데이트 되는 경우 응용 프로그램을 사용 하는 필요가 없습니다 컴파일하거나, 없으며 배포 되는 즉시 새 DLL의 사용. 반면, 정적으로 연결 된 개체 코드에서 수정 해야 다시 연결 하 고이 사용 하는 모든 응용 프로그램을 다시 배포 합니다.  
  
-   출시 후 지원을 제공 하기 위해 Dll을 사용할 수 있습니다. 예를 들어 디스플레이 드라이버 DLL 응용 프로그램을 출시할 때 사용할 수 없었던 디스플레이 지원 하기 위해 수정할 수 있습니다. 명시적 링크 Dll로 응용 프로그램 확장을 로드를 사용 하 여 및 새 기능을 다시 작성 하거나 다시 배포 하지 않고 앱을 추가할 수 있습니다.  
  
-   동적 연결 하면 보다 쉽게 서로 다른 프로그래밍 언어로 작성 된 응용 프로그램을 지원할 수 있습니다. 함수의 호출 규칙에 따라 프로그램으로 서로 다른 프로그래밍 언어로 작성 된 프로그램에서 동일한 DLL 함수를 호출할 수 있습니다. 프로그램과 DLL 함수를 다음과 같은 방법으로 호환 되어야 합니다: 사용 하는 함수는 인수를 스택에 밀어 넣은 수, 함수 또는 응용 프로그램, 스택을 정리 하는 일을 담당 인지 및 인수 인지 순서 레지스터에 전달 합니다.  
  
-   동적 링크 MFC 라이브러리 클래스를 확장 하는 메커니즘을 제공 합니다. 기존 MFC 클래스에서 클래스를 파생 시킬 수 있으며 MFC 응용 프로그램에서 사용 하기 위한 MFC 확장 DLL에에서 배치할 수 있습니다.  
  
-   동적 작업을 연결 하면 응용 프로그램의 국가별 버전 생성 등의 더 쉽습니다. 이 DLL의 로캘 관련 리소스를 배치 하 여 응용 프로그램의 국가별 버전을 만들 훨씬 쉽습니다. 응용 프로그램의 많은 지역화 된 버전 제공 되는 경우 대신 별도 리소스 DLL에에서 문자열 및 각 언어에 대 한 이미지를 배치할 수 있습니다 및 다음 응용 프로그램에서 런타임에 해당 로캘에 대 한 적절 한 리소스를 로드할 수 있습니다.   
  
 단점은 Dll을 사용 하 여 응용 프로그램 자체 포함 된; 된다는 점입니다. 배포 또는 설치의 일부로 직접 확인 해야 하는 별도 DLL 모듈의 존재 여부에 따라 다릅니다.  
  
  
## <a name="more-information-on-how-to-create-and-use-dlls"></a>만들기 및 Dll을 사용 하는 방법에 대 한 자세한 내용  
  
다음 항목에서는 Visual c + +에서 Dll을 프로그래밍 하는 방법에 대 한 자세한 정보를 제공합니다.  
  
 [연습: 동적 연결 라이브러리 만들기 및 사용(C++)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)  
 Visual Studio를 사용하여 DLL을 만들고 사용하는 방법에 대해 설명합니다.  
  
 [DLL의 종류](../build/kinds-of-dlls.md)  
 빌드할 수 있는 다양한 종류의 DLL에 대한 정보를 제공합니다.  
  
 [DLL 관련 질문과 대답](../build/dll-frequently-asked-questions.md)  
 DLL 관련 질문과 대답을 제공합니다.  
  
 [DLL에 실행 파일 링크](../build/linking-an-executable-to-a-dll.md)  
 DLL에 대한 명시적 및 암시적 링크에 대해 설명합니다.  
  
 [DLL 초기화](../build/run-time-library-behavior.md#initializing-a-dll)  
 DLL 초기화 코드 DLL이 로드 될 때 실행 되어야 하는 방법을 설명 합니다.  
  
 [DLL 및 Visual C++ 런타임 라이브러리 동작](../build/run-time-library-behavior.md)  
 런타임 라이브러리가 DLL 시동을 순서대로 수행하는 과정을 설명합니다.  
  
 [LoadLibrary 및 AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
 사용에 대해 설명 **LoadLibrary** 및 `AfxLoadLibrary` 를 명시적으로 런타임 시 DLL에 연결 합니다.  
  
 [GetProcAddress](../build/getprocaddress.md)  
 사용 하 여 설명 **GetProcAddress** DLL에서 내보낸된 함수 주소를 가져옵니다.  
  
 [FreeLibrary 및 AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
 사용 하 여 설명 **FreeLibrary** 및 `AfxFreeLibrary` 때 DLL 모듈이 더 이상 필요 합니다.  
  
 [Windows에서 DLL을 찾는 데 사용되는 검색 경로](../build/search-path-used-by-windows-to-locate-a-dll.md)  
 시스템에서 DLL을 찾기 위해 Windows 운영 체제가 사용하는 검색 경로에 대해 설명합니다.  
  
 [동적으로 MFC에 링크된 기본 MFC DLL의 모듈 상태](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)  
 MFC DLL 동적으로 MFC에 링크 되는 일반적인의 모듈 상태를 설명 합니다.  
  
 [MFC 확장명 DLL](../build/extension-dlls-overview.md)  
 기존 MFC 라이브러리 클래스에서 파생된 다시 사용할 수 있는 클래스를 구현하는 DLL에 대해 설명합니다.  
  
 [리소스 전용 DLL 만들기](../build/creating-a-resource-only-dll.md)  
 아이콘, 비트맵, 문자열 및 대화 상자 등의 리소스만 포함된 리소스 전용 DLL에 대해 설명합니다.  
  
 [MFC 응용 프로그램의 지역화된 리소스: 위성 DLL](../build/localized-resources-in-mfc-applications-satellite-dlls.md)  
 여러 언어로 지역화된 응용 프로그램을 만드는 데 도움이 되는 위성 DLL에 대한 향상된 지원을 제공합니다.  
  
 [가져오기 및 내보내기](../build/importing-and-exporting.md)  
 DLL에서 함수를 내보내거나 응용 프로그램으로 공용 기호를 가져오는 방법에 대해 설명합니다.  
  
 [액티브 기술 및 DLL](../build/active-technology-and-dlls.md)  
 DLL 내에서 개체 서버가 구현될 수 있도록 합니다.  
  
 [DLL의 자동화](../build/automation-in-a-dll.md)  
 MFC DLL 마법사 지원의 자동화 옵션이 무엇인지 설명합니다.  
  
 [MFC DLL의 명명 규칙](../build/naming-conventions-for-mfc-dlls.md)  
 MFC에 포함된 DLL 및 라이브러리가 구조적 명명 규칙을 지키는 방법에 대해 설명합니다.  
  
 [Visual Basic 응용 프로그램에서 DLL 함수 호출](../build/calling-dll-functions-from-visual-basic-applications.md)  
 Visual Basic 응용 프로그램에서 DLL 함수를 호출하는 방법에 대해 설명합니다.  
  
## <a name="related-sections"></a>관련 단원  
  
 [DLL의 일부로 MFC 사용](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
 Windows 동적 연결 라이브러리의 일부로 MFC 라이브러리를 사용할 수 있는 기본 MFC Dll에 설명 합니다.  
  
 [MFC의 DLL 버전](../mfc/tn033-dll-version-of-mfc.md)  
 어떻게 MFCxx.dll를 사용할 수 있습니다 및 MFCxxD.dll (여기서 x는 MFC 버전 번호) 공유 동적 연결 라이브러리 MFC 응용 프로그램 및 MFC 확장 Dll 설명 합니다.  
