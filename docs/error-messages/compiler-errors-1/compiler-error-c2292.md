---
title: 컴파일러 오류 C2292 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2292
dev_langs:
- C++
helpviewer_keywords:
- C2292
ms.assetid: 256b392f-2b8f-4162-b578-e7633984e162
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be3d00af54709d697461a8424041769aed9956e1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171359"
---
# <a name="compiler-error-c2292"></a>컴파일러 오류 C2292
'identifier': 최적 case 상속 표현: 'representation1' 'representation2'가 필요 하지만 선언  
  
 다음 코드를 컴파일할 [/vmb](../../build/reference/vmb-vmg-representation-method.md) ("최적 항상" 표현) C2292 발생 합니다.  
  
```  
// C2292.cpp  
// compile with: /vmb  
class __single_inheritance X;  
  
struct A { };  
struct B { };  
struct X : A, B { };  // C2292, X uses multiple inheritance  
```