---
title: "컴파일러 오류 C3155 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3155"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3155"
ms.assetid: b04a42e1-64e7-40f8-81fe-c7945348b2cf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3155
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

속성 인덱서에는 특성을 사용할 수 없습니다.  
  
 인덱싱된 속성을 잘못 선언했습니다.  자세한 내용은 [방법: 인덱싱된 속성 사용](../../misc/how-to-use-indexed-properties.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3155 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3155.cpp  
// compile with: /clr /c  
using namespace System;  
ref struct R {  
   property int F[[ParamArray] int] {   // C3155  
   // try the following line instead  
   // property int F[ int] {   // OK  
      int get(int i) {   
         return 0;   
      }  
   }  
};  
```