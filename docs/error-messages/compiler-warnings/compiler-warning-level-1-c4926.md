---
title: "컴파일러 경고 (수준 1) C4926 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4926
dev_langs:
- C++
helpviewer_keywords:
- C4926
ms.assetid: 5717fce0-146f-4ef2-bde0-e9a01c0922d1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e552fb7014b5afcda70f0b69c53dd0f9008e1d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4926"></a>컴파일러 경고(수준 1) C4926
'identifier': 기호를 이미 정의했으므로 특성이 무시됩니다.  
  
 정방향 선언이 있지만 이름이 같은 특성을 가진 구문이 이미 있습니다. 정방향 선언에 대한 특성은 무시됩니다.  
  
 다음 샘플에서는 C4926을 생성합니다.  
  
```  
// C4926.cpp  
// compile with: /W1  
[module(name="MyLib")];  
  
[coclass]  
struct a {  
};  
  
[coclass]  
struct a;   // C4926  
  
int main() {  
}  
```