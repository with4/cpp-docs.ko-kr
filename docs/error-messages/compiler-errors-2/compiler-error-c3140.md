---
title: "컴파일러 오류 C3140 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3140
dev_langs: C++
helpviewer_keywords: C3140
ms.assetid: 122f8943-fac3-4db8-a3a8-2c5d19233de6
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1ebc5b182b7f4ae70fa2f767fbeae0a51b0507e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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