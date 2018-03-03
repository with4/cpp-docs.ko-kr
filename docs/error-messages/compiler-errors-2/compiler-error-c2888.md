---
title: "컴파일러 오류 C2888 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2888
dev_langs:
- C++
helpviewer_keywords:
- C2888
ms.assetid: 244f593e-ff25-4dad-b31f-84dafa3bc84a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fc78a27acb687ea92dd1ecc74a881653c7b414f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2888"></a>컴파일러 오류 C2888
'identifier': 'namespace' 네임 스페이스 내에서 기호를 정의할 수 없습니다  
  
 1. 포함 하는 네임 스페이스에는 네임 스페이스에 속하는 기호를 정의 해야 합니다.  
  
 다음 샘플에서는 C2888 오류가 생성 됩니다.  
  
```  
// C2888.cpp  
// compile with: /c  
namespace M {  
   namespace N {  
      void f1();  
      void f2();  
   }  
  
   void N::f1() {}   // OK: namspace M encloses N  
}  
  
namespace O {  
   void M::N::f2() {}   // C2888 namespace O does not enclose M  
}  
```