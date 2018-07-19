---
title: 컴파일러 오류 c 3152 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3152
dev_langs:
- C++
helpviewer_keywords:
- C3152
ms.assetid: 4ee6e2cd-5d19-4b73-833d-765c35797e4b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93d1d73a5ab48ed992edafd8f6fe845e7e0f1561
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249413"
---
# <a name="compiler-error-c3152"></a>컴파일러 오류 c 3152
'construct': 'keyword'은(는) 클래스, 구조체 또는 가상 멤버 함수에만 적용될 수 있습니다.  
  
 특정 키워드는 C++ 클래스에만 적용될 수 있습니다.  
  
 다음 샘플에서는 C3152를 생성하고 해결 방법을 보여 줍니다.  
  
```  
// C3152.cpp  
// compile with: /clr /c  
ref class C {  
   int (*pfn)() sealed;   // C3152  
   virtual int g() sealed;   // OK  
};  
```  
