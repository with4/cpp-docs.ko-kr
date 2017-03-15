---
title: "DLL 초기화 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL[C++], 초기화"
  - "DLL 초기화"
  - "종료 코드[C++]"
ms.assetid: f655c5ff-ab5b-493a-a1da-4d1074e60c5b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# DLL 초기화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

일반적으로 DLL에는 해당 DLL이 로드될 때 실행되어야 하는 메모리 할당과 같은 초기화 코드가 있습니다.  Visual C\+\+를 사용하는 경우 DLL의 초기화 코드를 추가하는 위치는 빌드하는 DLL의 형식에 따라 다릅니다.  초기화 및 종료 코드를 추가할 필요가 없으면 DLL을 빌드할 때 별도의 작업을 수행하지 않아도 됩니다.  다음 표에서는 DLL을 초기화해야 하는 경우 코드를 추가할 위치에 대해 설명합니다.  
  
|DLL 형식|초기화 및 종료 코드를 추가하는 위치|  
|------------|--------------------------|  
|기본 DLL|DLL에 포함된 `CWinApp` 개체의 `InitInstance` 및 `ExitInstance`|  
|확장 DLL|MFC DLL 마법사에 의해 생성되는 `DllMain` 함수|  
|비 MFC DLL|사용자가 제공하는 `DllMain`이라는 함수|  
  
 Win32에서 모든 DLL에는 초기화 및 종료 시 모두 호출되는 선택적 진입점 함수가 포함될 수 있으며, 이 함수를 대개 `DllMain`이라고 합니다.  이 함수가 포함되면 필요할 때 추가 리소스를 할당하거나 해제할 수 있습니다.  Windows는 프로세스 연결, 프로세스 분리, 스레드 연결 및 스레드 분리의 네 가지 경우 진입점 함수를 호출합니다.  
  
 C 런타임 라이브러리에서는 **\_DllMainCRTStartup**이라는 진입점 함수를 제공하여 `DllMain`을 호출합니다.  DLL의 형식에 따라 소스 코드에 `DllMain`이라는 함수를 포함시키거나 MFC 라이브러리에서 제공하는 `DllMain`을 사용해야 합니다.  
  
## 수행할 작업  
  
-   [기본 DLL 초기화](../build/initializing-regular-dlls.md)  
  
-   [확장 DLL 초기화](../build/initializing-extension-dlls.md)  
  
-   [비 MFC DLL 초기화](../build/initializing-non-mfc-dlls.md)  
  
## 추가 정보  
  
-   [C 런타임 라이브러리 동작 및 \_DllMainCRTStartup](../build/run-time-library-behavior.md)  
  
-   [\<caps:sentence id\="tgt24" sentenceid\="58bb7328659bda9ffb73a1dcd39da06b" class\="tgtSentence"\>The function specification for DllMain \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682583)  
  
-   [\<caps:sentence id\="tgt25" sentenceid\="f29344705c59343b34b642944921cbdf" class\="tgtSentence"\>Dynamic\-link library entry\-point function\(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682596)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)