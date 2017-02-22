---
title: "Visual Studio에서 매니페스트 생성 | Microsoft Docs"
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
  - "매니페스트[C++]"
ms.assetid: 0af60aa9-d223-42cd-8426-b3fc543a2a81
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Visual Studio에서 매니페스트 생성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

특정 프로젝트에 대한 매니페스트 파일 생성은 프로젝트 **속성 페이지** 대화 상자에서 제어할 수 있습니다.  **구성 속성** 탭에서 **링커**, **매니페스트 파일**, **매니페스트 생성**을 차례로 클릭합니다.  새 프로젝트의 프로젝트 속성은 기본적으로 매니페스트 파일을 생성하도록 설정됩니다.  그러나 프로젝트의 **매니페스트 생성** 속성을 사용하여 프로젝트의 매니페스트 생성을 비활성화할 수 있습니다.  이 속성을 **예**로 설정하면 이 프로젝트에 대한 매니페스트가 생성됩니다.  그렇지 않으면 링커에서 응용 프로그램 코드의 종속성을 확인할 때 어셈블리 정보를 무시하며 매니페스트를 생성하지 않습니다.  
  
 Visual Studio의 빌드 시스템에서는 매니페스트를 최종 이진 응용 프로그램 파일에 포함하거나 외부 파일로 생성할 수 있습니다.  이 동작은 **프로젝트 속성** 대화 상자의 **매니페스트 포함** 옵션에 의해 제어됩니다.  이 속성을 설정하려면 **매니페스트 도구** 노드를 열고 **입력 및 출력**을 선택합니다.  매니페스트가 포함되지 않도록 설정하면 매니페스트가 외부 파일로 생성되고 최종 이진 파일과 동일한 디렉터리에 저장됩니다.  매니페스트가 포함되도록 설정하면 Visual Studio에서 다음과 같은 과정을 거쳐 최종 매니페스트를 포함합니다.  
  
1.  소스 코드가 개체 파일로 컴파일된 후 링커에서 종속 어셈블리 정보를 수집합니다.  링커에서 최종 이진 파일을 링크하는 도중 이후에 최종 매니페스트를 생성하는 데 사용되는 중간 매니페스트가 생성됩니다.  
  
2.  중간 매니페스트 및 링크가 완료된 후 매니페스트 도구가 실행되어 최종 매니페스트가 병합되고 외부 파일로 저장됩니다.  
  
3.  그런 다음 프로젝트 빌드 시스템은 매니페스트 도구가 생성한 매니페스트에 이진 파일에 이미 포함된 매니페스트와 다른 정보가 있는지 확인합니다.  
  
4.  이진 파일에 포함된 매니페스트가 매니페스트 도구에서 생성한 매니페스트와 다르거나 이진 파일에 포함된 매니페스트가 없는 경우 Visual Studio는 링커를 한 번 더 호출하여 외부 매니페스트 파일을 이진 파일에 리소스로 포함합니다.  
  
5.  이진 파일에 포함된 매니페스트가 매니페스트 도구에서 생성한 매니페스트와 동일한 경우 빌드가 다음 단계로 진행됩니다.  
  
 매니페스트는 최종 이진 파일 내에 텍스트 리소스로 포함되고 최종 이진 파일을 Visual Studio에서 파일로 열면 매니페스트를 볼 수 있습니다.  매니페스트가 올바른 라이브러리를 가리키는지 확인하려면 [Visual C\+\+ 응용 프로그램의 종속성 이해](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)에 설명된 단계를 수행하거나 [문제 해결](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md) 단원에 제시된 방법을 따르십시오.  
  
## 참고 항목  
 [방법: C\/C\+\+ 응용 프로그램에 매니페스트 포함](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)   
 [전용 어셈블리](_win32_private_assemblies)   
 [매니페스트 도구](http://msdn.microsoft.com/library/aa375649)   
 [C\/C\+\+ 프로그램의 매니페스트 생성 이해](../build/understanding-manifest-generation-for-c-cpp-programs.md)