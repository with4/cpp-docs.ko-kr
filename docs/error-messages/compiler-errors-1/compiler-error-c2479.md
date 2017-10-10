---
title: "컴파일러 오류 C2479 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2479
dev_langs:
- C++
helpviewer_keywords:
- C2479
ms.assetid: c74c7869-e65b-4ca1-b6fa-eb39fed4458a
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fef1f43a82d039377b3259ae06cd9650a3cc9db4
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2479"></a>컴파일러 오류 C2479
'identifier': 'allocate ()'는 정적 범위의 데이터 항목에 대 한 유효한만  
  
 `__declspec( allocate())` 구문을 정적 데이터에만 사용할 수 있습니다.  
  
 다음 샘플에서는 C2479 오류가 생성 됩니다.  
  
```  
// C2479.cpp  
// compile with: /c  
#pragma section("mycode", read)  
static __declspec(allocate("mycode")) void DoNothing() {}   // C2479  
__declspec(allocate("mycode"))  int i = 0;   // OK  
```
