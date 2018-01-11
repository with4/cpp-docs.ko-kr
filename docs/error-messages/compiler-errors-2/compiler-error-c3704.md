---
title: "컴파일러 오류 C3704 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3704
dev_langs: C++
helpviewer_keywords: C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 720af3b0ae1fa0727041e03e1573fbba4dccfae5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3704"></a>컴파일러 오류 C3704
'function': vararg 메서드 이벤트를 발생 시킬 수 없습니다  
  
 사용 하려는 [__event](../../cpp/event.md) vararg 메서드에서만 합니다. 이 오류를 해결 하려면 대체는 `fireEvent(int i, ...)` 하 여 호출 된 `fireEvent(int i)` 다음 코드 예제와 같이 호출 합니다.  
  
 다음 샘플에서는 C3704 오류가 생성 됩니다.  
  
```  
// C3704.cpp  
[ event_source(native) ]  
class CEventSrc {  
   public:  
      __event void fireEvent(int i, ...);   // C3704  
      // try the following line instead:  
      // __event void fireEvent(int i);  
};  
  
int main() {  
}  
```