---
title: 컴파일러 오류 C2289 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2289
dev_langs:
- C++
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d351bffc33fc754ffcb66d2428a77fb040089a3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2289"></a>컴파일러 오류 C2289
동일한 형식 한정자를 두 번 이상 사용했습니다.  
  
 형식 선언 또는 정의에서 형식 한정자(`const`, `volatile`, `signed`또는 `unsigned`)를 두 번 이상 사용하여 ANSI 호환성(**/Za**)에서 오류가 발생합니다.  
  
 다음 샘플에서는 C2286을 생성합니다.  
  
```  
// C2289.cpp  
// compile with: /Za /c  
volatile volatile int i;   // C2289  
volatile int j;   // OK  
```