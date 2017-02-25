---
title: "컴파일러 오류 C2833 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2833"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2833"
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2833
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator operator'은\(는\) 인식할 수 있는 연산자 또는 형식이 아닙니다.  
  
 `operator`라는 단어 다음에는 재정의할 연산자나 변환할 형식이 와야 합니다.  
  
 관리되는 형식으로 정의할 수 있는 연산자의 목록은 [사용자 정의 연산자](../../dotnet/user-defined-operators-cpp-cli.md)를 참조하십시오.  
  
 다음 샘플에서는 C2833 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2833.cpp  
// compile with: /c  
class A {};  
  
void operator ::* ();   // C2833  
void operator :: ();   // OK  
```