---
title: "컴파일러 경고 (수준 1) C4326 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4326"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4326"
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4326
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function'의 반환 형식이 'type1'이어야 하는데 'type2'입니다.  
  
 함수에서 ***type1***이 아닌 형식을 반환했습니다.  예를 들어, [\/Za](../../build/reference/za-ze-disable-language-extensions.md)를 사용했을 때 main에서 `int`를 반환하지 않았습니다.  
  
 다음 샘플에서는 C4326 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4326.cpp  
// compile with: /Za /W1  
char main()  
{   // C4326 try int main  
}  
```