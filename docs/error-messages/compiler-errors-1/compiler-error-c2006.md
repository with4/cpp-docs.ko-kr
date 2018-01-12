---
title: "컴파일러 오류 C2006 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2006
dev_langs: C++
helpviewer_keywords: C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4db382ab78cbd230813fada89f9c04244035932f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2006"></a>컴파일러 오류 C2006
'directive' 하는데 'token' 파일 이름이 필요 합니다.  
  
 지시문과 같은 [#include](../../preprocessor/hash-include-directive-c-cpp.md) 또는 [#import](../../preprocessor/hash-import-directive-cpp.md) 파일 이름이 필요 합니다. 이 오류를 해결 하려면 *토큰* 유효한 파일 이름입니다. 파일 이름을 큰따옴표 또는 꺾쇠 괄호에서 선택할 수도 있습니다.  
  
 다음 샘플에서는 C2006 오류가 생성 됩니다.  
  
```  
// C2006.cpp  
#include stdio.h   // C2006  
```  
  
 해결 방법:  
  
```  
// C2006b.cpp  
// compile with: /c  
#include <stdio.h>  
```