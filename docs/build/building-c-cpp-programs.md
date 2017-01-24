---
title: "C/C++ 프로그램 빌드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vcbuilding"
  - "buildingaprogramVC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "빌드[C++]"
  - "빌드[C++], 옵션"
  - "프로젝트[C++], 빌드"
  - "Visual C++ 프로젝트, 빌드"
  - "Visual C++, 빌드 옵션"
ms.assetid: fa6ed4ff-334a-4d99-b5e2-a1f83d2b3008
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C/C++ 프로그램 빌드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio 또는 명령줄에서 Visual C\+\+ 프로젝트를 빌드할 수 있습니다.  Visual Studio IDE는 [MSBuild](../build/msbuild-visual-cpp.md)를 사용하여 프로젝트와 솔루션을 빌드합니다.  명령줄에서는 C\/C\+\+ 컴파일러\(cl.exe\) 및 링커\(link.exe\)를 사용하여 간단한 프로젝트를 빌드할 수 있습니다.  명령줄에서 보다 복잡한 프로젝트를 빌드하려는 경우 MSBuild 또는 [NMAKE](../build/nmake-reference.md)를 사용할 수 있습니다.  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]를 사용하여 프로젝트와 솔루션을 빌드하는 방법의 개요는 [Visual Studio에서 응용 프로그램　빌드](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)를 참조하세요.  
  
## 단원 내용  
 [Visual Studio에서 C\+\+ 프로젝트 빌드](../ide/building-cpp-projects-in-visual-studio.md)  
 Visual Studio IDE를 사용하여 C\/C\+\+ 프로젝트를 빌드하는 방법을 설명합니다.  
  
 [명령줄 빌드](../build/building-on-the-command-line.md)  
 Visual Studio에 포함된 C\/C\+\+ 명령줄 컴파일러 및 빌드 도구를 사용하는 방법을 설명합니다.  
  
 [C\/C\+\+ 격리된 응용 프로그램 및 side\-by\-side 어셈블리 빌드](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
 격리된 응용 프로그램 및 side\-by\-side 어셈블리 아이디어를 기반으로 하는 Windows 데스크톱 응용 프로그램의 배포 모델에 대해 설명합니다.  
  
 [C\/C\+\+ 빌드 참조](../build/reference/c-cpp-building-reference.md)  
 C\+\+, 컴파일러\/링커 옵션 및 다양한 빌드 도구를 사용한 프로그램 빌드와 관련된 참조 문서의 링크를 제공합니다.  
  
 [64비트용 프로그램 구성](../build/configuring-programs-for-64-bit-visual-cpp.md)  
 Visual Studio와 명령줄이 모두 64비트 도구 집합을 사용하도록 구성하는 방법과 64비트 아키텍처를 대상으로 지정하는 방법 그리고 코드를 64비트 아키텍처로 이동할 때 일반적으로 발생하는 마이그레이션 문제에 대해 설명합니다.  
  
 [ARM 프로세서용 프로그램 구성](../build/configuring-programs-for-arm-processors-visual-cpp.md)  
 ARM 프로세서에서 사용하는 규칙과 코드를 ARM 아키텍처로 이동할 때 일반적으로 발생하는 마이그레이션 문제에 대해 설명합니다.  
  
 [Windows XP용 C\+\+ 11 프로그램 구성](../build/configuring-programs-for-windows-xp.md)  
 Windows XP 개발을 대상으로 하도록 플랫폼 도구 집합을 설정하는 방법을 설명합니다.  
  
## 관련 단원  
 [NIB: Samples Included in Visual C\+\+](http://msdn.microsoft.com/ko-kr/c9ec56b3-2bbd-49b4-8a4c-9ed4b78b7a84)  
 Visual C\+\+ 및 Visual C\+\+가 지원하는 라이브러리와 기술의 기능을 보여주는 샘플 코드에 대한 링크를 제공합니다.  
  
 [Visual Studio에서 응용 프로그램　빌드](../Topic/Compiling%20and%20Building%20in%20Visual%20Studio.md)  
 Visual Studio 빌드 시스템 및 도구에 대해 설명합니다.