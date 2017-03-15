---
title: "컴파일러 경고 (수준 1) C4353 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4353"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4353"
ms.assetid: 6e79f186-ed82-4c95-9923-0ad5bb9c4db1
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4353
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

비표준 확장을 사용했습니다. 함수 식으로 상수 0을 사용했습니다.'\_\_noop' 내장 함수를 대신 사용하십시오.  
  
 상수 0을 함수 식에 사용할 수 없습니다.  자세한 내용은 [\_\_noop](../../intrinsics/noop.md)를 참조하십시오.  
  
 다음 샘플에서는 C4353 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4353.cpp  
// compile with: /W1  
void MyPrintf(void){};  
#define X 0  
#if X  
   #define DBPRINT MyPrint  
#else  
   #define DBPRINT 0   // C4353 expected  
#endif  
int main(){  
DBPRINT();  
}  
```