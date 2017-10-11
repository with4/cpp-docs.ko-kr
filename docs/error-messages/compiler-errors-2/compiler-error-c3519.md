---
title: "컴파일러 오류 C3519 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3519
dev_langs:
- C++
helpviewer_keywords:
- C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c655c8ba0513bcf25d5bc9666d65352a7f587374
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3519"></a>컴파일러 오류 C3519
'invalid_param': embedded_idl 특성에 잘못 된 매개 변수  
  
 에 전달 된 매개 변수는 `embedded_idl` 특성 [#import](../../preprocessor/hash-import-directive-cpp.md), 하지만 컴파일러가 매개 변수를 인식 하지 않았습니다.  
  
 에 허용 되는 유일한 매개 변수 `embedded_idl` 는 `emitidl` 및 `no_emitidl`합니다.  
  
 다음 샘플에서는 C3519 오류가 생성 됩니다.  
  
```  
// C3519.cpp  
// compile with: /LD  
[module(name="MyLib2")];  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")     
// C3519  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")     
// OK  
```
