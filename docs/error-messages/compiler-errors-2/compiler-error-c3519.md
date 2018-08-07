---
title: 컴파일러 오류 C3519 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3519
dev_langs:
- C++
helpviewer_keywords:
- C3519
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 740fef32484164e7439335686adce0a4aa8027f6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257200"
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