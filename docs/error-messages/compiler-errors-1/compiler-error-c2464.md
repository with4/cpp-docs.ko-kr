---
title: "컴파일러 오류 C2464 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2464"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2464"
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C2464
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'new'를 사용하여 참조를 할당할 수 없습니다.  
  
 참조 식별자가 `new` 연산자를 사용하여 할당되었습니다.  참조는 메모리 개체가 아니므로 `new`는 이에 대한 포인터를 반환할 수 없습니다.  표준 변수 선언 구문을 사용하여 참조를 선언하십시오.  
  
 다음 샘플에서는 C2464 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2464.cpp  
int main() {  
   new ( int& ir );   // C2464  
}  
```