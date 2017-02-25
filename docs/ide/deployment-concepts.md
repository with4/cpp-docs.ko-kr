---
title: "배포 개념 | Microsoft Docs"
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
  - "응용 프로그램 배포[C++], 응용 프로그램 배포 정보"
  - "종속성[C++], 응용 프로그램 배포"
  - "응용 프로그램 배포[C++], 응용 프로그램 배포 정보"
  - "라이브러리[C++], 응용 프로그램 배포 문제"
  - "Windows Installer[C++]"
ms.assetid: ebd7f246-ab54-40e8-87fa-dac02c0047b3
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 배포 개념
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 단원에서는 C\+\+ 응용 프로그램 배포의 주요 고려 사항에 대해 설명합니다.  
  
## C\+\+에서 Windows Installer 배포  
 일반적으로 Visual C\+\+ 프로젝트에서는 기존 Windows Installer 설치를 사용하여 배포합니다.  Windows Installer 배포를 준비하려면 응용 프로그램을 setup.exe 파일에 패키지하고 이 파일을 설치 관리자 패키지\(.msi\)와 함께 배포합니다.  그러면 사용자는 setup.exe를 실행하여 응용 프로그램을 설치합니다.  
  
 솔루션에 설치 프로젝트를 추가하여 응용 프로그램을 패키지할 수 있습니다. 이 프로젝트를 빌드하면 사용자에게 배포할 설치 및 설치 관리자 패키지 파일이 만들어집니다.  자세한 내용은 [배포 방법 선택](../ide/choosing-a-deployment-method.md)을 참조하십시오.  
  
## 라이브러리 종속성  
 Visual C\+\+ 라이브러리에서 제공하는 기능을 사용하여 C\/C\+\+ 응용 프로그램이 빌드되면 런타임에 이들 라이브러리가 있어야 한다는 종속성이 생깁니다.  응용 프로그램을 실행하려면 응용 프로그램에서 필요한 Visual C\+\+ 라이브러리에 정적 또는 동적으로 링크해야 합니다.  응용 프로그램에서 Visual C\+\+ 라이브러리에 동적으로 링크하는 경우 응용 프로그램이 실행될 때 라이브러리를 로드할 수 있도록 라이브러리가 존재해야 합니다.  반면 응용 프로그램에서 Visual C\+\+ 라이브러리에 정적으로 링크하는 경우 사용자 컴퓨터에 해당 DLL이 존재하지 않아도 됩니다.  그러나 정적 링크에는 응용 프로그램 파일 크기 증가 및 유지 보수의 어려움과 같은 몇 가지 단점이 있습니다.  자세한 내용은 [DLL 사용의 장점](../build/advantages-of-using-dlls.md)을 참조하십시오.  
  
## 패키징 및 재배포  
 Visual C\+\+ 라이브러리는 DLL로 패키지되고, Visual Studio에서는 개발자의 컴퓨터에 C\/C\+\+ 응용 프로그램에 필요한 모든 라이브러리를 설치합니다.  그러나 사용자에게 응용 프로그램을 배포할 때 응용 프로그램을 실행하기 위해 사용자가 Visual Studio를 설치하도록 하는 것은 대부분의 경우 적합하지 않습니다.  따라서 응용 프로그램을 제대로 실행하기 위해 필요한 Visual C\+\+의 해당 부분만 재배포하는 것이 중요합니다.  
  
 패키징 및 재배포에 대한 자세한 내용은 다음 항목을 참조하십시오.  
  
-   [재배포할 DLL 확인](../ide/determining-which-dlls-to-redistribute.md).  
  
-   [배포 방법 선택](../ide/choosing-a-deployment-method.md).  
  
 문제 해결에 대한 예제 및 해결 방법은 다음을 참조하십시오.  
  
-   [배포 예제](../ide/deployment-examples.md).  
  
-   [문제 해결](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
## 참고 항목  
 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Visual C\+\+ 응용 프로그램의 종속성 이해](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)   
 [Windows Installer Deployment](http://msdn.microsoft.com/ko-kr/121be21b-b916-43e2-8f10-8b080516d2a0)