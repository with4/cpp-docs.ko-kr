---
title: "컴파일러 오류 C2714 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2714"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2714"
ms.assetid: 401a5a42-660c-4bad-9d63-1a2d092bc489
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C2714
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\_\_alignof\(void\)은\(는\) 사용할 수 없습니다.  
  
 잘못된 값을 연산자에 전달했습니다.  
  
 자세한 내용은 [\_\_alignof 연산자](../../cpp/alignof-operator.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C2714 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2714.cpp  
int main() {  
   return __alignof(void);   // C2714  
   return __alignof(char);   // OK  
}  
```