---
title: "컴파일러 오류 C2779 | Microsoft Docs"
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
  - "C2779"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2779"
ms.assetid: 4a00e492-855a-41f3-8a18-5f60ee20c2f2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2779
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration' : 속성 메서드는 비정적 데이터 멤버와만 연결될 수 있습니다.  
  
 `property` 확장 특성이 정적 데이터 멤버에 잘못 적용되었습니다.  
  
 다음 샘플에서는 C2779 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2779.cpp  
struct A {  
   static __declspec(property(put=PutProp))  
   // try the following line instead  
   __declspec(property(put=PutProp))  
      int prop;   // C2779  
   int PutProp(void);  
};  
```