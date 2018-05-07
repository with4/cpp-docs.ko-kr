---
title: 컴파일러 오류 C2160 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2160
dev_langs:
- C++
helpviewer_keywords:
- C2160
ms.assetid: a1f694a7-fb16-4437-b7f5-a1af6da94bc5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6667a88c7cfd202938a4956d981d4fc2c399f57f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2160"></a>컴파일러 오류 C2160
매크로 정의 시작에 '##'이 올 수 없습니다.  
  
 매크로 정의가 토큰 붙여넣기 연산자(##)로 시작되었습니다.  
  
 다음 샘플에서는 C2160을 생성합니다.  
  
```  
// C2160.cpp  
// compile with: /c  
#define mac(a,b) #a   // OK  
#define mac(a,b) ##a   // C2160  
```