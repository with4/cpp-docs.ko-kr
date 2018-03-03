---
title: "컴파일러 경고 (수준 1) C4237 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4237
dev_langs:
- C++
helpviewer_keywords:
- C4237
ms.assetid: f2e86c4b-80d8-460e-9429-83c5f3f5d7ca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 89fa6a15c77ad0107dc3ef39a3563cae3ddecab4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4237"></a>컴파일러 경고(수준 1) C4237
'keyword' 키워드는 아직 지원 되지 않지만 나중에 사용  
  
 Visual c + + 컴파일러에서 c + + 사양에 키워드를 구현 되지 않은 있지만 키워드는 사용자 정의 기호로 사용할 수 없습니다.  
  
 다음 샘플에서는 C4237 오류가 생성 됩니다.  
  
```  
// C4237.cpp  
// compile with: /W1 /c  
int export;   // C4237  
```