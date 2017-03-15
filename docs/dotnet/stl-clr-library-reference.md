---
title: "STL/CLR 라이브러리 참조 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cliext 디렉터리"
  - "STL/CLR 라이브러리"
  - "STL/CLR, 재배포"
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# STL/CLR 라이브러리 참조
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

STL\/CLR 라이브러리는 표준 C\+\+ 라이브러리의 하위 집합인 STL\(표준 템플릿 라이브러리\) 패키징이며, C\+\+ 및 .NET Framework CLR\(공용 언어 런타임\)과 함께 사용할 수 있습니다.  STL\/CLR을 통해 관리되는 환경에서 STL의 모든 컨테이너, 반복기 및 알고리즘을 사용할 수 있습니다.  
  
 STL\/CLR을 사용하려면:  
  
-   일반적인 표준 C\+\+ 라이브러리와 동일한 항목이 아닌 **cliext** 포함 하위 디렉터리의 헤더를 포함합니다.  
  
-   라이브러리 이름을 `std::`가 아닌 `cliext::`로 한정합니다.  
  
 STL\/CLR은 .NET 어셈블리 **Microsoft.VisualC.STLCLR.dll**의 어셈블리 간 시나리오에서 사용하는 제네릭 형식 및 인터페이스를 노출합니다.  이 DLL은 .NET Framework 3.5에 포함되었습니다.  STL\/CLR을 사용하는 응용 프로그램을 재배포할 경우에는 설치 프로젝트의 종속성 섹션에서 프로젝트에 사용되는 다른 모든 Visual C\+\+ 라이브러리는 물론 .NET Framework 3.5를 포함해야 합니다.  
  
## 단원 내용  
 [cliext 네임스페이스](../dotnet/cliext-namespace.md)  
 STL\/CLR 라이브러리의 모든 형식이 들어있는 네임스페이스를 설명합니다.  
  
 [STL\/CLR 컨테이너](../dotnet/stl-clr-containers.md)  
 컨테이너 구성 요소와 삽입할 구성 요소의 유형에 관한 요건 및 소유권 문제, 표준 C\+\+ 라이브러리의 컨테이너 등에 관하여 간단한 설명이 제시됩니다.  
  
 [STL\/CLR 컨테이너 요소에 대한 요구 사항](../dotnet/requirements-for-stl-clr-container-elements.md)  
 STL 컨테이너에 삽입되는 모든 참조 형식의 최소 요구 사항에 대해 설명합니다.  
  
 [방법: .NET 컬렉션에서 STL\/CLR 컨테이너로 변환](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)  
 .NET 컬렉션을 STL\/CLR 컨테이너로 변환하는 방법에 대해 설명합니다.  
  
 [방법: STL\/CLR 컨테이너에서 .NET 컬렉션으로 변환](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)  
 STL\/CLR 컨테이너를 .NET 컬렉션으로 변환하는 방법에 대해 설명합니다.  
  
 [방법: 어셈블리에서 STL\/CLR 컨테이너 노출](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)  
 C\+\+ 어셈블리로 여러 STL\/CLR 컨테이너의 요소를 표시하는 방법을 보여줍니다.  
  
 이 단원에서는 STL\/CLR의 다음 구성 요소에 대해서도 설명합니다.  
  
|||  
|-|-|  
|[adapter](../dotnet/adapter-stl-clr.md)|[algorithm](../dotnet/algorithm-stl-clr.md)|  
|[deque](../dotnet/deque-stl-clr.md)|[for each, in](../dotnet/for-each-in.md)|  
|[functional](../dotnet/functional-stl-clr.md)|[hash\_map](../dotnet/hash-map-stl-clr.md)|  
|[hash\_multimap](../dotnet/hash-multimap-stl-clr.md)|[hash\_multiset](../dotnet/hash-multiset-stl-clr.md)|  
|[hash\_set](../dotnet/hash-set-stl-clr.md)|[list](../dotnet/list-stl-clr.md)|  
|[map](../dotnet/map-stl-clr.md)|[multimap](../dotnet/multimap-stl-clr.md)|  
|[multiset](../dotnet/multiset-stl-clr.md)|[numeric](../dotnet/numeric-stl-clr.md)|  
|[priority\_queue](../dotnet/priority-queue-stl-clr.md)|[queue](../dotnet/queue-stl-clr.md)|  
|[set](../dotnet/set-stl-clr.md)|[stack](../dotnet/stack-stl-clr.md)|  
|[utility](../dotnet/utility-stl-clr.md)|[vector](../dotnet/vector-stl-clr.md)|  
  
## 참고 항목  
 [C\+\+ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)