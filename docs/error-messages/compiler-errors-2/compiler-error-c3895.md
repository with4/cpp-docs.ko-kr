---
title: "컴파일러 오류 C3895 | Microsoft Docs"
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
  - "C3895"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3895"
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3895
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : type 데이터 멤버는 'volatile'이 될 수 없습니다.  
  
 [literal](../../windows/literal-cpp-component-extensions.md) 또는 [initonly](../../dotnet/initonly-cpp-cli.md)를 비롯한 특정 종류의 데이터 멤버는 [volatile](../../cpp/volatile-cpp.md)이 될 수 없습니다.  
  
 다음 샘플에서는 C3895 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3895.cpp  
// compile with: /clr  
ref struct Y1 {  
   initonly  
   volatile int data_var2;   // C3895  
};  
```