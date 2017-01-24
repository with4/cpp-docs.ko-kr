---
title: "컴파일러 오류 C3745 | Microsoft Docs"
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
  - "C3745"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3745"
ms.assetid: 1e64aec5-7e53-47e5-bc7d-3905230cfc66
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3745
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 이벤트만 'raised'일 수 있습니다.  
  
 [\_\_event](../../cpp/event.md) 키워드를 사용해서 정의한 함수만 [\_\_raise](../../cpp/raise.md) 키워드에 전달할 수 있습니다.  
  
 다음 샘플에서는 C3745 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3745.cpp  
struct E {  
   __event void func();  
   void func(int) {  
   }  
  
   void func2() {  
   }  
  
   void bar() {  
      __raise func();  
      __raise func(1);   // C3745  
      __raise func2();   // C3745  
   }  
};  
  
int main() {  
   E e;  
   __raise e.func();  
   __raise e.func(1);   // C3745  
   __raise e.func2();   // C3745  
}  
```