---
title: "컴파일러 오류 C2147 | Microsoft Docs"
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
  - "C2147"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2147"
ms.assetid: d1adb3bf-7ece-4815-922c-ad7492fb6670
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2147
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

구문 오류: 'identifier'은\(는\) 새 키워드입니다.  
  
 구문에 사용한 식별자가 새 버전의 언어에서는 키워드로 예약되어 있습니다.  
  
 다음 샘플에서는 C2147 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2147.cpp  
// compile with: /clr  
int main() {  
   int gcnew = 0;   // C2147  
   int i = 0;   // OK  
}  
```