---
title: "컴파일러 오류 C3347 | Microsoft Docs"
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
  - "C3347"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3347"
ms.assetid: e939ad29-0b78-4681-9618-9bdae5675cee
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3347
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg': idl\_module 특성에 필수 인수를 지정하지 않았습니다.  
  
 필수 인수가 [idl\_module](../../windows/idl-module.md) 특성에 전달되지 않았습니다.  
  
 다음 샘플에서는 C3347을 생성합니다.  
  
```  
// C3347.cpp // compile with: /c [module(name="xx")]; [idl_module(dllname="x")];    // C3347 // try the following line instead // [idl_module(name="test", dllname="x")];  
```