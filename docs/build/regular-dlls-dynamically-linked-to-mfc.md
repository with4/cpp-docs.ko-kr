---
title: "동적으로 MFC에 링크하는 기본 DLL | Microsoft Docs"
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
  - "AFX_MANAGE_STATE 매크로"
  - "DLL[C++], 기본"
  - "동적으로 링크된 DLL[C++]"
  - "기본 DLL[C++], MFC에 동적 연결"
  - "공유 DLL 버전[C++]"
ms.assetid: b4f7ab92-8723-42a5-890e-214f4e29dcd0
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 동적으로 MFC에 링크하는 기본 DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

동적으로 MFC에 링크하는 기본 DLL은 MFC를 내부적으로 사용하는 DLL이며, 이 DLL의 내보내기 함수는 MFC 또는 비 MFC 실행 파일에 의해 호출될 수 있습니다.  이름에서 알 수 있듯이 이러한 종류의 DLL은 MFC의 공유 버전이라고도 하는 MFC의 동적 연결 라이브러리 버전으로 빌드됩니다.  기본 DLL에서 함수는 대개 표준 C 인터페이스를 사용하여 내보내집니다.  
  
 현재 모듈 상태를 DLL을 위한 것으로 설정하려면 동적으로 MFC에 링크하는 기본 DLL에 있는 모든 내보내기 함수의 처음 부분에 `AFX_MANAGE_STATE` 매크로를 추가해야 합니다.  DLL에서 내보낸 함수의 시작 부분에 다음과 같은 코드 행을 추가하여 이를 수행합니다.  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 동적으로 MFC에 링크하는 기본 DLL에는 다음과 같은 특징이 있습니다.  
  
-   이 DLL은 Visual C\+\+ 4.0에서 도입된 새로운 형식의 DLL입니다.  
  
-   C, C\+\+, 파스칼, Visual Basic 등 DLL 사용을 지원하는 모든 언어로 클라이언트 실행 파일을 만들 수 있으며 이 실행 파일은 MFC 응용 프로그램이 아니어도 됩니다.  
  
-   정적으로 링크되는 기본 DLL과 달리 이 형식의 DLL은 공유 MFC DLL이라고도 하는 MFC DLL에 동적으로 링크됩니다.  
  
-   이 형식의 DLL에 링크된 MFC 가져오기 라이브러리는 확장 DLL 또는 MFC DLL인 MFCxx\(D\).lib를 사용하는 응용 프로그램에 사용되는 것과 동일합니다.  
  
 동적으로 MFC에 링크되는 기본 DLL의 요구 사항은 다음과 같습니다.  
  
-   이 DLL은 동적으로 MFC DLL에 링크되는 실행 파일처럼 **\_AFXDLL**이 정의된 상태에서 컴파일됩니다.  그러나 정적으로 MFC에 링크되는 기본 DLL처럼 **\_USRDLL**도 정의됩니다.  
  
-   이 형식의 DLL에서는 `CWinApp` 파생 클래스를 인스턴스화해야 합니다.  
  
