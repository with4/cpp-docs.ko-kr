---
title: "강력한 이름 어셈블리(어셈블리 서명)(C++/CLI) | Microsoft Docs"
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
  - ".NET Framework[C++], 어셈블리 서명"
  - "어셈블리[C++]"
  - "어셈블리[C++], 서명"
  - "링커[C++], 어셈블리 서명"
  - "어셈블리 서명"
  - "강력한 이름의 어셈블리[C++]"
ms.assetid: c337cd3f-e5dd-4c6f-a1ad-437e85dba1cc
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 강력한 이름 어셈블리(어셈블리 서명)(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 어셈블리에 서명하는 방법을 보여 줍니다. 이를 가리켜 어셈블리에 강력한 이름을 부여한다고도 합니다.  
  
## 설명  
 Visual C\+\+를 사용하는 경우 링커 옵션을 통해 어셈블리에 서명하면 어셈블리에 서명하는 CLR 특성과 관련된 문제를 해결할 수 있습니다.  
  
-   <xref:System.Reflection.AssemblyDelaySignAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyFileAttribute>  
  
-   <xref:System.Reflection.AssemblyKeyNameAttribute>  
  
 특성을 사용하면 안 되는 이유 중 하나는 키 이름이 어셈블리 메타데이터에 표시되므로 파일 이름에 기밀 정보가 포함되는 경우 보안상 위험할 수 있기 때문입니다.  또한 CLR 특성을 사용하여 어셈블리에 강력한 이름을 지정하는 경우 Visual C\+\+ 개발 환경에서 사용하는 빌드 과정에서는 어셈블리가 서명된 키를 무효화한 다음 어셈블리에 대해 mt.exe와 같은 사후 처리 도구를 실행합니다.  
  
 명령줄에서 빌드하고, 링커 옵션을 사용하여 어셈블리에 서명한 다음 mt.exe와 같은 사후 처리 도구를 실행하는 경우 sn.exe를 사용하여 어셈블리에 다시 서명해야 합니다.  또는 어셈블리를 빌드하고 서명을 연기한 다음 사후 처리 도구를 실행한 후 서명을 완료할 수도 있습니다.  
  
 개발 환경에서 빌드할 때 서명 특성을 사용하는 경우 빌드 후 이벤트에서 sn.exe\([Sn.exe\(강력한 이름 도구\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)\)를 명시적으로 호출하는 방법으로 어셈블리에 서명할 수 있습니다.  자세한 내용은 [빌드 이벤트 지정](../ide/specifying-build-events.md)을 참조하십시오.  특성 및 빌드 후 이벤트를 사용하면 링커 옵션을 사용하는 경우보다 빌드 시간이 단축될 수 있습니다.  
  
 어셈블리 서명을 지원하는 링커 옵션은 다음과 같습니다.  
  
-   [\/DELAYSIGN\(어셈블리에 부분적으로 서명\)](../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYFILE\(어셈블리에 서명할 키 또는 키 쌍 지정\)](../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER\(어셈블리에 서명할 키 컨테이너 지정\)](../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
 강력한 이름의 어셈블리에 대한 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md)을 참조하십시오.  
  
## 참고 항목  
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)