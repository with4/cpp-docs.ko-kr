---
title: "컴파일러 오류 C2881 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2881
dev_langs:
- C++
helpviewer_keywords:
- C2881
ms.assetid: b49c63c2-b064-4d4b-a75e-ddd2af947522
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b6f34c3f48e90ce773f23068bd7f0b3712197ec9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2881"></a>컴파일러 오류 C2881
'namespace1': 이미 'namespace2'에 대 한 별칭으로 사용  
  
 두 개의 네임 스페이스에 대 한 별칭으로 동일한 이름을 사용할 수 없습니다.  
  
 다음 샘플에서는 C2881 오류가 생성 됩니다.  
  
```  
// C2881.cpp  
// compile with: /c  
namespace A {  
   int k;  
}  
  
namespace B {  
   int i;  
}  
  
namespace C = A;  
namespace C = B;   // C2881 C is already an alias for A  
```