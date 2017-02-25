---
title: "컴파일러 경고 (수준 1) C4183 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4183"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4183"
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 경고 (수준 1) C4183
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 반환 형식이 없습니다. 'int'를 반환하는 멤버 함수로 간주됩니다.  
  
 클래스 또는 구조체의 멤버 함수에 대한 인라인 정의는 반환 형식을 사용하지 않습니다.  이 멤버 함수는 기본 반환 형식인 `int`를 사용하는 것으로 간주됩니다.  
  
 다음 샘플에서는 C4183 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4183.cpp  
// compile with: /W1 /c  
#pragma warning(disable : 4430)  
class MyClass1;  
class MyClass2 {  
   MyClass1() {};   // C4183  
};  
```