---
title: "컴파일러 경고 (수준 1) C4806 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4806
dev_langs: C++
helpviewer_keywords: C4806
ms.assetid: 79eb74cd-b925-4b5b-84e1-8ae6f33e38b3
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5bddda6bd683133f278f79544b2bf13aa132e131
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4806"></a>컴파일러 경고(수준 1) C4806
'operation': 안전하지 않은 연산입니다. 'type' 형식의 값('type' 형식으로 확장)이 주어진 상수와 같을 수 없습니다.  
  
 이 메시지는 `b == 3`과 같은 코드에 대해 경고합니다. 여기서 `b` 는 `bool`형식입니다. 승격 규칙으로 인해 `bool` 이 `int`로 승격됩니다. 유효하지만 **true**가 될 수 없습니다. 다음 샘플에서는 C4806을 생성합니다.  
  
```  
// C4806.cpp  
// compile with: /W1  
int main()  
{  
   bool b = true;  
   // try..  
   // int b = true;  
  
   if (b == 3)   // C4806  
   {  
      b = false;  
   }  
}  
```