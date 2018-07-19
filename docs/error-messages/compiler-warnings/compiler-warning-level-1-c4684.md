---
title: 컴파일러 경고 (수준 1) C4684 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4684
dev_langs:
- C++
helpviewer_keywords:
- C4684
ms.assetid: e95f1a83-2784-4b05-ae94-12148e056e26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cba83467e4705323eaecd990a7c5c32777990ffb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33280990"
---
# <a name="compiler-warning-level-1-c4684"></a>컴파일러 경고(수준 1) C4684
'attribute': 경고!! 특성에 잘못 된 코드가 생성 발생할 수 있습니다: 주의 하 여 사용  
  
 일반적으로 사용 하지 않아야 하는 특성을 사용 하는 경우.  
  
 다음 샘플에서는 C4684 오류가 생성 됩니다.  
  
```  
// C4684.cpp  
// compile with: /W1 /LD  
 [module(name="xx")]; // C4684 expected  
[no_injected_text];  
```