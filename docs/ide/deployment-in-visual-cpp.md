---
title: "Visual C++의 개발 | Microsoft Docs"
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
  - "응용 프로그램 배포[C++]"
  - "응용 프로그램 배포[C++]"
ms.assetid: d4b4ffc0-d2bd-4e4a-84a6-62f1c26f6a09
caps.latest.revision: 21
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Visual C++의 개발
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다른 컴퓨터에 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 응용 프로그램을 배포할 때는 응용 프로그램과 해당 응용 프로그램이 종속된 모든 라이브러리 파일을 설치해야 합니다.  보안 취약점이 해결되는 등 라이브러리가 업데이트되면 응용 프로그램이 배포될 때마다 업데이트를 적용할 수 있습니다.  
  
 Visual Studio는 세 가지 방법\(중앙 배포, 로컬 배포 및 정적 연결\)으로 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 라이브러리를 응용 프로그램과 함께 배포할 수 있습니다.  Microsoft는 중앙 배포된 라이브러리를 자동으로 업데이트합니다.  로컬 배포 또는 정적 링크 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 라이브러리의 경우 응용 프로그램 작성자가 업데이트를 제공해야 합니다.  
  
## 중앙 배포  
 중앙 배포의 경우 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 라이브러리 파일이 %windir%\\system32\\ 디렉터리에 설치됩니다.  [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 라이브러리를 중앙 배포하려면 다음 중 하나를 사용할 수 있습니다.  
  
-   *재배포 가능 패키지 파일*. [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 재배포 가능 라이브러리 설치에 사용할 수 있는 독립 실행형 명령줄 실행 파일입니다.  
  
-   *재배포 가능 병합 모듈\(.msm 파일\)*. 특정 라이브러리 배포에 사용할 수 있고 응용 프로그램의 Windows Installer\(.msi\) 파일에 포함하는 파일입니다.  
  
 재배포 가능 패키지 파일은 특정 시스템 아키텍처에 대해 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 라이브러리를 설치합니다.  응용 프로그램 설치를 프로그래밍하여 응용 프로그램을 설치하기 전에 필수 구성 요소로 실행할 수 있습니다.  병합 모듈을 사용하면 Windows Installer 응용 프로그램 설치 파일의 특정 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 라이브러리에 대한 설치 논리를 포함할 수 있습니다.  응용 프로그램에 필요한 수의 병합 모듈을 포함할 수 있습니다.  
  
 재배포 가능 패키지를 사용하여 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 라이브러리를 중앙 배포하면 Microsoft 자동 업데이트가 가능하므로 응용 프로그램에 동적 연결 및 재배포 가능 패키지를 사용하는 것이 좋습니다.  
  
## 로컬 배포  
 로컬 배포의 경우 라이브러리 파일은 응용 프로그램 폴더에 실행 파일과 함께 설치됩니다.  각 버전의 파일 이름은 버전 번호 포함으로 고유한 이름이 되기 때문에 다양한 버전의 라이브러리를 같은 폴더에 설치할 수 있습니다.  예를 들어, C 런타임 버전 12는 msvcr120.dll입니다.  
  
 Microsoft는 로컬 배포된 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 라이브러리를 자동으로 업데이트할 수 없기 때문에 이러한 라이브러리의 로컬 배포에 주의해야 합니다.  재배포 가능 라이브러리 로컬 배포를 사용하기로 결정하는 경우 로컬 배포된 라이브러리를 자동으로 업데이트하는 사용자 고유의 메서드를 구현하는 것이 좋습니다.  
  
## 정적 링크  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 라이브러리 파일을 별도로 배포할 필요가 없도록 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 라이브러리를 응용 프로그램에 정적 연결, 즉 응용 프로그램에 컴파일할 수 있습니다.  그러나 정적으로 연결된 라이브러리는 적절하게 업데이트할 수 없기 때문에 이 방식에 주의해야 합니다.  정적 연결을 사용하고 연결된 라이브러리를 업데이트하려면 응용 프로그램을 다시 컴파일하고 다시 배포해야 합니다.  
  
## 문제 해결  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 라이브러리의 로드 순서는 시스템에 따라 다릅니다.  로더 문제를 진단하려면 depends.exe 또는 where.exe를 사용합니다.  자세한 내용은 [동적 연결 라이브러리 순서\(Windows\)](http://msdn.microsoft.com/library/windows/desktop/ms682586.aspx)를 참조하십시오.  
  
## 참고 항목  
 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)