---
title: "컴파일러 오류 C3747 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3747"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3747"
ms.assetid: a9a4be67-5d9c-4dcc-9ae9-baae46cbecde
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3747
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 type 매개 변수\(매개 변수 param\)가 없습니다.  
  
 매개 변수 목록에서 기본값을 사용하는 제네릭 또는 템플릿 매개 변수 다음에 기본값을 사용하지 않는 매개 변수가 올 수 없습니다.  
  
 다음 샘플에서는 C3747 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3747.cpp  
template <class T1 = int, class T2>   // C3747  
struct MyStruct {};  
```  
  
 다음과 같이 해결할 수 있습니다.  
  
```  
// C3747b.cpp  
// compile with: /c  
template <class T1, class T2 = int>  
struct MyStruct {};  
```