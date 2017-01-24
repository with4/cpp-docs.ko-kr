---
title: "컴파일러 오류 C2705 | Microsoft Docs"
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
  - "C2705"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2705"
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2705
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'label' : 'exception handler block' 범위로 잘못 점프했습니다.  
  
 실행 부분이 `try`\/`catch`, `__try`\/`__except`, `__try`\/`__finally` 블록 내의 레이블로 점프합니다.  자세한 내용은 [예외 처리](../../cpp/exception-handling-in-visual-cpp.md)를 참조하십시오.  
  
 다음 샘플에서는 C2705 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2705.cpp  
int main() {  
goto trouble;  
   __try {  
      trouble: ;   // C2705  
   }  
   __finally {}  
  
   // try the following line instead  
   // trouble: ;  
}  
```