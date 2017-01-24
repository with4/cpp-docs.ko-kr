---
title: "컴파일러 오류 C2665 | Microsoft Docs"
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
  - "C2665"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2665"
ms.assetid: a7f99b61-2eae-4f2b-ba75-ea68fd1e8312
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2665
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': number1개의 오버로드 모두 number2번째 매개 변수를 'type' 형식으로부터 변환할 수 없습니다.  
  
 오버로드된 함수의 매개 변수를 필수 형식으로 변환할 수 없습니다.  다음과 같이 해결할 수 있습니다.  
  
-   변환 연산자를 제공합니다.  
  
-   명시적 변환을 사용합니다.  
  
## 예제  
 다음 샘플에서는 C2665 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2665.cpp  
void func(short, char*){}  
void func(char*, char*){}  
  
int main() {  
   func(0, 1);   // C2665  
   func((short)0, (char*)1);   // OK  
}  
```