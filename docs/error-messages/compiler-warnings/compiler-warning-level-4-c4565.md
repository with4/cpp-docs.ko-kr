---
title: "컴파일러 경고 (수준 4) C4565 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4565
dev_langs: C++
helpviewer_keywords: C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b89da26312c68bc76d23fc829a14f17db3d601b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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