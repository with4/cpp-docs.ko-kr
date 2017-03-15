---
title: "방법: 64비트 플랫폼을 대상으로 한 Visual C++ 프로젝트 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "플랫폼[C++], 64비트"
  - "64비트 프로그래밍[C++], 프로젝트 구성"
  - "프로젝트 구성[C++]"
ms.assetid: 2b9ae001-df36-4750-83b2-982145d632ad
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 방법: 64비트 플랫폼을 대상으로 한 Visual C++ 프로젝트 구성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

64비트 플랫폼을 대상으로 하도록 C\+\+ 응용 프로그램을 설정하는 데 Visual Studio의 프로젝트 구성을 사용할 수 있습니다. 또한 Win32 프로젝트 설정을 64비트 프로젝트 구성에 마이그레이션할 수 있습니다.  
  
### 64비트 플랫폼을 대상으로 하도록 C\+\+ 응용 프로그램을 설정하려면  
  
1.  구성하려는 C\+\+ 프로젝트를 엽니다.  
  
2.  해당 프로젝트의 속성 페이지를 엽니다. 자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../misc/how-to-open-project-property-pages.md)을 참조하세요.  
  
    > [!NOTE]
    >  .NET 프로젝트의 경우 **구성 속성** 노드 또는 해당 자식 노드 중 하나가 **\<프로젝트 이름\> 속성 페이지** 대화 상자에서 선택되어 있는지 확인합니다. 선택되어 있지 않으면 **구성 관리자** 단추를 사용할 수 없습니다.  
  
3.  **구성 관리자** 단추를 선택하여 **구성 관리자** 대화 상자를 엽니다.  
  
4.  **활성 솔루션 플랫폼** 드롭다운 목록에서 **\<새로 만들기...\>** 옵션을 선택하여 **새 솔루션 플랫폼** 대화 상자를 엽니다.  
  
5.  **새 플랫폼 입력 또는 선택** 드롭다운 목록에서 64비트 플랫폼을 선택합니다.  
  
    > [!NOTE]
    >  **새 솔루션 플랫폼** 대화 상자에서 **다음에서 설정 복사** 옵션을 사용하여 기존 프로젝트 설정을 새 64비트 프로젝트 구성에 복사할 수 있습니다.  
  
6.  **확인** 단추를 선택합니다. 이전 단계에서 선택한 플랫폼이 **구성 관리자** 대화 상자의 **활성 솔루션 플랫폼** 아래에 표시됩니다.  
  
7.  **구성 관리자** 대화 상자에서 **닫기** 단추를 선택한 후 **\<프로젝트 이름\> 속성 페이지** 대화 상자에서 **확인** 단추를 선택합니다.  
  
### Win32 프로젝트 설정을 64비트 프로젝트 구성에 복사하려면  
  
-   64비트 플랫폼을 대상으로 하도록 프로젝트를 설정하는 동안 **새 솔루션 플랫폼** 대화 상자가 열리는 경우 **다음에서 설정 복사** 드롭다운 목록에서 **Win32**를 선택합니다. 다음 프로젝트 설정이 프로젝트 수준에서 자동으로 업데이트됩니다.  
  
    -   [\/MACHINE](../build/reference/machine-specify-target-platform.md) 링커 옵션이 **\/MACHINE:X64**로 설정됩니다.  
  
    -   **출력 등록**이 꺼집니다. 자세한 내용은 [링커 속성 페이지](../ide/linker-property-pages.md)을 참조하세요.  
  
    -   **대상 환경**이 **\/env x64**로 설정됩니다. 자세한 내용은 [MIDL 속성 페이지: 일반](../ide/midl-property-pages-general.md)을 참조하세요.  
  
    -   **매개 변수 유효성 검사**가 초기화되어 기본값으로 다시 설정됩니다. 자세한 내용은 [MIDL 속성 페이지: 고급](../ide/midl-property-pages-advanced.md)을 참조하세요.  
  
    -   **디버그 정보 형식**이 Win32 프로젝트 구성에서 **\/ZI**로 설정되면 64비트 프로젝트 구성에서는 **\/Zi**로 설정됩니다. 자세한 내용은 [\/Z7, \/Zi, \/ZI\(디버깅 정보 형식\)](../build/reference/z7-zi-zi-debug-information-format.md)을 참조하세요.  
  
    > [!NOTE]
    >  이러한 프로젝트 속성이 파일 수준에서 재정의된 경우에는 어떠한 속성도 변경되지 않습니다.  
  
## 참고 항목  
 [64비트 응용 프로그램](../Topic/64-bit%20Applications.md)   
 [64비트용 프로그램 구성](../build/configuring-programs-for-64-bit-visual-cpp.md)   
 [64비트 응용 프로그램 디버그](../Topic/Debug%2064-Bit%20Applications.md)