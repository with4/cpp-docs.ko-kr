---
title: "심각한 오류 C1020 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1020
dev_langs:
- C++
helpviewer_keywords:
- C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c2689b2526b2cf9dc513052e292aca429113c129
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1020"></a>심각한 오류 C1020
예기치 않은 #endif입니다.  
  
 `#endif` 지시문에 일치하는 `#if`, `#ifdef`또는 `#ifndef` 지시문이 없습니다. 각 `#endif` 에 일치하는 지시문이 있어야 합니다.  
  
 다음 샘플에서는 C1020을 생성합니다.  
  
```  
// C1020.cpp  
#endif     // C1020  
```  
  
 해결 방법:  
  
```  
// C1020b.cpp  
// compile with: /c  
#if 1  
#endif  
```
