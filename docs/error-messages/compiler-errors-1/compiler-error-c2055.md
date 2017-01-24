---
title: "컴파일러 오류 C2055 | Microsoft Docs"
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
  - "C2055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2055"
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

형식 목록이 아니라 형식 매개 변수 목록이 와야 합니다.  
  
 함수 정의에는 형식 매개 변수 목록 대신 매개 변수 형식 목록이 포함되어 있습니다.  형식 매개 변수가 쓸모 없거나 줄임표\(`...`\)가 아닌 한 ANSI C에서 형식 매개 변수를 명명해야 합니다.  
  
 다음 샘플에서는 C2055 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2055.c  
// compile with: /c  
void func(int, char) {}  // C2055  
void func (int i, char c) {}   // OK  
```