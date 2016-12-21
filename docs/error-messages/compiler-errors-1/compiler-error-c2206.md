---
title: "컴파일러 오류 C2206 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2206"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2206"
ms.assetid: d7fba68b-aa28-4885-a9a0-27107358f066
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2206
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function': 형식 정의는 함수 정의에 사용할 수 없습니다.  
  
 `typedef`가 함수 형식을 정의하는 데 사용됩니다.  
  
 다음 샘플에서는 C2206을 생성합니다.  
  
```  
// C2206.cpp typedef int functyp(); typedef int MyInt; functyp func1 {};   // C2206 int main() { MyInt i = 0;   // OK }  
```