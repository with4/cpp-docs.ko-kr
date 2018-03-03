---
title: "컴파일러 경고 (수준 1) C4333 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4333
dev_langs:
- C++
helpviewer_keywords:
- C4333
ms.assetid: d3763c52-6110-4da0-84db-5264e3f3f166
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 22704292cae37b4c4395c49fb69fb2c59c1ccd48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4333"></a>컴파일러 경고(수준 1) C4333
'operator': 오른쪽 시프트 횟수가 너무 커 데이터가 손실  
  
 오른쪽 시프트 작업과 된 크기가 너무 큽니다.  모든 중요 한 비트 시프트 아웃 되 고 결과 항상 0이 됩니다.  
  
## <a name="example"></a>예  
 다음 샘플에서는 C4333 오류가 발생 합니다.  
  
```  
// C4333.cpp  
// compile with: /c /W1  
unsigned shift8 (unsigned char c) {  
   return c >> 8;   // C4333  
  
   // try the following line instead  
   // return c >> 4;   // OK  
}  
```