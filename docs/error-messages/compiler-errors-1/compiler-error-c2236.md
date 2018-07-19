---
title: 컴파일러 오류 C2236 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2236
dev_langs:
- C++
helpviewer_keywords:
- C2236
ms.assetid: 0b6771a7-a783-4729-9c3d-7a3339c432cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f755c9ba72e2d36bdce608e93e8a60175e493a45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170556"
---
# <a name="compiler-error-c2236"></a>컴파일러 오류 C2236
예기치 않은 토큰 'identifier'입니다. ';'이 없습니다.  
  
 식별자가 이미 형식으로 정의되었으며 사용자 정의 형식으로 재정의할 수 없습니다.  
  
 다음 샘플에서는 C2236을 생성합니다.  
  
```  
// C2236.cpp  
// compile with: /c  
int class A {};  // C2236 "int class" is unexpected  
int i;  
class B {};  
```