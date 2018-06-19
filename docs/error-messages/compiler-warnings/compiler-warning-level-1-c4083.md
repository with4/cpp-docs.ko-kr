---
title: 컴파일러 경고 (수준 1) C4083 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4083
dev_langs:
- C++
helpviewer_keywords:
- C4083
ms.assetid: e7d3344e-5645-4d56-8460-d1acc9145ada
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a0d0d7baa0e521484841c638cef4332001a65e78
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277682"
---
# <a name="compiler-warning-level-1-c4083"></a>컴파일러 경고 (수준 1) C4083
'token'; 필요합니다. 'identifier' 식별자가 발견  
  
 식별자에 잘못 된 위치에서 발생 한 **#pragma** 문.  
  
## <a name="example"></a>예제  
  
```  
// C4083.cpp  
// compile with: /W1 /LD  
#pragma warning disable:4083    // C4083  
#pragma warning(disable:4083)   //correct  
```  
  
 구문을 검사는 [#pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) 지시문입니다.