---
title: "정적으로 MFC에 링크된 기본 DLL | Microsoft Docs"
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
  - "DLL[C++], 기본"
  - "기본 DLL[C++]"
  - "기본 DLL[C++], MFC에 정적으로 링크됨"
  - "정적으로 링크된 DLL[C++]"
  - "USRDLL"
  - "USRDLL, MFC에 정적으로 링크됨"
ms.assetid: 2eed531c-726a-4b8a-b936-f721dc00a7fa
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 정적으로 MFC에 링크된 기본 DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

정적으로 MFC에 링크된 기본 DLL은 MFC를 내부적으로 사용하는 DLL이며, MFC 또는 비 MFC 실행 파일에서 이러한 DLL의 내보내기 함수를 호출할 수 있습니다.  이름에서 알 수 있듯이 이러한 종류의 DLL은 MFC의 정적 연결 라이브러리 버전을 사용하여 빌드됩니다.  기본 DLL에서 함수는 대개 표준 C 인터페이스를 사용하여 내보내집니다.  기본 DLL의 작성, 빌드 및 사용 방법에 대한 예제를 보려면 [DLLScreenCap](http://msdn.microsoft.com/ko-kr/2171291d-3a50-403b-90a1-d93c2acb4f4a) 샘플을 참조하십시오.  
  
 USRDLL이라는 용어는 Visual C\+\+ 설명서에서 더 이상 사용되지 않습니다.  정적으로 MFC에 링크한 기본 DLL의 특징은 이전 USRDLL의 특징과 같습니다.  
  
 정적으로 MFC에 링크된 기본 DLL에는 다음과 같은 특징이 있습니다.  
  
-   C, C\+\+, 파스칼, Visual Basic 등 DLL 사용을 지원하는 모든 언어로 클라이언트 실행 파일을 만들 수 있으며 이 실행 파일은 MFC 응용 프로그램이 아니어도 됩니다.  
  
-   DLL은 응용 프로그램에서 사용하는 것과 동일한 MFC 정적 연결 라이브러리에 링크됩니다.  따라서 DLL에 대한 별도의 정적 연결 라이브러리 버전은 필요하지 않습니다.  
  
-   MFC 버전 4.0 이전에 USRDLL은 정적으로 MFC에 링크된 기본 DLL과 같은 형식의 기능을 제공했습니다.  그러나 Visual C\+\+ 버전 4.0부터는 USRDLL이라는 용어를 사용하지 않습니다.  
  
 정적으로 MFC에 링크된 기본 DLL의 요구 사항은 다음과 같습니다.  
  
-   이 형식의 DLL에서는 `CWinApp`에서 파생된 클래스를 인스턴스화해야 합니다.  
  
-   이 형식의 DLL에서는 MFC에서 제공하는 `DllMain`을 사용합니다.  따라서 일반적인 MFC 응용 프로그램과 마찬가지로 모든 DLL과 관련된 초기화 코드는 `InitInstance` 멤버 함수에, 종료 코드는 `ExitInstance`에 포함시켜야 합니다.  
  
-   USRDLL이라는 용어가 더 이상 사용되지 않지만 컴파일러 명령줄에서는 "**\_USRDLL**"을 정의해야 합니다.  이 정의는 MFC 헤더 파일에서 가져올 선언을 결정합니다.  
  
 기본 DLL에는 MFC 응용 프로그램과 마찬가지로, `CWinApp` 파생 클래스 및 해당 응용 프로그램 클래스의 단일 개체가 있어야 합니다.  그러나 응용 프로그램의 `CWinApp` 개체와 달리 DLL의 `CWinApp` 개체에는 기본 메시지 펌프가 없습니다.  
  
 응용 프로그램이 기본 메시지 펌프를 소유하고 있어 `CWinApp::Run` 메커니즘은 DLL에 적용되지 않습니다.  DLL이 모덜리스 대화 상자를 열거나 자체의 기본 프레임 창을 갖는 경우, 응용 프로그램의 기본 메시지 펌프는 DLL에서 내보내는 루틴을 호출해야 합니다. 그러면 이 루틴이 DLL의 응용 프로그램 개체에 대한 `CWinApp::PreTranslateMessage` 멤버 함수를 호출하게 됩니다.  
  
 이 함수의 예제를 보려면 DLLScreenCap 샘플을 참조하십시오.  
  
 기호는 대개 표준 C 인터페이스를 사용하여 기본 DLL에서 내보내집니다.  기본 DLL에서 내보내기 함수의 선언 형식은 다음과 유사합니다.  
  
```  
extern "C" __declspec(dllexport) MyExportedFunction( );  
```  
  
 기본 DLL 내의 모든 메모리 할당은 DLL 내에 존재해야 하므로 DLL에서 다음 중 어떤 것도 호출 실행 파일에 전달하거나 호출 실행 파일로부터 받아서는 안 됩니다.  
  
-   MFC 개체에 대한 포인터  
  
-   MFC에서 할당한 메모리에 대한 포인터  
  
 위와 같은 작업이 필요하거나 호출 실행 파일과 DLL 사이에 MFC 파생 개체를 전달해야 하는 경우에는 확장 DLL을 빌드해야 합니다.  
  
 C 런타임 라이브러리에서 할당한 메모리에 대한 포인터는 해당 데이터의 복사본을 만들어야만 응용 프로그램과 DLL 간에 안전하게 전달됩니다.  이러한 포인터를 삭제하거나 크기를 변경하거나 사용하려면 반드시 메모리의 복사본을 만들어야 합니다.  
  
 또한 정적으로 MFC에 링크된 DLL은 공유 MFC DLL에 동적으로 링크될 수 없습니다.  정적으로 MFC에 링크된 DLL은 다른 DLL과 마찬가지로 응용 프로그램에 동적으로 바인딩되며, 응용 프로그램은 다른 DLL과 마찬가지로 그것에 링크합니다.  
  
 표준 MFC 정적 연결 라이브러리는 [MFC DLL의 명명 규칙](../build/naming-conventions-for-mfc-dlls.md)에 설명된 규칙에 따라 이름이 지정됩니다.  그러나 MFC 버전 3.0 이상에서는 링커에 링크하려는 MFC 라이브러리 버전을 직접 지정할 필요가 없습니다.  대신 MFC 헤더 파일에서 **\_DEBUG** 또는 **\_UNICODE** 등과 같은 전처리기의 정의에 따라 링크할 올바른 버전의 MFC 라이브러리를 자동으로 결정합니다.  MFC 헤더 파일에 \/DEFAULTLIB 지시문을 추가하여 링커가 특정 버전의 MFC 라이브러리에 링크하도록 합니다.  
  
## 수행할 작업  
  
-   [기본 DLL 초기화](../build/initializing-regular-dlls.md)  
  
## 추가 정보  
  
-   [DLL의 일부로 MFC 사용](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [기본 DLL에서 데이터베이스, OLE 및 소켓 확장 DLL 사용](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [MFC DLL 마법사](../mfc/reference/mfc-dll-wizard.md)  
  
-   [동적으로 MFC에 링크하는 기본 DLL](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [확장 DLL](../build/extension-dlls-overview.md)  
  
## 참고 항목  
 [DLL 종류](../build/kinds-of-dlls.md)