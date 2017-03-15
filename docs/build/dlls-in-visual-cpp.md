---
title: "Visual C++의 DLL | Microsoft Docs"
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
helpviewer_keywords: 
  - "DLL[C++]"
  - "DLL[C++], DLLs 정보"
  - "동적 링크[C++]"
  - "실행 파일[C++]"
  - "링크[C++], 동적과 정적 비교"
ms.assetid: 5216bca4-51e2-466b-b221-0e3e776056f0
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual C++의 DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DLL\(동적 연결 라이브러리\)은 함수 및 리소스의 공유 라이브러리로 사용되는 실행 파일입니다.  동적 연결을 사용하면 실행 파일이 함수를 호출하거나 별도 파일에 저장된 리소스를 사용할 수 있습니다.  이러한 함수 및 리소스는 사용하는 실행 파일과 별도로 컴파일 및 배포할 수 있습니다.  실행 파일이 로드될 때 또는 런타임에 요청 시 운영 체제에서 실행 파일의 메모리 공간에 DLL을 로드할 수 있습니다.  DLL을 통해 실행 파일 간에 함수 및 리소스를 쉽게 공유할 수 있습니다.  즉, 여러 개의 응용 프로그램이 메모리에 있는 하나의 DLL 복사본 내용을 동시에 액세스할 수 있습니다.  
  
 정적 연결은 .lib 파일에 있는 모든 개체 코드를 실행 파일에 복사합니다.  동적 연결에는 런타임에 데이터 항목이나 함수를 포함하는 DLL을 찾아서 로드하는 데 필요한 정보만 포함됩니다.  DLL을 만들 때 이 정보를 포함하는 .lib 파일도 만듭니다.  DLL을 호출하는 실행 파일을 빌드하는 경우 링커는 .lib 파일의 내보낸 기호를 사용하여 로더를 위해 이 정보를 저장합니다.  로더가 DLL을 로드하면 DLL이 실행 파일의 메모리 공간에 매핑됩니다.  DLL의 특수 함수인 `DllMain`이 DLL에 필요한 초기화를 수행하기 위해 호출됩니다.  
  
 정적 링크 대신 동적 링크를 사용하는 데에는 몇 가지 장점이 있습니다.  DLL을 사용하면 메모리 공간을 절약하고 교환을 줄일 수 있습니다.  여러 응용 프로그램이 DLL의 단일 복사본을 사용할 수 있는 경우 디스크 공간 및 다운로드 대역폭을 절약할 수 있습니다.  별도로 DLL을 배포 및 업데이트할 수 있으므로 모든 코드를 다시 빌드하여 배포하지 않고 출시 후 지원 및 소프트웨어 업데이트를 제공할 수 있습니다.  DLL은 다중 언어 프로그램을 지원하고 쉽게 응용 프로그램의 국가별 버전을 만들 수 있게 해주는 로캘별 리소스를 제공하는 편리한 방법입니다.  
  
 다음 항목에서는 DLL을 프로그래밍하는 방법에 대한 자세한 정보를 제공합니다.  
  
## 단원 내용  
 [연습: 동적 연결 라이브러리 만들기 및 사용\(C\+\+\)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)  
 Visual Studio를 사용하여 DLL을 만들고 사용하는 방법에 대해 설명합니다.  
  
 [응용 프로그램과 DLL의 차이점](../build/differences-between-applications-and-dlls.md)  
 응용 프로그램과 DLL 사이의 기본적인 차이점을 설명합니다.  
  
 [DLL 사용의 장점](../build/advantages-of-using-dlls.md)  
 동적 연결의 장점을 설명합니다.  
  
 [DLL의 종류](../build/kinds-of-dlls.md)  
 빌드할 수 있는 다양한 종류의 DLL에 대한 정보를 제공합니다.  
  
 [DLL 관련 질문과 대답](../build/dll-frequently-asked-questions.md)  
 DLL 관련 질문과 대답을 제공합니다.  
  
 [DLL에 실행 파일 링크](../build/linking-an-executable-to-a-dll.md)  
 DLL에 대한 명시적 및 암시적 링크에 대해 설명합니다.  
  
 [DLL 초기화](../build/initializing-a-dll.md)  
 DLL이 로드될 때 실행되어야 하는 메모리 할당과 같은 DLL 초기화에 대해 설명합니다.  
  
 [런타임 라이브러리 동작](../build/run-time-library-behavior.md)  
 런타임 라이브러리가 DLL 시동을 순서대로 수행하는 과정을 설명합니다.  
  
 [LoadLibrary 및 AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
 **LoadLibrary** 및 `AfxLoadLibrary`를 사용하여 런타임에 명시적으로 DLL에 연결하는 방법을 설명합니다.  
  
 [GetProcAddress](../build/getprocaddress.md)  
 **GetProcAddress**를 사용하여 DLL의 내보낸 함수 주소를 얻는 방법에 대해 설명합니다.  
  
 [FreeLibrary 및 AfxFreeLibrary](../build/freelibrary-and-afxfreelibrary.md)  
 DLL 모듈이 더 이상 필요하지 않을 경우의 **FreeLibrary** 및 `AfxFreeLibrary` 사용에 대해 설명합니다.  
  
 [Windows에서 DLL을 찾는 데 사용되는 검색 경로](../build/search-path-used-by-windows-to-locate-a-dll.md)  
 시스템에서 DLL을 찾기 위해 Windows 운영 체제가 사용하는 검색 경로에 대해 설명합니다.  
  
 [동적으로 MFC에 링크하는 기본 DLL의 모듈 상태](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)  
 MFC에 동적으로 연결된 기본 DLL의 모듈 상태에 대해 설명합니다.  
  
 [확장 DLL](../build/extension-dlls-overview.md)  
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
  
## 관련 단원  
 [DLL의 일부로 MFC 사용](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
 Windows 동적 연결 라이브러리의 일부로 MFC 라이브러리를 사용할 수 있게 하는 기본 DLL에 대해 설명합니다.  
  
 [MFC의 DLL 버전](../mfc/tn033-dll-version-of-mfc.md)  
 MFC 응용 프로그램 및 확장 DLL과 함께 MFCxx.dll 및 MFCxxD.dll\(여기서 x는 MFC 버전 번호\) 공유 동적 연결 라이브러리를 사용하는 방법에 대해 설명합니다.  
  
 [\(NOTINBUILD\)Visual C\+\+ Programming Methodologies](http://msdn.microsoft.com/ko-kr/0822f806-fa81-4b65-bf0f-1e2921f30c95)  
 Visual C\+\+ 라이브러리에 대한 개념적인 정보를 설명하는 항목 및 다양한 코딩 기술 및 기법을 설명하는 항목에 대한 링크를 제공합니다.