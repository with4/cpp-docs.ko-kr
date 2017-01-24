---
title: "컴파일러 오류 C2470 | Microsoft Docs"
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
  - "C2470"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2470"
ms.assetid: e17d2cb8-b84c-447c-976a-625f0c96f3fe
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2470
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : 함수 정의처럼 보이지만 매개 변수 목록이 없습니다. 명백한 본문을 건너뜁니다.  
  
 함수 정의에 해당 인수 목록이 없습니다.  
  
 다음 샘플에서는 C2470 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2470.cpp  
int MyFunc {};  // C2470  
void MyFunc2() {};  //OK  
  
int main(){  
   MyFunc();  
   MyFunc2();  
}  
```