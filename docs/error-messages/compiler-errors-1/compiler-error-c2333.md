---
title: 컴파일러 오류 C2333 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2333
dev_langs:
- C++
helpviewer_keywords:
- C2333
ms.assetid: 2636fc1e-d3e7-4e68-8628-3c81a99ba813
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1613d560ef22c33ca1a19ac63584138a18c19c4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33195284"
---
# <a name="compiler-error-c2333"></a>컴파일러 오류 C2333
'function': 함수 선언; 하는 동안 오류가 발생 했습니다. 함수 본문을 건너뜁니다.  
  
 이 오류는 해당 하는 클래스 내에 정의 된 멤버 함수에 대 한 다른 오류가 발생 한 후 발생 합니다.  
  
 다음 샘플에서는 C2333 오류가 생성 됩니다.  
  
```  
// C2333.cpp  
struct s1 {  
   s1(s1) {}   // C2333  
};  
```