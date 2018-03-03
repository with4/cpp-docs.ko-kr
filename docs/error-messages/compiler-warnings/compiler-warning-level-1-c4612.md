---
title: "컴파일러 경고 (수준 1) C4612 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4612
dev_langs:
- C++
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 922da98a54a572462d2b247f6211a39bcaed9ec6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4612"></a>컴파일러 경고(수준 1) C4612
포함 파일 이름에 오류가 있습니다.  
  
 파일 이름이 잘못되었거나 누락된 경우 **#pragma include_alias** 에서 이 경고가 발생합니다.  
  
 에 대 한 인수는 **#pragma include_alias** 문을 으로부터의 인용 צ ְ ײ (**"***filename***"**) 또는 꺾쇠 괄호 양식 ( **\<**  *filename***>**), 있지만 둘 다 동일한 양식을 사용 해야 합니다.  
  
## <a name="example"></a>예  
  
```  
// C4612.cpp  
// compile with: /W1 /LD  
#pragma include_alias("StandardIO", <stdio.h>) // C4612  
```