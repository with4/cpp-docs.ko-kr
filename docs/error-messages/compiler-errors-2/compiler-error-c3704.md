---
title: "컴파일러 오류 C3704 | Microsoft Docs"
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
  - "C3704"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3704"
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3704
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': vararg 메서드는 이벤트를 발생시킬 수 없습니다.  
  
 vararg 메서드에 [\_\_event](../../cpp/event.md)를 사용하려고 했습니다.  이 오류를 해결하려면 다음 코드 샘플에서와 같이 `fireEvent(int i, ...)` 호출을 `fireEvent(int i)` 호출로 바꾸십시오.  
  
 다음 샘플에서는 C3704 오류가 발생하는 경우를 보여 줍니다.  
  
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