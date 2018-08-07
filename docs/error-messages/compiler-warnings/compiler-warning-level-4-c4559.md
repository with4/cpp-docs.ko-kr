---
title: 컴파일러 경고 (수준 4) C4559 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4559
dev_langs:
- C++
helpviewer_keywords:
- C4559
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c853fa55482604d97c29653fadb06b0afdd44977
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33295352"
---
# <a name="compiler-warning-level-4-c4559"></a>컴파일러 경고(수준 4) C4559
'function': 재정의. 함수 향상 __declspec(modifier)  
  
 함수를 다시 선언를 하거나 두 번째 정의 또는 선언은 __**declspec** 한정자 (***한정자***). 이 경고는 정보 제공용입니다. 이 경고를 해결 하려면 정의 중 하나를 삭제 합니다.  
  
 다음 샘플에서는 C4559 오류가 생성 됩니다.  
  
```  
// C4559.cpp  
// compile with: /W4 /LD  
void f();  
__declspec(noalias) void f();   // C4559  
```