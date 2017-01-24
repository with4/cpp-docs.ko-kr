---
title: "컴파일러 오류 C2777 | Microsoft Docs"
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
  - "C2777"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2777"
ms.assetid: 5fe158c0-2a65-488a-aca2-61d4a8b32d43
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2777
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

속성 당 'put' 메서드를 하나만 지정할 수 있습니다.  
  
 [속성](../../cpp/property-cpp.md) declspec 한정자에 `put` 속성이 여러 개 있습니다.  
  
 다음 샘플에서는 C2777 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2777.cpp  
struct A {  
   __declspec(property(put=PutProp,put=PutPropToo))   // C2777  
   // try the following line instead  
   // __declspec(property(put=PutProp))  
      int prop;  
   int PutProp(void);  
   int PutPropToo(void);  
};  
```