---
title: 컴파일러 오류 C2013 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2013
dev_langs:
- C++
helpviewer_keywords:
- C2013
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 53265c27bbac02ddbccb3b2a89b77a515e752f73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33163753"
---
# <a name="compiler-error-c2013"></a>컴파일러 오류 C2013
'>'가 없습니다.  
  
 `#include` 지시문에 닫는 꺾쇠 괄호가 없습니다. 오류를 해결하려면 닫는 대괄호를 추가합니다.  
  
 다음 샘플에서는 C2013을 생성합니다.  
  
```  
// C2013.cpp  
#include <stdio.h    // C2013  
```  
  
 해결 방법:  
  
```  
// C2013b.cpp  
// compile with: /c  
#include <stdio.h>  
```