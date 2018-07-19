---
title: 컴파일러 경고 (수준 1) C4939 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4939
dev_langs:
- C++
helpviewer_keywords:
- C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 459674bb4e6899563a18943f7ba510a6168d0e28
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296886"
---
# <a name="compiler-warning-level-1-c4939"></a>컴파일러 경고(수준 1) C4939
\#pragma vtordisp는 사용 되지 않으며 Visual c + +의 이후 릴리스에서 제거 될 예정  
  
 [vtordisp](../../preprocessor/vtordisp.md) pragma는 이후 Visual C++ 릴리스에서 제거될 예정입니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4939를 생성합니다.  
  
```  
// C4939.cpp  
// compile with: /c /W1  
#pragma vtordisp(off)   // C4939  
```