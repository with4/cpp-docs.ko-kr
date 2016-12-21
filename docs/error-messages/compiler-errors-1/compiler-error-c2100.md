---
title: "컴파일러 오류 C2100 | Microsoft Docs"
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
  - "C2100"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2100"
ms.assetid: 9ed5ea11-9d55-4ddf-8b1a-162c74f3c390
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2100
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

간접 참조가 잘못되었습니다.  
  
 간접 참조 연산자\(`*` \)가 비포인터 값에 적용되었습니다.  
  
 다음 샘플에서는 C2100 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2100.cpp  
int main() {  
   int r = 0, *s = 0;  
   s = &r;  
   *r = 200;   // C2100  
   *s = 200;   // OK  
}  
```