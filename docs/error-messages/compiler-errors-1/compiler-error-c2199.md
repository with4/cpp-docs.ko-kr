---
title: 컴파일러 오류 C2199 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2199
dev_langs:
- C++
helpviewer_keywords:
- C2199
ms.assetid: 6a92a1b7-7906-49e6-a31f-e8bffbc7706a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 31164597c9427dc5e915f5a0315d8e2bb7825e8e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33169012"
---
# <a name="compiler-error-c2199"></a>컴파일러 오류 C2199
구문 오류: 찾을 ' 식별자 (' 전역 범위에서 (의도 한 선언 ि ल ्?)  
  
 지정된 된 컨텍스트 구문 오류가 발생 했습니다. 잘못 된 선언 구문이 있을 수 있습니다.  
  
 다음 샘플에서는 C2199 오류가 생성 됩니다.  
  
```  
// C2199.cpp  
// compile with: /c  
int j = int(1) int(1);   // C2199  
int j = 1;   // OK  
```