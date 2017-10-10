---
title: "컴파일러 오류 C2637 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2637
dev_langs:
- C++
helpviewer_keywords:
- C2637
ms.assetid: 58d94447-eb96-4d8f-a690-dd78d322462e
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: f676205e2850e411ddb5e5b996114c00c65087f2
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2637"></a>컴파일러 오류 C2637
'identifier': 데이터 멤버에 대 한 포인터를 수정할 수 없습니다  
  
 데이터 멤버에 대 한 포인터는 호출 규칙을 사용할 수 없습니다. 를 해결 하려면 호출 규칙을 제거 하거나 멤버 함수에 대 한 포인터를 선언 합니다.  
  
 다음 샘플에서는 C2637 오류가 생성 됩니다.  
  
```  
// C2637.cpp  
// compile with: /c  
struct S {};  
int __stdcall S::*pms1;   // C2637  
  
// OK  
int S::*pms2;  
int (__stdcall S::*pms3)(...);  
```
