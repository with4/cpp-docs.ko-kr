---
title: 컴파일러 경고 (수준 4) C4690 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4690
dev_langs:
- C++
helpviewer_keywords:
- C4690
ms.assetid: 080a0ea1-458b-477b-a37a-4a34c94709ff
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c8285fd3763b93c8a320a6cb984168b88d2e9ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293623"
---
# <a name="compiler-warning-level-4-c4690"></a>컴파일러 경고(수준 4) C4690
[ emitidl( pop ) ]: 데이터를 넣는 작업(push)보다 데이터를 꺼내는 작업(pop)이 많습니다.  
  
 [emitidl](../../windows/emitidl.md) 특성을 넣은 횟수보다 꺼낸 횟수가 한 번 더 많습니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4690을 생성합니다.  
  
```  
// C4690.cpp  
// compile with: /c /W4  
[emitidl(pop)];   // C4690  
class x {};  
```