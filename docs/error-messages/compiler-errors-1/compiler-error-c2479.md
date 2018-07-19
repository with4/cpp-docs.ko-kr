---
title: 컴파일러 오류 C2479 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2479
dev_langs:
- C++
helpviewer_keywords:
- C2479
ms.assetid: c74c7869-e65b-4ca1-b6fa-eb39fed4458a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1edd4771e14de4044148d2a6ef93a4516856b064
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225995"
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