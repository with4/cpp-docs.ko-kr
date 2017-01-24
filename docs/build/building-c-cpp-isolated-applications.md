---
title: "C/C++ 격리된 응용 프로그램 빌드 | Microsoft Docs"
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
  - "격리된 응용 프로그램[C++]"
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C/C++ 격리된 응용 프로그램 빌드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

격리된 응용 프로그램은 side\-by\-side 어셈블리에만 의존하며 매니페스트를 사용하여 해당 종속 파일에 바인딩됩니다.  응용 프로그램이 완전히 격리되어야 Windows에서 제대로 실행되는 것은 아니지만, 응용 프로그램을 완전히 격리하면 나중에 응용 프로그램을 유지 관리해야 하는 경우 시간을 절약할 수 있습니다.  응용 프로그램을 완전히 격리할 경우의 이점에 대한 자세한 내용은 [Isolated Applications](http://msdn.microsoft.com/library/aa375190)를 참조하십시오.  
  
 Visual C\+\+를 사용하여 네이티브 C\/C\+\+ 응용 프로그램을 빌드하는 경우 Visual Studio 프로젝트 시스템에서는 기본적으로 Visual C\+\+ 라이브러리에 대한 응용 프로그램의 종속성을 설명하는 매니페스트 파일을 생성합니다.  이를 제외한 다른 종속성이 응용 프로그램에 없는 경우 Visual Studio를 사용하여 다시 빌드하는 즉시 응용 프로그램이 격리됩니다.  응용 프로그램이 런타임에 다른 라이브러리를 사용하는 경우 [C\/C\+\+ side\-by\-side 어셈블리 빌드](../build/building-c-cpp-side-by-side-assemblies.md)에서 설명하는 단계에 따라 이러한 라이브러리를 side\-by\-side 어셈블리로 다시 빌드해야 할 수도 있습니다.  
  
## 참고 항목  
 [격리된 응용 프로그램 및 side\-by\-side 어셈블리 개념](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C\/C\+\+ 격리된 응용 프로그램 및 side\-by\-side 어셈블리 빌드](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)