-   이 형식의 DLL에서는 MFC에서 제공하는 `DllMain`을 사용합니다.  따라서 일반적인 MFC 응용 프로그램과 마찬가지로 모든 DLL과 관련된 초기화 코드는 `InitInstance` 멤버 함수에, 종료 코드는 `ExitInstance`에 포함시켜야 합니다.  
  
 이러한 종류의 DLL은 MFC의 동적 연결 라이브러리 버전을 사용하기 때문에 명시적으로 현재 모듈 상태를 해당 DLL을 위한 것으로 설정해야 합니다.  이렇게 하려면 DLL에서 내보내는 모든 함수의 처음 부분에 [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md) 매크로를 사용해야 합니다.  
  
 기본 DLL에는 MFC 응용 프로그램과 마찬가지로, `CWinApp` 파생 클래스 및 해당 응용 프로그램 클래스의 단일 개체가 있어야 합니다.  그러나 응용 프로그램의 `CWinApp` 개체와 달리 DLL의 `CWinApp` 개체에는 기본 메시지 펌프가 없습니다.  
  
 응용 프로그램이 기본 메시지 펌프를 소유하고 있어 `CWinApp::Run` 메커니즘은 DLL에 적용되지 않습니다.  DLL이 모덜리스 대화 상자를 표시하거나 자체의 기본 프레임 창을 갖는 경우, 응용 프로그램의 기본 메시지 펌프는 `CWinApp::PreTranslateMessage`를 호출하는 DLL의 내보내는 루틴을 호출해야 합니다.  
  
 따라서 일반적인 MFC 응용 프로그램과 마찬가지로 모든 DLL과 관련된 초기화 코드를 `CWinApp::InitInstance` 멤버 함수에 포함시켜야 합니다.  `CWinApp` 파생 클래스의 `CWinApp::ExitInstance` 멤버 함수는 DLL이 언로드되기 전에 MFC에서 제공하는 `DllMain` 함수에서 호출됩니다.  
  
 공유 DLL인 MFCx0.dll Msvcr\*0.dll 등의 파일은 응용 프로그램과 함께 배포해야 합니다.  
  
 또한 동적으로 MFC에 링크되는 DLL이 정적으로 MFC에 링크될 수는 없습니다.  응용 프로그램에서는 다른 DLL과 마찬가지로, 동적으로 MFC에 링크되는 기본 DLL에 링크됩니다.  
  
 기호는 대개 표준 C 인터페이스를 사용하여 기본 DLL에서 내보내집니다.  기본 DLL에서 내보내기 함수의 선언 형식은 다음과 유사합니다.  
  
```  
extern "C" __declspec(dllexport) MyExportedFunction( );  
```  
  
 기본 DLL 내의 모든 메모리 할당은 DLL 내에 존재해야 하므로 DLL에서 다음 중 어떤 것도 호출 실행 파일에 전달하거나 호출 실행 파일로부터 받아서는 안 됩니다.  
  
-   MFC 개체에 대한 포인터  
  
-   MFC에서 할당한 메모리에 대한 포인터  
  
 위와 같은 작업이 필요하거나 호출 실행 파일과 DLL 사이에 MFC 파생 개체를 전달해야 하는 경우에는 확장 DLL을 빌드해야 합니다.  
  
 C 런타임 라이브러리에서 할당한 메모리에 대한 포인터는 해당 데이터의 복사본을 만들어야만 응용 프로그램과 DLL 간에 안전하게 전달됩니다.  이러한 포인터를 삭제하거나 크기를 변경하거나 사용하려면 반드시 메모리의 복사본을 만들어야 합니다.  
  
 동적으로 MFC에 링크하는 기본 DLL을 빌드할 때에는 [AFX\_MANAGE\_STATE](../Topic/AFX_MANAGE_STATE.md) 매크로를 사용하여 MFC 모듈 상태를 올바르게 전환해야 합니다.  DLL에서 내보낸 함수의 시작 부분에 다음과 같은 코드 행을 추가하여 이를 수행합니다.  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
 정적으로 MFC에 링크하는 기본 DLL이나 확장 DLL에 **AFX\_MANAGE\_STATE** 매크로를 사용해서는 안 됩니다.  자세한 내용은 [MFC 모듈의 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)를 참조하십시오.  
  
 기본 DLL의 작성, 빌드 및 사용 방법에 대한 예제를 보려면 [DLLScreenCap](http://msdn.microsoft.com/ko-kr/2171291d-3a50-403b-90a1-d93c2acb4f4a) 샘플을 참조하십시오.  동적으로 MFC에 링크하는 기본 DLL에 대한 자세한 내용은 이 샘플의 요약 부분에서 "DLLTRACE를 변환하여MFC DLL에 동적으로 링크" 단원을 참조하십시오.  
  
## 수행할 작업  
  
-   [기본 DLL 초기화](../build/initializing-regular-dlls.md)  
  
## 추가 정보  
  
-   [동적으로 MFC에 링크하는 기본 DLL의 모듈 상태](../build/module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)  
  
-   [MFC 모듈의 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [기본 DLL에서 데이터베이스, OLE 및 소켓 확장 DLL 사용](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [DLL의 일부로 MFC 사용](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
## 참고 항목  
 [DLL 종류](../build/kinds-of-dlls.md)