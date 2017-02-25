---
title: "컴파일러 오류 C3062 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3062"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3062"
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3062
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'enum': 내부 형식이 'type'이므로 열거자에 값이 필요합니다.  
  
 열거형에는 내부 형식을 지정할 수 있습니다.  그러나 일부 형식에서는 각 열거자에 값을 할당해야 합니다.  
  
 열거형에 대한 자세한 내용은 [enum 클래스](../../windows/enum-class-cpp-component-extensions.md)를 참조하십시오.  
  
 다음 샘플에서는 C3062 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3062.cpp  
// compile with: /clr  
  
enum class MyEnum : bool { a };   // C3062  
enum class MyEnum2 : bool { a = true};   // OK  
```