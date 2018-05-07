---
title: 컴파일러 경고 (수준 1) C4167 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4167
dev_langs:
- C++
helpviewer_keywords:
- C4167
ms.assetid: 74a420bd-9371-4167-b1ee-74dd8680f97b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c72d6fd88b8c4797b2e352d6d30dbf797a23a00d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4167"></a>컴파일러 경고(수준 1) C4167
function: 내장 함수로만 사용할 수 있습니다.  
  
 **#pragma 함수** 는 컴파일러에서 내장 형식으로 사용해야 하는 함수에 대해 기존 호출을 사용하도록 강제하려고 합니다. pragma가 무시됩니다.  
  
 이 경고를 방지하려면 **#pragma 함수**를 제거합니다.  
  
## <a name="example"></a>예제  
  
```  
// C4167.cpp  
// compile with: /W1  
#include <malloc.h>  
#pragma function(_alloca )   // C4167: _alloca() is intrinsic only  
int main(){}  
```