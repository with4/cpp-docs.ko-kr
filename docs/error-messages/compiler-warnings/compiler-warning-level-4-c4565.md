---
title: 컴파일러 경고 (수준 4) C4565 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4565
dev_langs:
- C++
helpviewer_keywords:
- C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d3c4249783686c1fabb44395d3c092eca0d9230a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293366"
---
# <a name="compiler-warning-level-4-c4565"></a>컴파일러 경고(수준 4) C4565
'function': 재정의. 기호는 __declspec(modifier)와 이전에 선언 되었으므로  
  
 기호가 재정의 되거나 다시 선언 하 고 두 번째 정의 나 첫 번째 정의 또는 선언 달리 선언 되지 않았습니다는 `__declspec` 한정자 (***한정자***). 이 경고는 정보 제공용입니다. 이 경고를 해결 하려면 정의 중 하나를 삭제 합니다.  
  
 다음 샘플에서는 C4565 오류가 생성 됩니다.  
  
```  
// C4565.cpp  
// compile with: /W4 /LD  
__declspec(noalias) void f();  
void f();   // C4565  
```