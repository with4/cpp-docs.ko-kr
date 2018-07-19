---
title: 컴파일러 경고 (수준 1) C4227 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4227
dev_langs:
- C++
helpviewer_keywords:
- C4227
ms.assetid: 78f98374-c00b-4000-aefa-1b1c67b4666b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0f3c0cced0e27d3f981c30251d4b9e1d78169559
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33273591"
---
# <a name="compiler-warning-level-1-c4227"></a>컴파일러 경고(수준 1) C4227
사용 하는 오래 된 구문: 참조의 한정자는 무시 됩니다.  
  
 같은 한정자를 사용 하 여 `const` 또는 `volatile` 은 쿼리로 c + + 참조를 사용 합니다.  
  
## <a name="example"></a>예제  
  
```  
// C4227.cpp  
// compile with: /W1 /c  
int j = 0;  
int &const i = j;   // C4227  
```