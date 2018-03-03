---
title: "컴파일러 경고 (수준 1) C4224 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4224
dev_langs:
- C++
helpviewer_keywords:
- C4224
ms.assetid: 1531cae0-5040-49fd-b149-005bb5085391
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 618e0b12ed20b13d85a7198781d1bec0fea78456
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4224"></a>컴파일러 경고(수준 1) C4224
비표준 확장이 사용 됨: 'identifier' 형식 매개 변수 형식으로 이전에 정의 되었습니다  
  
 식별자로 이전에 사용한는 `typedef`합니다. 이 인해 경고 ANSI 호환성 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).  
  
## <a name="example"></a>예  
  
```  
// C4224.cpp  
// compile with: /Za /W1 /LD  
typedef int I;  
void func ( int I );  // C4224  
```