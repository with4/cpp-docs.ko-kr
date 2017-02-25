---
title: "컴파일러 오류 C2467 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2467"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2467"
ms.assetid: f9ead270-5d0b-41cc-bdcd-586a647c67a7
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2467
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

익명 'user\-defined\-type' 선언은 올바르지 않습니다.  
  
 중첩된 사용자 정의 형식이 선언되었습니다.  이 오류는 ANSI 규격 옵션\([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\)이 활성화된 상태에서 C 소스 코드를 컴파일할 경우에 발생합니다.  
  
 다음 샘플에서는 C2467 오류가 발생하는 경우를 보여 줍니다.  
  
```  
//C2467.c  
// compile with: /Za   
int main() {  
   struct X {  
      union { int i; };   // C2467, nested declaration  
   };  
}  
```