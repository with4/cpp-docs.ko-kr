---
title: "컴파일러 오류 C2013 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C2013
dev_langs:
- C++
helpviewer_keywords:
- C2013
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 23fdceda3b40a657301e8909c6847e9d596eb24d
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

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
