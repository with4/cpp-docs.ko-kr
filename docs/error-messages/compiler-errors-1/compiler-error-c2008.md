---
title: 컴파일러 오류 C2008 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2008
dev_langs:
- C++
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88dcbc88b50ee46b406d383ec36e1fed167eca05
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
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