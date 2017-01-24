---
title: "컴파일러 오류 C3913 | Microsoft Docs"
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
  - "C3913"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3913"
ms.assetid: a678bfce-9524-470d-9f23-7d08ecb972c8
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3913
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 속성은 인덱싱되어야 합니다.  
  
 기본 속성을 잘못 정의했습니다.  
  
 자세한 내용은 [속성](../../windows/property-cpp-component-extensions.md)을 참조하십시오.  
  
 다음 샘플에서는 C3913 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3913.cpp  
// compile with: /clr /c  
ref struct X {  
   property int default {   // C3913  
   // try the following line instead  
   // property int default[int] {  
      int get(int) { return 0; }  
      void set(int, int) {}  
   }  
};  
```