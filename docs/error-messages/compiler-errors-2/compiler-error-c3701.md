---
title: "컴파일러 오류 C3701 | Microsoft Docs"
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
  - "C3701"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3701"
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3701
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 이벤트 소스에 이벤트가 없습니다.  
  
 이벤트 메서드가 없는 클래스에서 [event\_source](../../windows/event-source.md)를 사용하려고 했습니다.  이 오류를 해결하려면 클래스에 이벤트를 하나 이상 추가하십시오.  
  
 다음 샘플에서는 C3701 오류가 발생하는 경우를 보여 줍니다.  
  
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