---
title: "컴파일러 경고 (수준 1) C4033 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4033
dev_langs:
- C++
helpviewer_keywords:
- C4033
ms.assetid: 189a9ec3-ff6d-49dd-b9b2-530b28bbb7c9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aec85fa985b3d8183d7614bdd6b3527b5d671b2b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4033"></a>컴파일러 경고(수준 1) C4033
'function'은 값을 반환해야 합니다.  
  
 함수가 값을 반환하지 않습니다. 정의되지 않은 값이 반환됩니다.  
  
 반환 값 없이 `return` 을 사용하는 함수를 `void`형식으로 선언해야 합니다.  
  
 이 오류는 C 언어 코드용입니다.  
  
 다음 샘플에서는 C4033을 생성합니다.  
  
```  
// C4033.c  
// compile with: /W1 /LD  
int test_1(int x)   // C4033 expected  
{  
   if (x)  
   {  
      return;   // C4033  
   }  
}  
```