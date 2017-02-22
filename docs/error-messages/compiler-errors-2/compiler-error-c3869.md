---
title: "컴파일러 오류 C3869 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3869"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3869"
ms.assetid: 85b2ad72-95c1-4ed6-9761-6ef66c3802b7
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# 컴파일러 오류 C3869
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

gcnew 제약 조건에 빈 매개 변수 목록 '\(\)'가 없습니다.  
  
 `gcnew` 특수 제약 조건을 빈 매개 변수 목록 없이 지정했습니다.  자세한 내용은 [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3869 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3869.cpp  
// compile with: /c /clr  
using namespace System;  
generic <typename T>  
where T : gcnew   // C3869  
// try the following line instead  
// where T : gcnew()  
ref class List {};  
```