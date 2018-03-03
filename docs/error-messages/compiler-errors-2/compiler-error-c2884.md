---
title: "컴파일러 오류 C2884 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2884
dev_langs:
- C++
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 72fdf38e9aa2ec01a4ee8018cc24f526b2a144da
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2884"></a>컴파일러 오류 C2884
'name': 'function' 지역 함수와 충돌 using 선언으로 인해  
  
 함수를 두 번 이상 정의 하려고 했습니다. 첫 번째 정의 로컬 정의입니다. 포함 된 네임 스페이스에서 두 번째는는 `using` 선언 합니다.  
  
 다음 샘플에서는 C2884 오류가 생성 됩니다.  
  
```  
// C2884.cpp  
namespace A {  
   void z(int);  
}  
  
void f() {  
   void z(int);  
   using A::z;   // C2884 z is already defined  
}  
```