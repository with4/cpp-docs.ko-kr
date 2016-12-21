---
title: "컴파일러 오류 C2776 | Microsoft Docs"
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
  - "C2776"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2776"
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2776
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

속성 당 'get' 메서드를 하나만 지정할 수 있습니다.  
  
 [property](../../cpp/property-cpp.md) 확장 특성에 `get` 함수를 하나만 지정할 수 있습니다.  이 오류는 `get` 함수를 여러 개 지정할 경우에 발생합니다.  
  
 다음 샘플에서는 C2776 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2776.cpp  
struct A {  
   __declspec(property(get=GetProp,get=GetPropToo))  
   // try the following line instead  
   // __declspec(property(get=GetProp))  
      int prop;   // C2776  
   int GetProp(void);  
   int GetPropToo(void);  
};  
```