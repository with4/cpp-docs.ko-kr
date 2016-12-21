---
title: "컴파일러 경고 (수준 1) C4142 | Microsoft Docs"
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
  - "C4142"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4142"
ms.assetid: 1fdfc3dc-60a2-4f00-b133-20e400f9b7a6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4142
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 재정의가 약합니다.  
  
 생성되는 코드에 영향을 주지 않는 방식으로 형식이 재정의됩니다.  
  
 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
-   파생 클래스의 멤버 함수에 대한 반환 형식이 기본 클래스의 대응하는 멤버 함수의 반환 형식과 다릅니다.  
  
-   `typedef` 명령으로 정의한 형식이 다른 구문을 사용하여 재정의되었습니다.  
  
 다음 샘플에서는 C4142 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4142.c  
// compile with: /W1  
float X2;  
X2 = 2.0 + 1.0;   // C4142  
  
int main() {  
   float X2;  
   X2 = 2.0 + 1.0;   // OK  
}  
```