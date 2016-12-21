---
title: "관리되는 형식(C++/CL) | Microsoft Docs"
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
  - "__gc 형식"
  - "형식[C++], CLR"
ms.assetid: 1ddd114e-be02-4de7-a4dd-a2d72ad8ff81
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 관리되는 형식(C++/CL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 관리되는 형식을 선언하는 구문과 이러한 형식의 개체를 만들고 사용하는 구문이 Managed Extensions for C\+\+와 상당히 다르게 변경되었습니다.  이 차이는 ISO\-C\+\+ 형식 시스템 내에서의 통합을 강화하는 데 따른 것입니다.  다음 하위 단원에서는 이러한 변경 내용에 대해 자세하게 설명합니다.  
  
## 단원 내용  
 [관리되는 클래스 형식 선언](../dotnet/declaration-of-a-managed-class-type.md)  
 관리되는 `class`, `struct` 또는 `interface`를 선언하는 방법에 대해 설명합니다.  
  
 [CLR 참조 클래스 개체 선언](../dotnet/declaration-of-a-clr-reference-class-object.md)  
 추적 핸들을 사용하여 참조 클래스 형식 개체를 선언하는 방법에 대해 설명합니다.  
  
 [CLR 배열 선언](../dotnet/declaration-of-a-clr-array.md)  
 배열을 선언하고 초기화하는 방법에 대해 설명합니다.  
  
 [생성자 초기화 순서 변경 사항](../dotnet/changes-in-constructor-initialization-order.md)  
 클래스 생성자 초기화 순서의 주요 변경 내용에 대해 설명합니다.  
  
 [소멸자 의미의 변경 내용](../dotnet/changes-in-destructor-semantics.md)  
 명확하지 않은 종료, `Finalize` 및 `Dispose` 비교, 참조 개체에 대한 문제, 명시적 `Finalize` 사용 등에 대해 설명합니다.  
  
 **참고:** 대리자에 대한 내용은 [클래스 또는 인터페이스 내에서 멤버 선언\(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)의 일반 항목인 클래스 내의 이벤트 멤버와 함께 설명하기 위해 [대리자 및 이벤트](../dotnet/delegates-and-events.md)에서 다룹니다.  
  
## 참고 항목  
 [C\+\+\/CLI 마이그레이션 입문](../dotnet/cpp-cli-migration-primer.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Arrays](../windows/arrays-cpp-component-extensions.md)