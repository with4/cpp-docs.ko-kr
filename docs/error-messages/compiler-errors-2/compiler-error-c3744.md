---
title: "컴파일러 오류 C3744 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3744"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3744"
ms.assetid: a447d050-80d1-406a-9a6e-f15c527d717c
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C3744
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

관리되는 이벤트의 경우 \_\_unhook를 사용하려면 인수가 적어도 3개는 있어야 합니다.  
  
 [\_\_unhook](../../cpp/unhook.md) 함수는 Managed Extensions for C\+\+에 대해 컴파일된 프로그램에서 사용될 경우에 매개 변수를 세 개 사용해야 합니다.  
  
 `__hook` 및 `__unhook`는 \/clr 프로그래밍에 사용할 수 없습니다.  \+\= 및 \-\= 연산자를 대신 사용하십시오.  
  
 C3744는 **\/clr:oldSyntax**를 사용하는 경우에만 발생합니다.  
  
 다음 샘플에서는 C3744 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3744.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
public __delegate void delegate1();  
  
[ event_source(managed) ]  
public __gc class CPSource {  
public:  
   __event delegate1* event1;  
};  
  
[event_receiver(managed)]  
public __gc class CReceiver {  
public:  
   void Handler1() {  
   }  
  
   void UnhookAll1(CPSource* pSrc, CReceiver* pRec) {  
      pRec;  
      __unhook(pSrc);   // C3744  
      // The following line resolves the error.  
      // __unhook(&CPSource::event1, pSrc, &CReceiver::Handler1);  
   }  
};  
  
int main() {  
}  
```