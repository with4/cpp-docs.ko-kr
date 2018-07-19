---
title: 컴파일러 오류 C2256 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2256
dev_langs:
- C++
helpviewer_keywords:
- C2256
ms.assetid: 171fa2bc-8c72-49cd-afe5-d723b7acd3c5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b2571d13d08d368bf974b0c283c7d676eab6b56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169129"
---
# <a name="compiler-error-c2256"></a>컴파일러 오류 C2256
'function'에 friend 지정자를 잘못 사용 했습니다.  
  
 소멸자 또는 생성자로 지정할 수 없습니다는 [friend](../../cpp/friend-cpp.md)합니다.  
  
 다음 샘플에서는 C2256 오류가 생성 됩니다.  
  
```  
// C2256.cpp  
// compile with: /c  
class C {  
public:  
   friend ~C();   // C2256  
   ~C();   // OK  
};  
```