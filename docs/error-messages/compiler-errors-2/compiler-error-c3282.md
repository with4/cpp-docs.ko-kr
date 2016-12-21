---
title: "Compiler Error C3282 | Microsoft Docs"
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
  - "C3282"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3282"
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C3282
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

제네릭 매개 변수 목록은 관리되는 클래스, WINRT 클래스, 구조체 또는 함수에만 사용할 수 있습니다.  
  
 제네릭 매개 변수 목록이 잘못 사용되었습니다.  자세한 내용은 [Generics](../../windows/generics-cpp-component-extensions.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3282 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C3282.cpp  
// compile with: /clr /c  
generic <typename T> int x;   // C3282  
  
ref struct GC0 {  
   generic <typename T> int x;   // C3282  
};  
  
// OK  
generic <typename T>  
ref class M {};  
```