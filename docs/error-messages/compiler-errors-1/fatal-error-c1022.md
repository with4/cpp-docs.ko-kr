---
title: 심각한 오류 C1022 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1022
dev_langs:
- C++
helpviewer_keywords:
- C1022
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4a6ec241a9a8e175d542b1f3b9db9ea1cdc3ba0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1022"></a>심각한 오류 C1022
#endif가 필요합니다.  
  
 `#if`, `#ifdef`또는 `#ifndef` 지시문에 일치하는 `#endif` 지시문이 없습니다. 각 `#if`, `#ifdef`또는 `#ifndef` 에 일치하는 `#endif`가 있어야 합니다.  
  
 다음 샘플에서는 C1022를 생성합니다.  
  
```  
// C1022.cpp  
#define true 1  
  
#if (true)  
#else   
#else    // C1022  
```  
  
 해결 방법:  
  
```  
// C1022b.cpp  
// compile with: /c  
#define true 1  
  
#if (true)  
#else   
#endif  
```