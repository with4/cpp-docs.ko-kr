---
title: 컴파일러 오류 C3140 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3140
dev_langs:
- C++
helpviewer_keywords:
- C3140
ms.assetid: 122f8943-fac3-4db8-a3a8-2c5d19233de6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c2c8c9e47020fe53e87b985b5db6192cd26098fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33246906"
---
# <a name="compiler-error-c3140"></a>컴파일러 오류 C3140
같은 컴파일 단위에서 여러 개의 'module' 특성을 가질 수 없습니다.  
  
 [모듈](../../windows/module-cpp.md) 특성만 정의 될 수 한 번 프로젝트 마다.  
  
 다음 샘플에서는 C3140 오류가 생성 됩니다.  
  
```  
// C3140.cpp  
// compile with: /c  
[emitidl];  
[module(name = "MyLibrary")];  
[module(name = "MyLibrary2")];   // C3140  
```