---
title: "컴파일러 오류 C2530 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2530"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2530"
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2530
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 참조를 초기화해야 합니다.  
  
 참조가 선언되어 있지 않으면 다음 방법으로 선언할 때 초기화해야 합니다.  
  
-   [extern](../../cpp/using-extern-to-specify-linkage.md) 키워드를 사용하여 초기화  
  
-   클래스, 구조체 또는 공용 구조체의 멤버로서 초기화\(생성자에서 초기화\)  
  
-   함수 선언 또는 정의에 매개 변수로서 초기화  
  
-   함수의 반환 형식으로서 초기화  
  
 다음 샘플에서는 C2530 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2530.cpp  
int main() {  
   int i = 0;  
   int &j;   // C2530  
   int &k = i;   // OK  
}  
```