---
title: "컴파일러 오류 C2706 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2706"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2706"
ms.assetid: e18da924-c42d-4b09-8e29-f4e0382d7dc6
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 오류 C2706
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

짝이 되는 \_\_try 없이 \_\_except를 잘못 사용했습니다. \_\_try 블록에 '}'가 빠진 것 같습니다.  
  
 컴파일러가 `__try` 블록의 닫는 중괄호를 찾지 못했습니다.  
  
 다음 샘플에서는 C2706 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2706.cpp  
int main() {  
   __try {  
      void f();  
   // C2706  } missing here  
   __except(GetExceptionCode() == 0x0) {  
   }  
}  
```