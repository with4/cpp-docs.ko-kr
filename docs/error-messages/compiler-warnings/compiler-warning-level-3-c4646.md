---
title: 컴파일러 경고 (수준 3) C4646 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4646
dev_langs:
- C++
helpviewer_keywords:
- C4646
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36ff770877333042319b2a91dc5006e2ceb4118f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33291218"
---
# <a name="compiler-warning-level-3-c4646"></a>컴파일러 경고(수준 3) C4646
__declspec(noreturn)으로 선언된 함수에 void가 아닌 반환 형식이 있습니다.  
  
 [noreturn](../../cpp/noreturn.md) `__declspec` 한정자로 표시한 함수에는 [void](../../cpp/void-cpp.md) 반환 형식이 있어야 합니다.  
  
 다음 샘플에서는 C4646을 생성합니다.  
  
```  
// C4646.cpp  
// compile with: /W3 /WX  
int __declspec(noreturn) TestFunction()  
{   // C4646  make return type void  
}  
```