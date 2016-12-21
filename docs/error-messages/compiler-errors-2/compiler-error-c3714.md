---
title: "컴파일러 오류 C3714 | Microsoft Docs"
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
  - "C3714"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3714"
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3714
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'method': 이벤트 처리기 메서드는 'method' 소스와 같은 호출 규칙을 사용해야 합니다.  
  
 소스 이벤트 메서드와 동일한 호출 규칙을 사용하지 않는 이벤트 처리기 메서드를 정의했습니다.  이 오류를 해결하려면 이벤트 처리기 메서드에 소스 이벤트 메서드와 동일한 호출 규칙을 제공하십시오.  예를 들어, 아래 코드에서 `handler1`과 `event1`의 호출 규칙을 일치시키십시오\([\_\_cdecl](../../cpp/cdecl.md) 또는 [\_\_stdcall](../../cpp/stdcall.md) 또는 다른 호출 규칙\).  두 선언 모두에서 호출 규칙 키워드를 제거하면 문제가 해결되며 `event1`과 `handler1` 호출 규칙이 기본적으로 [thiscall](../../cpp/thiscall.md)로 정의됩니다.  자세한 내용은 [변환](../../cpp/calling-conventions.md)을 참조하십시오.  
  
 다음 샘플에서는 C3714 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3714.cpp  
// compile with: /c  
// processor: x86  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void __cdecl event1();  
   // try the following line instead  
   // __event void __stdcall event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void __stdcall handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3714  
   }  
  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3714  
   }  
};  
```