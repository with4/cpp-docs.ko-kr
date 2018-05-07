---
title: 컴파일러 경고 (수준 1) C4606 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4606
dev_langs:
- C++
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf9f0a954b48e2c8bd036651efa3e8a3e65b8e68
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4606"></a>컴파일러 경고(수준 1) C4606
\#pragma 경고: 'warning_number'가 무시 됩니다. 코드 분석 경고가 경고 수준과 연결 되어 있지 않습니다.  
  
 코드 분석 경고만 대 한 `error`, `once`, 및 `default` 지원 되는 [경고](../../preprocessor/warning.md) pragma입니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4606 오류가 발생 합니다.  
  
```  
// C4606.cpp  
// compile with: /c /W1  
#pragma warning(1: 6001)   // C4606  
#pragma warning(once: 6001)   // OK  
```