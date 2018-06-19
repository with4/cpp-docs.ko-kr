---
title: 컴파일러 오류 C2735 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2735
dev_langs:
- C++
helpviewer_keywords:
- C2735
ms.assetid: 6ce45600-7148-4bc0-8699-af0ef137571e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ab970aa4e46ed0206f311e100f7ee777907aff8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33232671"
---
# <a name="compiler-error-c2735"></a>컴파일러 오류 C2735
형식 매개 변수 형식 지정자에는 'keyword' 키워드를 사용할 수 없습니다.  
  
 키워드가이 컨텍스트에서 올바르지 않습니다.  
  
 다음 샘플에서는 C2735 오류가 생성 됩니다.  
  
```  
// C2735.cpp  
void f(inline int){}   // C2735  
```