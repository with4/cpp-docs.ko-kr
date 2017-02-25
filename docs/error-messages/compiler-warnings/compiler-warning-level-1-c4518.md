---
title: "컴파일러 경고 (수준 1) C4518 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4518"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4518"
ms.assetid: 4ad21004-f076-43fd-99f4-4bf1f9be4c0b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 경고 (수준 1) C4518
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'specifier' : 예기치 않은 저장소 클래스 또는 형식 지정자가 있으므로 무시됩니다.  
  
 다음 샘플에서는 C4518 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4518.cpp  
// compile with: /c /W1  
_declspec(dllexport) extern "C" void MyFunction();   // C4518  
  
extern "C" void MyFunction();   // OK  
```