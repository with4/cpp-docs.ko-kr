---
title: "C/C++ side-by-side 어셈블리 빌드 | Microsoft Docs"
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
  - "side-by-side 응용 프로그램[C++]"
ms.assetid: 7fa20b16-3737-4f76-a0b5-1dacea19a1e8
caps.latest.revision: 18
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C/C++ side-by-side 어셈블리 빌드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[side\-by\-side assembly](_win32_side_by_side_assemblies)를 DLL 그룹, Windows 클래스, COM 서버, 형식 라이브러리 또는 인터페이스 같이 런타임에 실행할 응용 프로그램에 사용할 수 있는 리소스의 컬렉션입니다.  어셈블리에서 DLL을 다시 패키지할 때의 가장 큰 이점은 여러 버전의 어셈블리를 응용 프로그램에서 동시에 사용할 수 있고 업데이트가 릴리스되는 경우 현재 설치된 어셈블리를 서비스할 수 있다는 점입니다.  
  
 Visual C\+\+ 응용 프로그램에서는 응용 프로그램의 서로 다른 부분에 하나 또는 여러 개의 DLL을 사용할 수 있습니다.  DLL은 런타임에 주 프로세스에 로드되고 필요한 코드가 실행됩니다.  응용 프로그램은 필요한 DLL을 찾고 여기에 종속된 다른 DLL을 확인하고 요청된 DLL과 이러한 종속 DLL을 함께 로드하기 위해 운영 체제에서 제공하는 정보를 사용합니다.  Windows XP, Windows Server 2003 및 Windows Vista 이전 버전의 Windows 운영 체제에서는 운영 체제 로더가 종속 DLL을 찾을 때 응용 프로그램의 로컬 폴더나 시스템 경로에 지정된 다른 폴더를 검색합니다.  Windows XP, Windows Server 2003 및 Windows Vista에서는 운영 체제 로더가 [manifest](http://msdn.microsoft.com/library/aa375365)를 파일을 사용하여 종속 DLL을 검색하거나 이러한 DLL이 포함된 side\-by\-side 어셈블리를 검색할 수도 있습니다.  
  
 기본적으로 Visual Studio를 사용하여 DLL을 빌드하는 경우 ID가 2인 RT\_MANIFEST 리소스로 포함된 [응용 프로그램 매니페스트](http://msdn.microsoft.com/library/aa374191)가 있습니다.  이 매니페스트는 실행 파일의 경우와 마찬가지로 다른 어셈블리에 대한 이 DLL의 종속성을 설명합니다.  이 매니페스트는 DLL이 side\-by\-side 어셈블리의 일부가 아니고 이 DLL에 종속된 응용 프로그램이 응용 프로그램 매니페스트를 사용하여 이를 로드하는 대신 운영 체제 로더를 사용하여 시스템 경로에서 이 DLL을 찾는 것으로 가정합니다.  
  
> [!NOTE]
>  응용 프로그램 매니페스트를 사용하는 DLL의 경우 ID가 2인 리소스로 매니페스트가 포함되는 것이 중요합니다.  예를 들어 [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175) 함수를 사용하여 DLL을 런타임에 동적으로 로드하는 경우 운영 체제 로더는 DLL의 매니페스트에 지정된 종속 어셈블리를 로드합니다.  `LoadLibrary` 호출 도중 DLL의 외부 응용 프로그램 매니페스트는 검사되지 않습니다.  매니페스트가 포함되어 있지 않으면 로더가 잘못된 버전의 어셈블리를 로드하려고 하거나 종속 어셈블리를 찾지 못할 수 있습니다.  
  
 하나 이상의 관련 DLL을 해당 [assembly manifest](http://msdn.microsoft.com/library/aa374219)를 있는 side\-by\-side 어셈블리로 다시 패키지할 수 있습니다. 이 매니페스트는 어떠한 파일이 어셈블리를 구성하는지 설명하고 다른 side\-by\-side 어셈블리에 대한 이 어셈블리의 종속성에 대해 설명합니다.  
  
> [!NOTE]
>  어셈블리에 포함된 DLL이 하나인 경우 어셈블리 매니페스트를 ID가 1인 리소스로 이 DLL에 포함시키고 전용 어셈블리에 DLL과 같은 이름을 지정하는 것이 좋습니다.  예를 들어, DLL의 이름이 mylibrary.dll인 경우 매니페스트의 \<assemblyIdentity\> 요소에 사용되는 이름 특성의 값도 mylibrary일 수 있습니다.  MFC ActiveX 프로젝트에서 .ocx 라이브러리를 만드는 경우와 같이 라이브러리의 확장명이 .dll이 아닌 경우 외부 어셈블리 매니페스트가 작성될 수 있습니다.  이 경우 어셈블리 및 해당 매니페스트의 이름은 DLL의 이름과 달라야 합니다\(예: MyAssembly, MyAssembly.manifest 및 mylibrary.ocx\).  그러나 이 경우에도 이러한 라이브러리의 이름을 변경하여 확장명을 .dll로 지정하고 매니페스트를 리소스로 포함하여 나중에 이 어셈블리를 유지 관리하는 데 드는 비용을 줄이는 것이 좋습니다.  운영 체제에서 전용 어셈블리를 검색하는 방식에 대한 자세한 내용은 [Assembly Searching Sequence](http://msdn.microsoft.com/library/aa374224)를 참조하십시오.  
  
 이 변경 내용에 따라 해당 DLL을 응용 프로그램 로컬 폴더에 [private assembly](_win32_private_assemblies)를 배포하거나 WinSxS 어셈블리 캐시에 [shared assembly](https://msdn.microsoft.com/en-us/library/aa375996.aspx)를 배포할 수 있습니다.  이 새로운 어셈블리가 런타임에 올바르게 동작하도록 하려면 여러 단계를 거쳐야 합니다. 자세한 내용은 [Guidelines for Creating Side\-by\-side Assemblies](http://msdn.microsoft.com/library/aa375155)를 참조하십시오.  어셈블리를 올바르게 작성한 다음 이 어셈블리에 의존하는 응용 프로그램과 함께 이를 공유 어셈블리나 전용 어셈블리로 배포할 수 있습니다.  side\-by\-side 어셈블리를 공유 어셈블리로 설치할 때 [Installing Win32 Assemblies for Side\-by\-Side Sharing on Windows XP](http://msdn.microsoft.com/library/aa369532)를 설명하는 지침을 따르거나 [merge modules](http://msdn.microsoft.com/library/aa369820)를 사용하십시오.  side\-by\-side 어셈블리를 전용 어셈블리로 설치하는 경우 설치 과정에서 해당 DLL, 리소스 및 어셈블리 매니페스트를 대상 컴퓨터의 응용 프로그램 로컬 폴더에 복사하기만 하면 런타임에 로더가 이 어셈블리를 찾을 수 있습니다. 자세한 내용은 [Assembly Searching Sequence](http://msdn.microsoft.com/library/aa374224)를 참조하십시오.  다른 방법은 [Windows Installer](http://msdn.microsoft.com/library/cc185688)를 사용하고 [Installing Win32 Assemblies for the Private Use of an Application on Windows XP](http://msdn.microsoft.com/library/aa369534)를 설명한 지침을 따르는 것입니다.  
  
## 참고 항목  
 [배포 예제](../ide/deployment-examples.md)   
 [C\/C\+\+ 격리된 응용 프로그램 빌드](../build/building-c-cpp-isolated-applications.md)   
 [C\/C\+\+ 격리된 응용 프로그램 및 side\-by\-side 어셈블리 빌드](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)