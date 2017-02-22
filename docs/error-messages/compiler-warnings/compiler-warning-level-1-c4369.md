---
title: "컴파일러 경고 (수준 1) C4369 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4369"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4369"
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 컴파일러 경고 (수준 1) C4369
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'enumerator' :  열거자 값 'value'을\(를\) 'type'\(으\)로 나타낼 수 없습니다. 값은 'new\_value'입니다.  
  
 열거자 값을 계산한 결과가 지정된 내부 형식에 대한 최대값보다 큽니다.  이로 인해 오버플로가 발생하여 컴파일러에서 열거자 값을 해당 형식에 맞게 최대한 낮추어 래핑했습니다.  
  
## 예제  
 다음 샘플에서는 C4369 경고가 발생하는 경우를 보여 줍니다.  
  
```  
// C4369.cpp  
// compile with: /W1  
int main() {  
   enum Color: char { red = 0x7e, green, blue };   // C4369  
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK  
}  
```