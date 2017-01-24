---
title: "컴파일러 경고 (수준 1) C4600 | Microsoft Docs"
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
  - "C4600"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4600"
ms.assetid: f023a2a1-7fc4-463f-a434-dc93fcd3f4e9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4600
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma 'macro name' : 비어 있지 않은 유효한 문자열이 필요합니다.  
  
 [pop\_macro](../../preprocessor/pop-macro.md) 또는 [push\_macro](../../preprocessor/push-macro.md)를 사용하여 매크로 이름을 저장하거나 설정할 때에는 빈 문자열을 지정할 수 없습니다.  
  
 다음 샘플에서는 C4600 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4600.cpp  
// compile with: /W1  
int main()  
{  
   #pragma push_macro("")   // C4600 passing an empty string  
}  
```