---
title: "컴파일러 오류 C2261 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2261"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2261"
ms.assetid: 60969482-9e83-49b5-9631-a04bc844da12
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2261
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'string' : 어셈블리 참조가 잘못되어 확인할 수 없습니다.  
  
 값이 잘못되었습니다.  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>는 friend 어셈블리를 지정하는 데 사용됩니다.  예를 들어, a.dll에서 b.dll을 friend 어셈블리로 지정하려는 경우 a.dll에서 InternalsVisibleTo\("b"\)를 지정합니다.  그런 다음 런타임에 b.dll에서 전용 형식을 제외한 a.dll의 모든 내용에 액세스할 수 있습니다.  
  
 friend 어셈블리를 지정하는 올바른 구문에 대한 자세한 내용은 [Friend 어셈블리\(C\+\+\)](../../dotnet/friend-assemblies-cpp.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C2261 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2261.cpp  
// compile with: /clr /c  
using namespace System::Runtime::CompilerServices;  
[assembly: InternalsVisibleTo("a,a,a")];   // C2261  
[assembly: InternalsVisibleTo("a.a")];   // OK  
[assembly: InternalsVisibleTo("a")];   // OK  
```