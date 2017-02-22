---
title: "컴파일러 오류 C2785 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2785"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2785"
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C2785
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration1' 및 'declaration2'의 반환 형식이 다릅니다.  
  
 함수 템플릿 특수화의 반환 형식이 기본 함수 템플릿의 반환 형식과 다릅니다.  
  
### 이 오류를 해결하려면  
  
1.  함수 템플릿의 모든 특수화가 일치하는지 확인하십시오.  
  
## 예제  
 다음 샘플에서는 C2785 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2785.cpp  
// compile with: /c  
template<class T> void f(T);  
  
template<> int f(int); // C2785  
template<> void f(int); // OK  
```