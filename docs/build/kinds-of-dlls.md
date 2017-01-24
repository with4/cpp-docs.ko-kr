---
title: "DLL 종류 | Microsoft Docs"
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
  - "DLL[C++], MFC"
  - "DLL[C++], 형식"
  - "MFC DLL[C++], 형식"
ms.assetid: f6a30db9-6138-4b2c-90cc-a17855e499a6
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# DLL 종류
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 항목에서는 빌드할 DLL의 종류를 결정하는 데 유용한 정보가 제공됩니다.  
  
##  <a name="_core_the_different_kinds_of_dlls_available_with_visual_c.2b2b"></a> 사용 가능한 DLL의 여러 가지 종류  
 Visual C\+\+에서는 MFC\(Microsoft Foundation Class\) 라이브러리를 사용하지 않는 Win32 DLL을 C 또는 C\+\+로 빌드할 수 있습니다.  이러한 비 MFC DLL 프로젝트는 Win32 응용 프로그램 마법사를 사용하여 만들 수 있습니다.  
  
 MFC 라이브러리 자체는 MFC DLL 마법사를 사용하여 정적 연결 라이브러리나 여러 DLL에서 사용할 수 있습니다.  사용자 DLL에서 MFC를 사용하는 경우, Visual C\+\+에서는 다음과 같은 세 가지의 DLL 개발 시나리오를 지원합니다.  
  
-   정적으로 MFC를 링크하는 기본 DLL 빌드  
  
-   동적으로 MFC에 링크하는 기본 DLL 빌드  
  
-   MFC에 항상 동적으로 링크하는 MFC 확장 DLL 빌드  
  
### 추가 정보  
  
-   [비 MFC DLL: 개요](../build/non-mfc-dlls-overview.md)  
  
-   [정적으로 MFC에 링크된 기본 DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [동적으로 MFC에 링크하는 기본 DLL](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [확장 DLL: 개요](../build/extension-dlls-overview.md)  
  
-   [사용할 DLL 종류 결정](#_core_which_kind_of_dll_to_use)  
  
##  <a name="_core_which_kind_of_dll_to_use"></a> 사용할 DLL 종류 결정  
 MFC를 사용하지 않는 DLL의 경우에는 Visual C\+\+를 사용하여 비 MFC Win32 DLL을 빌드할 수 있습니다.  정적 또는 동적으로 DLL을 MFC에 링크하면 디스크 공간 및 메모리를 많이 소모하게 됩니다.  따라서 DLL이 실제로 MFC를 사용하지 않는 경우에는 MFC에 링크하지 말아야 합니다.  
  
 MFC를 사용하는 DLL을 MFC 응용 프로그램 또는 비 MFC 응용 프로그램에서 사용하는 경우 동적으로 MFC에 링크하는 기본 DLL이나 정적으로 MFC에 링크하는 기본 DLL을 빌드해야 합니다.  대부분의 경우, 동적으로 MFC에 링크하는 기본 DLL을 사용하면 파일 크기도 훨씬 작고 MFC의 공유 버전을 사용함으로써 메모리 부담도 상당히 줄일 수 있습니다.  정적으로 MFC에 링크하면 해당 DLL만을 위한 MFC 라이브러리 코드의 복사본이 별도로 로드되므로 DLL의 파일 크기가 더 커질 뿐만 아니라 메모리도 많이 사용하게 됩니다.  
  
 동적으로 MFC에 링크한 DLL은 MFC를 직접 링크할 필요가 없으므로 정적으로 MFC에 링크한 DLL보다 빠르게 빌드할 수 있습니다.  빌드 속도는 링커가 디버그 정보를 압축해야 하는 디버그 빌드에서 특히 빠릅니다.  즉, 디버그 정보가 이미 들어 있는 DLL에 링크하므로 프로그램의 DLL 내에 압축해야 할 디버그 정보가 줄어듭니다.  
  
 MFC에 동적으로 링크할 경우의 한 가지 단점은 공유 DLL인 DLLs Mfcx0.dll과 Msvcrxx.dll 등의 파일을 프로그램의 DLL과 함께 배포해야 한다는 점입니다.  MFC DLL은 얼마든지 재배포할 수 있지만 항상 설치 프로그램에서 설치되어야 합니다.  또한 프로그램과 MFC DLL에서 모두 사용되는 C 런타임 라이브러리를 포함한 Msvcrxx.dll을 제공해야 합니다.  
  
 DLL을 MFC 실행 파일에서만 사용하는 경우에는 기본 DLL을 빌드할 수도 있고 확장 DLL을 빌드할 수도 있습니다.  DLL이 기존의 MFC 클래스에서 파생된 다시 사용할 수 있는 클래스를 구현하는 경우나 응용 프로그램과 DLL 간에 MFC 파생 개체를 전달해야 하는 경우에는 확장 DLL을 빌드해야 합니다.  
  
 동적으로 DLL을 MFC에 링크하는 경우에는 MFC DLL을 이 DLL과 함께 재배포할 수 있습니다.  이러한 아키텍처는 디스크 공간을 절약하고 메모리 사용량을 최소화하기 위해 여러 실행 파일 간에 클래스 라이브러리를 공유하는 데 특히 유용합니다.  
  
 버전 4.0 이전의 Visual C\+\+에서는 MFC를 사용하는 두 가지 종류의 DLL\(USRDLL 및 AFXDLL\)만 지원했습니다.  정적으로 MFC에 링크된 기본 DLL은 이전의 USRDLL과 같은 특징을 갖습니다.  또한 MFC 확장 DLL은 이전의 AFXDLL과 같은 특징을 갖습니다.  
  
### 추가 정보  
  
-   [비 MFC DLL: 개요](../build/non-mfc-dlls-overview.md)  
  
-   [정적으로 MFC에 링크된 기본 DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [동적으로 MFC에 링크하는 기본 DLL](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [확장 DLL: 개요](../build/extension-dlls-overview.md)  
  
## 참고 항목  
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)