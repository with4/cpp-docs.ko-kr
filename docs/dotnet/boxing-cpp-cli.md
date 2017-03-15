---
title: "Boxing(C++/CLI) | Microsoft Docs"
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
ms.assetid: f4ee27a8-6a34-432d-b9ec-39285d513b23
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Boxing(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Boxing is the process of converting a value type to the type `object` or to any interface type that's implemented by the value type.  When the common language runtime \(CLR\) boxes a value type, it wraps the value in a `System.Object` and stores it on the managed heap.  unboxing하면 개체에서 값 형식이 추출됩니다.  Boxing은 암시적이며 unboxing은 명시적입니다.  
  
## 관련 문서  
  
|제목|설명|  
|--------|--------|  
|[방법: 명시적으로 boxing 요청](../dotnet/how-to-explicitly-request-boxing.md)|Describes how to explicitly request boxing on a variable.|  
|[방법: gcnew를 사용하여 값 형식 만들기 및 암시적 boxing 사용](../dotnet/how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing.md)|Shows how to use `gcnew` to create a boxed value type that can be placed on the managed, garbage\-collected heap.|  
|[방법: Unbox](../dotnet/how-to-unbox.md)|Shows how to unbox and modify a value.|  
|[표준 변환 및 암시적 boxing](../dotnet/standard-conversions-and-implicit-boxing.md)|Shows that a standard conversion is chosen by the compiler over a conversion that requires boxing.|  
|[C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|The top\-level article for .NET programming in the Visual C\+\+ documentation.|