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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 085bcc71284894e0fd75a7a95958e8959d9cb6cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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