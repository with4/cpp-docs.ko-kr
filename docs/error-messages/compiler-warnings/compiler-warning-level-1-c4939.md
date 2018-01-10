---
title: "컴파일러 경고 (수준 1) C4939 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4939
dev_langs: C++
helpviewer_keywords: C4939
ms.assetid: 07096008-ba47-436c-a84c-2b03ad90d0b3
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2714963f2b6538805e2352ccb96a19f01f843e73
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4939"></a>컴파일러 경고(수준 1) C4939
\#pragma vtordisp는 사용 되지 않으며 Visual c + +의 이후 릴리스에서 제거 될 예정  
  
 [vtordisp](../../preprocessor/vtordisp.md) pragma는 이후 Visual C++ 릴리스에서 제거될 예정입니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4939를 생성합니다.  
  
```  
// C4939.cpp  
// compile with: /c /W1  
#pragma vtordisp(off)   // C4939  
```