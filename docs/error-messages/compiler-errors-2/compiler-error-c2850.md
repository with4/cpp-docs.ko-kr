---
title: "컴파일러 오류 C2850 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2850
dev_langs: C++
helpviewer_keywords: C2850
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22e6f77d843c0545dcb148a1adf74c050c5fbe3d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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