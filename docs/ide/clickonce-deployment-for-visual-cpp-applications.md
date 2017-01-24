---
title: "Visual C++ 응용 프로그램의 ClickOnce 배포 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "응용 프로그램 배포[C++], ClickOnce"
  - "응용 프로그램 배포[C++], ClickOnce"
  - "ClickOnce 배포[C++], C++ 응용 프로그램"
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual C++ 응용 프로그램의 ClickOnce 배포
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에서는 Windows 응용 프로그램을 배포하기 위한 두 가지 방법으로 ClickOnce 배포 및 [Windows Installer](http://msdn.microsoft.com/library/cc185688) 배포 기술을 제공합니다.  
  
## C\+\+의 ClickOnce 배포  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 배포 환경에서는 [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)]를 사용하여 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 프로젝트를 배포하는 방법을 직접 지원하지 않지만 적절한 도구를 사용하면 이 방식으로 배포할 수 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]는 [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../Token/vbprvb_md.md)] 배포 환경에서 [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)]를 지원하지 않습니다.  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 프로젝트가 [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)] 프로젝트에 종속되어 있는 경우 [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)] 배포 환경에서 [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] 배포를 사용하여 응용 프로그램과 해당 종속 파일을 게시할 수 있습니다.  
  
 [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)]를 사용하여 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 응용 프로그램을 배포하려면 먼저 [Mage.exe\(매니페스트 생성 및 편집 도구\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md) 또는 이 도구의 그래픽 사용자 인터페이스 버전을 사용하여 [ClickOnce 응용 프로그램 매니페스트](../Topic/ClickOnce%20Application%20Manifest.md) 및 [ClickOnce 배포 매니페스트](../Topic/ClickOnce%20Deployment%20Manifest.md)를 빌드해야 합니다. 자세한 내용은 [MageUI.exe \(매니페스트 생성 및 편집 도구, 그래픽 클라이언트\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)를 참조하십시오.  
  
 우선 Mage.exe를 사용하여 응용 프로그램 매니페스트를 빌드합니다. 그 결과로 생성되는 파일의 확장명은 .manifest입니다.  그런 다음 Mage.exe를 사용하여 배포 매니페스트를 빌드합니다. 그 결과로 생성되는 파일의 확장명은 .application입니다.  마지막으로 매니페스트에 서명합니다.  
  
 응용 프로그램 매니페스트는 대상 프로세서\(**x86**, **x64** 또는 **ARM**\)를 지정해야 합니다.  이러한 옵션에 대한 자세한 내용은 [64비트 응용 프로그램의 필수 구성 요소 배포](../Topic/Deploying%20Prerequisites%20for%2064-bit%20Applications.md)를 참조하십시오.  
  
 또한 응용 프로그램 및 배포 매니페스트의 이름은 C\+\+ 응용 프로그램의 이름과 달라야 합니다.  이는 Mage.exe에서 만든 응용 프로그램 매니페스트와 C\+\+ 응용 프로그램의 일부인 외부 매니페스트 사이에 충돌이 발생하지 않도록 하기 위한 것입니다.  
  
 응용 프로그램을 배포하려면 응용 프로그램에 사용되는 모든 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 라이브러리를 설치해야 합니다.  \/DEPENDENTS 옵션을 지정하여 DUMPBIN 유틸리티를 사용하거나 depends.exe를 사용하면 특정 응용 프로그램에 대한 종속성을 확인할 수 있습니다.  종속성에 대한 자세한 내용은 [Visual C\+\+ 응용 프로그램의 종속성 이해](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)를 참조하십시오.  VCRedist.exe를 실행해야 할 수도 있습니다. 이 유틸리티는 대상 컴퓨터에 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 라이브러리를 설치합니다.  
  
 필수 구성 요소를 배포하기 위해 응용 프로그램의 부트스트래퍼\(필수 구성 요소 설치 관리자\)를 빌드해야 할 수도 있습니다. 부트스트래퍼에 대한 자세한 내용은 [부트스트래퍼 패키지 만들기](../Topic/Creating%20Bootstrapper%20Packages.md)를 참조하십시오.  
  
 배포 방법에 대한 자세한 내용은 [ClickOnce 보안 및 배포](../Topic/ClickOnce%20Security%20and%20Deployment.md)를 참조하십시오.  [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] 배포 방법의 자세한 예제는 [연습: ClickOnce 응용 프로그램 수동 배포](../Topic/Walkthrough:%20Manually%20Deploying%20a%20ClickOnce%20Application.md)를 참조하십시오.  
  
## 참고 항목  
 [Mage.exe\(매니페스트 생성 및 편집 도구\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md)   
 [MageUI.exe \(매니페스트 생성 및 편집 도구, 그래픽 클라이언트\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)   
 [Makecert.exe\(인증서 작성 도구\)](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md)   
 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [응용 프로그램, 서비스 및 구성 요소 배포](../Topic/Deploying%20Applications,%20Services,%20and%20Components.md)   
 [Windows Installer Deployment](http://msdn.microsoft.com/ko-kr/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [ClickOnce 보안 및 배포](../Topic/ClickOnce%20Security%20and%20Deployment.md)   
 [부트스트래퍼 패키지 만들기](../Topic/Creating%20Bootstrapper%20Packages.md)   
 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [네이티브 및 .NET 상호 운용성](../dotnet/native-and-dotnet-interoperability.md)