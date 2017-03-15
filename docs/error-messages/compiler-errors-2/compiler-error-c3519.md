---
title: "컴파일러 오류 C3519 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3519"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3519"
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3519
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'invalid\_param' : embedded\_idl 특성에 대한 매개 변수가 잘못되었습니다.  
  
 [\#import](../../preprocessor/hash-import-directive-cpp.md)의 `embedded_idl` 특성에 매개 변수를 전달했지만 컴파일러에서 이 매개 변수를 인식하지 못했습니다.  
  
 `embedded_idl`에 사용할 수 있는 매개 변수는 `emitidl`과 `no_emitidl`뿐입니다.  
  
 다음 샘플에서는 C3519 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3519.cpp  
// compile with: /LD  
[module(name="MyLib2")];  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")     
// C3519  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")     
// OK  
```