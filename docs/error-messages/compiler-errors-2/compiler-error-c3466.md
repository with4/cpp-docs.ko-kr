---
title: "컴파일러 오류 C3466 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3466"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3466"
ms.assetid: 69a877d9-a749-474b-bfc3-8d3fd53ba8fd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C3466
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 제네릭 클래스의 특수화는 전달할 수 없습니다.  
  
 제네릭 클래스의 특수화에는 형식 전달을 사용할 수 없습니다.  
  
 자세한 내용은 [Type Forwarding \(C\+\+\/CLI\)](../../windows/type-forwarding-cpp-cli.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 구성 요소를 만듭니다.  
  
```  
// C3466.cpp  
// compile with: /clr /LD  
generic<typename T>  
public ref class GR {};  
  
public ref class GR2 {};  
```  
  
## 예제  
 다음 샘플에서는 C3466 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3466_b.cpp  
// compile with: /clr /c  
#using "C3466.dll"  
[assembly:TypeForwardedTo(GR<int>::typeid)];   // C3466  
[assembly:TypeForwardedTo(GR2::typeid)];   // OK  
```