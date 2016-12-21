---
title: "값 형식 및 동작(C++/CLI) | Microsoft Docs"
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
  - "값 형식"
ms.assetid: 5cb872a6-1e0a-429d-853d-df4ab47e8f2a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 값 형식 및 동작(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)]에서는 값 형식이 여러 가지 면에서 Managed Extensions for C\+\+와 다르게 변경되었습니다.  이 단원에서는 CLR 열거형 형식과 값 클래스 형식을 살펴보고 boxing 및 CLR 힙에서의 boxed 인스턴스에 대한 액세스를 비롯하여 내부 포인터 및 고정 포인터에 대한 내용도 살펴봅니다.  이러한 언어 영역에서 매우 많은 부분이 변경되었습니다.  
  
## 단원 내용  
 [CLR Enum Type](../dotnet/value-types-and-their-behaviors-cpp-cli.md)  
 열거형 선언과 동작의 변경 사항에 대해 설명합니다.  
  
 [값 형식 명시적 boxing](../dotnet/implicit-boxing-of-value-types.md)  
 값 형식을 암시적으로 boxing하는 이유와 그에 따라 변경된 동작에 대해 설명합니다.  
  
 [boxed 값에 대한 추적 핸들](../dotnet/a-tracking-handle-to-a-boxed-value.md)  
 값 형식에 대한 암시적 boxing을 boxed 값 개체에 대한 추적 핸들로 변환하는 방법에 대해 설명합니다.  
  
 [값 형식 의미](../dotnet/value-type-semantics.md)  
 상속된 가상 메서드, 클래스 기본 생성자, 내부 포인터, 고정 포인터를 비롯하여 값 형식 의미에서 변경된 사항에 대해 설명합니다.  
  
## 참고 항목  
 [C\+\+\/CLI 마이그레이션 입문](../dotnet/cpp-cli-migration-primer.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)