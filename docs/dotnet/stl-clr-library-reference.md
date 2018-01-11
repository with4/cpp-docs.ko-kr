---
title: "STL/CLR 라이브러리 참조 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- STL/CLR Library
- STL/CLR, redistribution
- cliext directory
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: aecb7c509fc1b072086a8772c3430c43b67350be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="stlclr-library-reference"></a>STL/CLR 라이브러리 참조
STL/CLR 라이브러리는 c + + 및.NET Framework 공용 언어 런타임 (CLR) 사용 하기 위해 c + + 표준 라이브러리의 하위 집합의 패키징. STL/CLR 컨테이너, 반복기 및 알고리즘의 관리 되는 환경에서 표준 라이브러리를 사용할 수 있습니다.  
  
 사용 하려면 STL/CLR:  
  
-   헤더에서 포함 된 **cliext** 일반적인 c + + 표준 라이브러리 해당 대신 하위 디렉터리가 포함 합니다.  
  
-   라이브러리 이름으로 한정 `cliext::` 대신 `std::`합니다.  
  
 .NET 어셈블리에서 어셈블리 간 시나리오에서 사용 하 여 제네릭 형식 및 인터페이스를 노출 하는 STL/CLR **Microsoft.VisualC.STLCLR.dll**합니다. 이 DLL은.NET Framework 3.5에 포함 됩니다. STL/CLR을 사용 하는 응용 프로그램을 재배포 하는 경우에.NET Framework 3.5 설치 프로젝트 종속성 섹션에서 프로젝트를 사용 하는 모든 Visual c + + 라이브러리를 포함 해야 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [cliext 네임스페이스](../dotnet/cliext-namespace.md)  
 STL/CLR 라이브러리의 모든 형식이 포함 된 네임 스페이스에 설명 합니다.  
  
 [STL/CLR 컨테이너](../dotnet/stl-clr-containers.md)  
 컨테이너 요소, 삽입할 수 있는 요소의 형식 및 소유권 문제에 대 한 요구 사항을 비롯 한 c + + 표준 라이브러리에 있는 컨테이너에 대 한 개요를 제공 합니다.  
  
 [STL/CLR 컨테이너 요소에 대한 요구 사항](../dotnet/requirements-for-stl-clr-container-elements.md)  
 C + + 표준 라이브러리 컨테이너에 삽입 된 모든 참조 형식에 대 한 최소 요구 사항을 설명 합니다.  
  
 [방법: .NET 컬렉션에서 STL/CLR 컨테이너로 변환](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)  
 STL/CLR 컨테이너.NET 컬렉션으로 변환 하는 방법에 설명 합니다.  
  
 [방법: STL/CLR 컨테이너에서 .NET 컬렉션으로 변환](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)  
 STL/CLR 컨테이너.NET 컬렉션으로 변환 하는 방법에 설명 합니다.  
  
 [방법: 어셈블리에서 STL/CLR 컨테이너 노출](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)  
 C + + 어셈블리를 작성 하는 여러 STL/CLR 컨테이너 요소를 표시 하는 방법을 보여 줍니다.  
  
 또한이 섹션에는 STL/CLR의 다음 구성 요소가 설명합니다.  
  
|||  
|-|-|  
|[adapter(STL/CLR)](../dotnet/adapter-stl-clr.md)|[algorithm(STL/CLR)](../dotnet/algorithm-stl-clr.md)|  
|[deque(STL/CLR)](../dotnet/deque-stl-clr.md)|[for each, in](../dotnet/for-each-in.md)|  
|[functional(STL/CLR)](../dotnet/functional-stl-clr.md)|[hash_map(STL/CLR)](../dotnet/hash-map-stl-clr.md)|  
|[hash_multimap(STL/CLR)](../dotnet/hash-multimap-stl-clr.md)|[hash_multiset(STL/CLR)](../dotnet/hash-multiset-stl-clr.md)|  
|[hash_set(STL/CLR)](../dotnet/hash-set-stl-clr.md)|[list(STL/CLR)](../dotnet/list-stl-clr.md)|  
|[map(STL/CLR)](../dotnet/map-stl-clr.md)|[multimap(STL/CLR)](../dotnet/multimap-stl-clr.md)|  
|[multiset(STL/CLR)](../dotnet/multiset-stl-clr.md)|[numeric(STL/CLR)](../dotnet/numeric-stl-clr.md)|  
|[priority_queue(STL/CLR)](../dotnet/priority-queue-stl-clr.md)|[queue(STL/CLR)](../dotnet/queue-stl-clr.md)|  
|[set(STL/CLR)](../dotnet/set-stl-clr.md)|[stack(STL/CLR)](../dotnet/stack-stl-clr.md)|  
|[utility(STL/CLR)](../dotnet/utility-stl-clr.md)|[vector(STL/CLR)](../dotnet/vector-stl-clr.md)|  
  
## <a name="see-also"></a>참고 항목  
 [C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)