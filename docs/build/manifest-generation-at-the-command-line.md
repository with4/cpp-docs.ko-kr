---
title: "명령줄에서 매니페스트 생성 | Microsoft Docs"
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
  - "매니페스트 도구(mt.exe)"
  - "매니페스트[C++]"
ms.assetid: fc2ff255-82b1-4c44-af76-8405c5850292
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 명령줄에서 매니페스트 생성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

nmake나 이와 유사한 도구를 사용하여 명령줄에서 C\/C\+\+ 응용 프로그램을 빌드하는 경우 링커가 모든 개체 파일을 처리하고 최종 이진 파일을 빌드한 후에 매니페스트가 생성됩니다.  링커는 개체 파일에 저장되어 있는 어셈블리 정보를 수집하고 이 정보를 최종 매니페스트 파일에 결합합니다.  기본적으로 링커는 최종 이진 파일을 설명하는 \<binary\_name\>.\<extension\>.manifest라는 파일을 생성합니다.  링커는 매니페스트 파일을 이진 파일 안에 포함하지 않으며 매니페스트를 외부 파일로만 생성할 수 있습니다.  매니페스트를 최종 이진 파일 안에 포함하는 방법에는 여러 가지가 있습니다. 예를 들어, [매니페스트 도구\(mt.exe\)](http://msdn.microsoft.com/library/aa375649)를 사용하거나 매니페스트를 리소스 파일로 컴파일할 수 있습니다.  증분 링크, 서명, 편집하며 계속하기 등과 같은 기능을 활성화하려면 매니페스트를 최종 이진 파일 안에 포함할 때 특정 규칙을 따라야 한다는 점을 명심할 필요가 있습니다.  명령줄에서 빌드할 때 사용되는 여러 가지 옵션에 대한 자세한 내용은 [방법: C\/C\+\+ 응용 프로그램에 매니페스트 포함](../build/how-to-embed-a-manifest-inside-a-c-cpp-application.md)을 참조하십시오.  
  
## 참고 항목  
 [매니페스트](http://msdn.microsoft.com/library/aa375365)   
 [\/INCREMENTAL\(증분 링크\)](../build/reference/incremental-link-incrementally.md)   
 [강력한 이름 어셈블리\(어셈블리 서명\)](../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)   
 [편집하며 계속하기](../Topic/Edit%20and%20Continue.md)   
 [C\/C\+\+ 프로그램의 매니페스트 생성 이해](../build/understanding-manifest-generation-for-c-cpp-programs.md)