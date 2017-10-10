---
title: "컴파일러 오류 C2850 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2850
dev_langs:
- C++
helpviewer_keywords:
- C2850
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ac2619417a55d5125863eb7ffd7ef45e09a2d742
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2850"></a>컴파일러 오류 C2850
'construct': 파일 범위 에서만 사용할 수 중첩된 된 구문에 사용할 수 없습니다.  
  
 구문 예: 일부 pragma는 전역 범위에만 사용할 수 있습니다.  
  
 다음 샘플에서는 C2850 오류가 생성 됩니다.  
  
```  
// C2850.cpp  
// compile with: /c /Yc  
// try the following line instead  
// #pragma hdrstop  
namespace X {  
   #pragma hdrstop   // C2850  
};  
```
