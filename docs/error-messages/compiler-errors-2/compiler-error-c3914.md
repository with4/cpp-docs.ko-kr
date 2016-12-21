---
title: "컴파일러 오류 C3914 | Microsoft Docs"
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
  - "C3914"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3914"
ms.assetid: 8f3190e6-ee50-4916-9ecc-3b8748b2e1e7
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3914
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 속성은 정적일 수 없습니다.  
  
 기본 속성이 잘못 선언되었습니다.  자세한 내용은 [방법: 인덱싱된 속성 사용](../../misc/how-to-use-indexed-properties.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3914 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3914.cpp  
// compile with: /clr /c  
ref struct X {  
   static property int default[int] {   // C3914  
   // try the following line instead  
   // property int default[int] {  
      int get(int) { return 0; }  
      void set(int, int) {}  
   }  
};  
```