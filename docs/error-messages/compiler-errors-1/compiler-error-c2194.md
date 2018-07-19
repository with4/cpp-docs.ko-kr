---
title: 컴파일러 오류 C2194 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2194
dev_langs:
- C++
helpviewer_keywords:
- C2194
ms.assetid: df6e631c-0062-4844-9088-4cc7a0ff879f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 61a2ca45df170245fae0795adc006349c1b62fb2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169246"
---
# <a name="compiler-error-c2194"></a>컴파일러 오류 C2194
'identifier': 텍스트 세그먼트입니다  
  
 `data_seg` pragma를 함께 사용 하는 세그먼트 이름 사용 `code_seg`합니다.  
  
 다음 샘플에서는 C2194 오류가 생성 됩니다.  
  
```  
// C2194.cpp  
// compile with: /c  
#pragma code_seg("MYCODE")  
#pragma data_seg("MYCODE")   // C2194  
#pragma data_seg("MYCODE2")   // OK  
```