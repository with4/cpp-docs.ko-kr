---
title: "컴파일러 경고 (수준 3) C4800 | Microsoft Docs"
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
  - "C4800"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4800"
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 3) C4800
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : 'true' 또는 'false'로 bool 값을 강제하고 있습니다\(성능 경고\).  
  
 이 경고는 `bool`이 아닌 값을 할당하거나 `bool` 형식으로 강제 변환할 때 발생합니다.  일반적으로 이 메시지는 **true**와 **false** 값만 있는 `int` 변수를 `bool` 변수에 할당할 때 발생하며 이 경우 `int` 변수를 `bool` 형식으로 다시 선언할 수 있습니다.  `bool` 형식을 사용하여 식을 다시 작성할 수 없으면 "`!=0`"를 식에 추가하여 `bool` 형식을 제공합니다.  식을 `bool` 형식으로 캐스팅해도 경고가 발생하도록 설계되었습니다.  
  
 다음 샘플에서는 C4800 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4800.cpp  
// compile with: /W3  
int main() {  
   int i = 0;  
  
   // try..  
   // bool i = 0;  
  
   bool j = i;   // C4800  
   j++;  
}  
```