---
title: "컴파일러 오류 C2008 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2008
dev_langs:
- C++
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3edf3320fb8a598e216e716ffdc5c2a1a01d1d6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2008"></a>컴파일러 오류 C2008
'character': 매크로 정의에 사용할 수 없습니다.  
  
 매크로 이름 바로 뒤의 문자가 나타납니다. 이 오류를 해결 하려면 매크로 이름 다음에 공간 이어야 합니다.  
  
 다음 샘플에서는 C2008 오류가 생성 됩니다.  
  
```  
// C2008.cpp  
#define TEST1"mytest1"    // C2008  
```  
  
 해결 방법:  
  
```  
// C2008b.cpp  
// compile with: /c  
#define TEST2 "mytest2"  
```