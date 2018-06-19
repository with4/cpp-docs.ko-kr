---
title: 컴파일러 경고 (수준 1) C4612 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4612
dev_langs:
- C++
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0983f5d0bb89eaf1daee94468b318557bc83cd05
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33281884"
---
# <a name="compiler-warning-level-1-c4612"></a>컴파일러 경고(수준 1) C4612
포함 파일 이름에 오류가 있습니다.  
  
 파일 이름이 잘못되었거나 누락된 경우 **#pragma include_alias** 에서 이 경고가 발생합니다.  
  
 에 대 한 인수는 **#pragma include_alias** 문을 으로부터의 인용 צ ְ ײ (**"***filename***"**) 또는 꺾쇠 괄호 양식 ( **\< ***filename***>**), 있지만 둘 다 동일한 양식을 사용 해야 합니다.  
  
## <a name="example"></a>예제  
  
```  
// C4612.cpp  
// compile with: /W1 /LD  
#pragma include_alias("StandardIO", <stdio.h>) // C4612  
```