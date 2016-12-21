---
title: "기본 DLL 초기화 | Microsoft Docs"
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
  - "DLL 초기화"
  - "기본 DLL[C++], 초기화"
ms.assetid: f1f091d1-bb91-468a-94f4-3c554657b8fc
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 기본 DLL 초기화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본 DLL에는 `CWinApp` 개체가 있기 때문에 MFC 응용 프로그램과 같은 위치\(DLL에 포함된 `CWinApp` 파생 클래스의 `InitInstance` 및 **ExitInstance** 멤버 함수\)에서 초기화 및 종료 작업을 수행해야 합니다.  MFC는 **\_DllMainCRTStartup**에서 **PROCESS\_ATTACH** 및 **PROCESS\_DETACH**에 대해 호출되는 `DllMain` 함수를 제공하므로 사용자가 직접 `DllMain` 함수를 작성해서는 안 됩니다.  MFC에서 제공하는 `DllMain` 함수는 DLL이 로드될 때 `InitInstance`를 호출하고, DLL이 언로드되기 전에 `ExitInstance`를 호출합니다.  
  
 기본 DLL은 해당 `InitInstance` 함수에서 [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) 및 [TlsGetValue](http://msdn.microsoft.com/library/windows/desktop/ms686812)를 호출하여 여러 스레드를 추적할 수 있습니다.  또한 DLL은 이 함수를 이용하여 스레드별 데이터를 추적할 수 있습니다.  
  
 동적으로 MFC에 링크하는 기본 DLL에서 MFC OLE, MFC 데이터베이스\(또는 DAO\) 또는 MFC 소켓이 지원되는 경우에는 각각 MFC 디버그 확장 DLL인 MFCOxxD.dll, MFCDxxD.dll 및 MFCNxxD.dll\(xx는 버전 번호\)이 자동으로 링크됩니다.  기본 DLL의 `CWinApp::InitInstance`에서 사용되는 각각의 DLL에 대해 다음과 같은 미리 정의된 초기화 함수 중 하나를 호출해야 합니다.  
  
|MFC 지원 종류|호출할 초기화 함수|  
|---------------|----------------|  
|MFC OLE\(MFCOxxD.dll\)|`AfxOleInitModule`|  
|MFC 데이터베이스\(MFCDxxD.dll\)|`AfxDbInitModule`|  
|MFC 소켓\(MFCNxxD.dll\)|`AfxNetInitModule`|  
  
## 수행할 작업  
  
-   [확장 DLL 초기화](../build/initializing-extension-dlls.md)  
  
-   [비 MFC DLL 초기화](../build/initializing-non-mfc-dlls.md)  
  
## 추가 정보  
  
-   [C 런타임 라이브러리 동작 및 \_DllMainCRTStartup](../build/run-time-library-behavior.md)  
  
-   [기본 DLL에서 데이터베이스, OLE 및 소켓 확장 DLL 사용](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [\<caps:sentence id\="tgt22" sentenceid\="704731be78a1b2b43311fed62656e454" class\="tgtSentence"\>Processes and threads \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms684841)  
  
-   [스레드 로컬 저장소 래퍼\(MFC Technical Note 58\)](../mfc/tn058-mfc-module-state-implementation.md)  
  
## 참고 항목  
 [DLL 초기화](../build/initializing-a-dll.md)