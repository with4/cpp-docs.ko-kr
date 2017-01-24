---
title: "컴파일러 오류 C3412 | Microsoft Docs"
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
  - "C3412"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3412"
ms.assetid: aa4dd43b-54ce-4cda-85c1-1a77dd6e34fa
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3412
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'template': 현재 범위에서 템플릿을 특수화할 수 없습니다.  
  
 템플릿은 전역 범위나 네임스페이스 범위에서만 특수화할 수 있고 클래스 범위에서는 특수화할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C3412 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3412.cpp  
template <class T>  
struct S {  
   template <>  
   struct S<int> {};   // C3412 in a class  
};  
```  
  
## 예제  
 다음 샘플에서는 가능한 해결 방법을 보여 줍니다.  
  
```  
// C3412b.cpp  
// compile with: /c  
template <class T>  
struct S {};  
  
template <>  
struct S<int> {};  
```