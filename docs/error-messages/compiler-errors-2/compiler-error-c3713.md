---
title: "컴파일러 오류 C3713 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3713
dev_langs: C++
helpviewer_keywords: C3713
ms.assetid: 75c6b9b6-955b-49bd-9bc8-ced88b496a1f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: da0ff1089166974830c12a588d85d6c09f068814
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3713"></a>컴파일러 오류 C3713
'method': 이벤트 처리기 메서드는 동일한 함수 매개 변수가 있어야 소스로 'method'  
  
 원본 이벤트 메서드와 동일한 매개 변수를 사용 하지 않은 이벤트 처리기 메서드를 정의 합니다. 이 오류를 해결 하려면 이벤트 처리기 메서드에 동일한 매개 변수 원본 이벤트 메서드를 제공 합니다.  
  
 다음 샘플에서는 C3713 오류가 생성 됩니다.  
  
```  
// C3713.cpp  
// compile with: /c  
[event_source(native)]  
class CEventSrc {  
public:  
   __event void event1(int nValue);  
   // try the following line instead  
   // __event void event1();  
};  
  
[event_receiver(native)]  
class CEventRec {  
public:  
   void handler1() {}  
  
   void HookEvents(CEventSrc* pSrc) {  
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3713  
   }  
  
   void UnhookEvents(CEventSrc* pSrc) {  
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1); // C3713  
   }  
};  
```