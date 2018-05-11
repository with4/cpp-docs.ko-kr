---
title: 컴파일러 오류 C2007 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2007
dev_langs:
- C++
helpviewer_keywords:
- C2007
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 159a4b8f9dffc4f6ee96b0bb1935682f9f6db281
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2007"></a>컴파일러 오류 C2007
\#구문 정의  
  
 뒤에 식별자 없이 표시 됩니다는 `#define`합니다. 이 오류를 해결 하려면 식별자를 사용 합니다.  
  
 다음 샘플에서는 C2007 오류가 생성 됩니다.  
  
```  
// C2007.cpp  
#define   // C2007  
```  
  
 해결 방법:  
  
```  
// C2007b.cpp  
// compile with: /c  
#define true 1  
```