---
title: "컴파일러 오류 C2433 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2433"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2433"
ms.assetid: 7079fedd-6059-4125-82ef-ebe275f1f9d1
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C2433
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 데이터 선언에 'modifier'을\(를\) 사용할 수 없습니다.  
  
 데이터 선언에는 `friend`, `virtual` 및 `inline` 한정자를 사용할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C2433 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2433.cpp  
class C{};  
  
int main() {  
   inline C c;   // C2433  
}  
```