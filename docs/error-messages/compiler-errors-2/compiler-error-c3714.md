---
title: "컴파일러 오류 C3714 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3714
dev_langs: C++
helpviewer_keywords: C3714
ms.assetid: 17718f75-5a37-4e42-912b-487e91008a95
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7d58e06d99975fd4ccff9ea4bace755ff1d758cb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3714"></a>컴파일러 오류 C3714
'method': '이벤트 처리기 메서드 같은 호출 규칙 소스로 method' 해야  
  
 원본 이벤트 메서드와 같은 호출 규칙을 사용 하지 않은 이벤트 처리기 메서드를 정의 합니다. 이 오류를 해결 하려면 이벤트 처리기 메서드를 소스 이벤트 메서드와와 동일한 호출 규칙을 부여 합니다. 예를 들어 아래 코드에서의 호출 규칙을 확인 `handler1` 및 `event1` 일치 ([__cdecl](../../cpp/cdecl.md) 또는 [__stdcall](../../cpp/stdcall.md) 나 다른 사용자). 제거 규칙 키워드 선언 모두에서 호출 하 여 문제가 해결 및도 발생 `event1` 및 `handler1` 을 기본값으로 설정 된 [thiscall](../../cpp/thiscall.md) 호출 규칙입니다. 참조 [호출 규칙](../../cpp/calling-conventions.md) 자세한 정보에 대 한 합니다.  
  
 다음 샘플에서는 C3714 오류가 생성 됩니다.  
  
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