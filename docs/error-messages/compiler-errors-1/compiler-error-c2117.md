---
title: "컴파일러 오류 C2117 | Microsoft Docs"
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
  - "C2117"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2117"
ms.assetid: b947379d-5861-42fc-ac26-170318579cbd
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2117
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 배열 범위 오버플로입니다.  
  
 배열에 이니셜라이저가 너무 많습니다.  
  
-   배열 요소와 초기 값의 크기 및 개수가 일치하지 않습니다.  
  
-   문자열에 null 종결자에 대한 공간이 없습니다.  
  
 다음 샘플에서는 C2117 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2117.cpp  
int main() {  
   char abc[4] = "abcd";   // C2117  
   char def[4] = "abd";   // OK  
}  
```