---
title: "컴파일러 경고 (수준 1) C4185 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4185
dev_langs: C++
helpviewer_keywords: C4185
ms.assetid: 37e7063a-35b1-4e05-ae31-e811dced02b9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c3fde7c9cf849006e55a3b1f3c54926597bc0fdc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4185"></a>컴파일러 경고(수준 1) C4185
알 수 없는 #import 특성 'attribute'를 무시합니다.  
  
 attribute는 `#import`의 유효한 특성이 아닙니다. 무시됩니다.  
  
## <a name="example"></a>예제  
  
```  
// C4185.cpp  
// compile with: /W1 /c  
#import "stdole2.tlb" no_such_attribute   // C4185  
```