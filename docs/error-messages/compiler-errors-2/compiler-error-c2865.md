---
title: "컴파일러 오류 C2865 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2865"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2865"
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2865
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : handle\_or\_pointer에 대한 비교가 잘못되었습니다.  
  
 [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md) 또는 [\_\_gc](../../misc/gc.md) 형식에 대한 참조의 동등성만 비교하여 이 참조들이 동일 개체를 참조하는지\(\=\=\) 아니면 각기 다른 개체를 참조하는지\(\!\=\) 알아볼 수 있습니다.  
  
 .NET 런타임은 관리되는 개체를 언제든지 이동하여 테스트 결과를 변경할 수 있으므로 이 참조의 순서는 비교할 수 없습니다.