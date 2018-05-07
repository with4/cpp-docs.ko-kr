---
title: 컴파일러 오류 C3704 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3704
dev_langs:
- C++
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b3b1f255852def5e04d75751b0a902fb7072545
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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