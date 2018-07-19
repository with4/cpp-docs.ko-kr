---
title: 컴파일러 오류 C2142 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2142
dev_langs:
- C++
helpviewer_keywords:
- C2142
ms.assetid: d0dbe10e-0952-49a4-8b33-e82fb7558b19
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11fd3cd62b236daa93424f53a0896888a89fe33d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170400"
---
# <a name="compiler-error-c2142"></a>컴파일러 오류 C2142
함수 선언이 다릅니다. 둘 중 하나에 지정  
  
 하나의 함수 선언에는 가변 매개 변수 목록을 포함합니다. 다른 선언 하지 않습니다. ANSI C ([/Za](../../build/reference/za-ze-disable-language-extensions.md))만 있습니다.  
  
 다음 샘플에서는 C2142 오류가 생성 됩니다.  
  
```  
// C2142.c  
// compile with: /Za /c  
void func();  
void func( int, ... );   // C2142  
void func2( int, ... );   // OK  
```