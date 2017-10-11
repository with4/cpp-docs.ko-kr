---
title: "컴파일러 오류 C3701 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3701
dev_langs:
- C++
helpviewer_keywords:
- C3701
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 723deeb35dc16aff4535c1961261ba705f8ee364
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3701"></a>컴파일러 오류 C3701
'function': event_source에 이벤트가 없습니다  
  
 사용 하려는 [event_source](../../windows/event-source.md) 메서드가 없으므로 이벤트 클래스에 있습니다. 이 오류를 해결 하려면 하나 이상의 이벤트 클래스에 추가 합니다.  
  
 다음 샘플에서는 C3701 오류가 생성 됩니다.  
  
```  
// C3701.cpp  
[ event_source(native) ]  
class CEventSrc {  
public:  
   // uncomment the following line to resolve this C3701  
   // __event void fireEvent(int i);  
};   // C3701  
  
int main() {  
}  
```
