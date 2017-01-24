---
title: "컴파일러 오류 C2842 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2842"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2842"
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2842
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : 관리되는 형식 또는 WinRT 형식은 고유한 'operator new' 또는 'operator delete'를 정의할 수 없습니다.  
  
 고유한 [operator new](../Topic/operator%20new%20\(%3Cnew%3E\).md) 또는 [operator delete](../Topic/operator%20delete%20\(%3Cnew%3E\).md)를 정의하여 네이티브 힙의 메모리 할당을 관리할 수 있습니다.  그러나 참조 클래스는 관리되는 힙에만 할당되기 때문에 이러한 연산자를 정의할 수 없습니다.  
  
 자세한 내용은 [사용자 정의 연산자](../../dotnet/user-defined-operators-cpp-cli.md)를 참조하세요.  
  
## 예제  
 다음 샘플에서는 C2842 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2842.cpp  
// compile with: /clr /c  
ref class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```  
  
## 예제  
 다음 샘플에서는 C2842 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2842_b.cpp  
// compile with: /clr:oldSyntax /c  
__gc class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```