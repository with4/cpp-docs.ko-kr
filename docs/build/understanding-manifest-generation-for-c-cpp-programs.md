---
title: "C/C++ 프로그램의 매니페스트 생성 이해 | Microsoft Docs"
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
  - "매니페스트[C++]"
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
caps.latest.revision: 12
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C/C++ 프로그램의 매니페스트 생성 이해
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[매니페스트](http://msdn.microsoft.com/library/aa375365)는 응용 프로그램이나 어셈블리 안에 리소스로 포함되거나 외부 XML 파일로 제공되는 XML 문서입니다.  [격리된 응용 프로그램](http://msdn.microsoft.com/library/aa375190)의 매니페스트는 런타임에 응용 프로그램을 바인딩해야 하는 공유 side\-by\-side 어셈블리의 이름과 버전을 관리하는 데 사용됩니다.  [side\-by\-side 어셈블리](_win32_side_by_side_assemblies)의 매니페스트는 이름, 버전, 리소스 및 기타 어셈블리에 대한 종속성을 지정합니다.  
  
 격리된 응용 프로그램 또는 side\-by\-side 어셈블리에 대한 매니페스트를 만드는 데는 두 가지 방법이 있습니다.  첫 번째 방법으로 어셈블리 작성자는 규칙 및 명명 요구 사항에 따라 매니페스트 파일을 수동으로 만들 수 있습니다.  그러나 프로그램이 CRT, MFC, ATL 등의 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 어셈블리에만 의존하는 경우 링커에서 매니페스트를 자동으로 생성할 수 있습니다.  
  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 라이브러리의 헤더에는 어셈블리의 정보가 포함됩니다. 라이브러리를 응용 프로그램 코드에 포함하면 링커가 최종 이진 파일에 대한 매니페스트를 구성하는 데 이 어셈블리 정보가 사용됩니다.  링커는 매니페스트 파일을 이진 파일 안에 포함하지 않으며 매니페스트를 외부 파일로만 생성할 수 있습니다.  매니페스트를 외부 파일로 생성하면 일부 시나리오에서 문제가 발생합니다.  예를 들어 전용 어셈블리의 경우에는 매니페스트를 포함하는 것이 좋습니다.  nmake를 사용하여 코드를 빌드하는 경우와 같이 명령줄에서 빌드할 때는 매니페스트 도구를 사용하여 매니페스트를 포함할 수 있습니다. 자세한 내용은 [명령줄에서 매니페스트 생성](../build/manifest-generation-at-the-command-line.md)을 참조하십시오.  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]에서 빌드하는 경우 **프로젝트 속성** 대화 상자에서 매니페스트 도구의 속성을 설정하여 매니페스트를 포함할 수 있습니다. 자세한 내용은 [Visual Studio에서 매니페스트 생성](../build/manifest-generation-in-visual-studio.md)을 참조하십시오.  
  
## 참고 항목  
 [격리된 응용 프로그램 및 side\-by\-side 어셈블리 개념](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C\/C\+\+ 격리된 응용 프로그램 및 side\-by\-side 어셈블리 빌드](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)