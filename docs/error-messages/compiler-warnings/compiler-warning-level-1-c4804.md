---
title: "컴파일러 경고 (수준 1) C4804 | Microsoft Docs"
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
  - "C4804"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4804"
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4804
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operation' : 연산에 'bool' 형식을 사용하는 것은 안전하지 않습니다.  
  
 이 경고는 `bool` 변수나 값을 예기치 않은 방법으로 사용한 경우 발생합니다.  예를 들어, 음의 단일 연산자\(**\-**\)나 보수 연산자\(`~`\)와 같은 연산자를 사용한 경우 C4804가 발생합니다.  컴파일러에서 식을 계산합니다.  
  
## 예제  
 다음 샘플에서는 C4804 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4804.cpp  
// compile with: /W1  
  
int main()  
{  
   bool i = true;  
   if (-i)   // C4804, remove the '-' to resolve  
   {  
      i = false;  
   }  
}  
```