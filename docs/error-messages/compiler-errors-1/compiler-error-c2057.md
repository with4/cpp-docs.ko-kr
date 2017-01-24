---
title: "컴파일러 오류 C2057 | Microsoft Docs"
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
  - "C2057"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2057"
ms.assetid: 038a99d6-1f5a-42fa-8449-03b4ff11ee0b
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2057
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

상수 식이 필요합니다.  
  
 컨텍스트에는 컴파일 시간에 값이 인식되는 상수 식이 필요합니다.  
  
 컴파일러는 해당 형식의 인스턴스에 대한 공간을 할당하기 위해 컴파일 시간에 형식의 크기를 알고 있어야 합니다.  
  
## 예제  
 다음 샘플에서는 C2057을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2057.cpp  
int i;  
int b[i];   // C2057 - value of i is unknown at compile time  
int main() {  
   const int i = 8;  
   int b[i]; // OK - value of i is fixed and known to compiler  
}  
```  
  
## 예제  
 C에서는 상수 식에 대해 보다 제한적인 규칙을 제공합니다.  다음 샘플에서는 C2057을 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C2057b.c  
#define ArraySize1 10  
int main() {   
   const int ArraySize2 = 10;   
   int h[ArraySize2];   // C2057 - C does not allow variables here  
   int h[ArraySize1];   // OK - uses preprocessor constant  
}  
```