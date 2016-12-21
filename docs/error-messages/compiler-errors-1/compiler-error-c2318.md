---
title: "컴파일러 오류 C2318 | Microsoft Docs"
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
  - "C2318"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2318"
ms.assetid: 169e30b9-df78-46cb-90bf-576ad3c32fd4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2318
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 catch 처리기와 관련된 try 블록이 없습니다.  
  
 `catch` 처리기가 정의되어 있지만 `try` 블록 앞에 오지 않습니다.  
  
 다음 샘플에서는 C2318을 생성합니다.  
  
```  
// C2318.cpp // compile with: /EHsc #include <eh.h> int main() { // no try block catch( int ) {}   // C2318 }  
```  
  
 해결 방법:  
  
```  
// C2318b.cpp // compile with: /EHsc #include <eh.h> int main() { try{} catch( int ) {} }  
```