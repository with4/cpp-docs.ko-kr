---
title: "컴파일러 경고 (수준 1) C4129 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4129"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4129"
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4129
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'character' : 문자 이스케이프 시퀀스를 인식할 수 없습니다.  
  
 문자 또는 문자열 상수에서 백슬래시\(\\\) 다음에 오는 `character`은\(는\) 유효한 이스케이프 시퀀스로 인식되지 않습니다.  백슬래시는 무시되어 인쇄되지 않지만  백슬래시 다음에 오는 문자는 인쇄됩니다.  
  
 단일 백슬래시를 인쇄하려면 이중 백슬래시\(\\\\\)를 지정하십시오.  
  
 이스케이프 시퀀스에 대한 내용은 단원 2.13.2의 C\+\+ 표준에 나와 있습니다.  
  
 다음 샘플에서는 C4129 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4129.cpp  
// compile with: /W1  
int main() {  
   char array1[] = "\/709";   // C4129  
   char array2[] = "\n709";   // OK  
}  
```