---
title: 컴파일러 경고 (수준 1) C4086 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4086
dev_langs:
- C++
helpviewer_keywords:
- C4086
ms.assetid: 9248831b-22bf-47af-8684-bfadb17e94fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 541543cde39821a938290d1a8f5ce2063c8fc997
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4086"></a>컴파일러 경고(수준 1) C4086
pragma 매개 변수는 '1', '2', '4', '8' 또는 '16'이어야 합니다.  
  
 pragma 매개 변수에 필수 값(1, 2, 4, 8 또는 16)이 없습니다.  
  
## <a name="example"></a>예제  
  
```  
// C4086.cpp  
// compile with: /W1 /LD  
#pragma pack( 3 ) // C4086  
```