---
title: 컴파일러 경고 (수준 1) C4141 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4141
dev_langs:
- C++
helpviewer_keywords:
- C4141
ms.assetid: 6ce8c058-7f4c-41cf-93e7-90a466744656
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6580557a5713bc7f7faf5e0e086081dcc156d5af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4141"></a>컴파일러 경고(수준 1) C4141
'modifier': 두 번 이상 사용했습니다.  
  
## <a name="example"></a>예제  
  
```  
// C4141.cpp  
// compile with: /W1 /LD  
inline inline void func ();   // C4141  
```