---
title: "동적으로 MFC에 링크하는 기본 DLL의 모듈 상태 | Microsoft Docs"
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
  - "DLL[C++], 모듈 상태"
  - "MFC DLL[C++], 기본 DLL"
  - "모듈 상태[C++]"
  - "모듈 상태[C++], 동적으로 연결된 기본 DLL"
  - "기본 DLL[C++], MFC에 동적 연결"
ms.assetid: b4493e79-d25e-4b7f-a565-60de5b32c723
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 동적으로 MFC에 링크하는 기본 DLL의 모듈 상태
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본 DLL을 MFC DLL에 동적으로 링크시키는 기술을 사용하면 매우 복잡한 구성도 가능해집니다.  예를 들어, 기본 DLL과 이 기본 DLL을 사용하는 실행 파일이 모두 MFC DLL 및 확장 DLL에 동적으로 링크할 수 있습니다.  
  
 이 구성에는 현재 `CWinApp` 개체와 핸들 맵에 대한 포인터 같은 MFC 전역 데이터와 관련된 문제가 있습니다.  
  
 MFC 버전 4.0 이전에는 이러한 전역 데이터가 MFC DLL 내에 상주했으며 프로세스의 모든 모듈에서 공유되었습니다.  Win32 DLL을 사용하는 각 프로세스에는 DLL 데이터의 고유한 사본이 있으므로 이 체계를 통해 프로세스별 데이터를 쉽게 추적할 수 있었습니다.  또한 AFXDLL 모델에서는 `CWinApp` 개체가 하나만 있고 프로세스에 핸들 맵 집합이 하나만 있는 것으로 가정했으므로 MFC DLL 자체에서 이러한 항목을 추적할 수 있었습니다.  
  
 그러나 이제는 기본 DLL을 MFC DLL에 동적으로 링크시키는 기술을 사용함으로써 하나의 프로세스에 여러 `CWinApp` 개체와 여러 핸들 맵 집합이 있을 수 있습니다.  따라서 MFC는 사용할 개체 및 핸들 맵 집합을 추적해야 하는 문제가 발생합니다.  
  
 이에 대한 해결책은 각 모듈\(응용 프로그램 또는 기본 DLL\)마다 이 전역 상태 정보의 복사본을 별도로 제공하는 것입니다.  따라서 기본 DLL에 있는 **AfxGetApp**를 호출하면 실행 파일이 아니라 해당 DLL에 있는 `CWinApp` 개체에 대한 포인터를 반환하게 됩니다.  이 MFC 전역 데이터의 모듈별 복사본을 모듈 상태라고 합니다. 자세한 내용은 [MFC Tech Note 58](../mfc/tn058-mfc-module-state-implementation.md)을 참조하십시오.  
  
 MFC 공용 창 프로시저는 자동으로 올바른 모듈 상태로 전환하므로 사용자가 기본 DLL에 구현된 메시지 처리기에서 이에 대해 신경 쓸 필요는 없습니다.  그러나 실행 파일이 기본 DLL 안으로 호출되는 경우에는 현재 모듈 상태를 해당 DLL을 위한 상태로 명시적으로 설정해야 합니다.  이렇게 하려면 DLL에서 내보내는 모든 함수에 **AFX\_MANAGE\_STATE** 매크로를 사용해야 합니다.  DLL에서 내보낸 함수의 시작 부분에 다음과 같은 코드 행을 추가하여 이를 수행합니다.  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
## 추가 정보  
  
-   [MFC 모듈의 상태 데이터 관리](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [동적으로 MFC에 링크하는 기본 DLL](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [확장 DLL](../build/extension-dlls-overview.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)