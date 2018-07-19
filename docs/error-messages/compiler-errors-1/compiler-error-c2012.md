---
title: 컴파일러 오류 C2012 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2012
dev_langs:
- C++
helpviewer_keywords:
- C2012
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e52b08d7a7d93682e1750ae545183195fc563734
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164125"
---
# <a name="compiler-error-c2012"></a>컴파일러 오류 C2012
'<' 다음에 이름이 없습니다.  
  
 `#include` 지시문에 필요한 파일 이름이 없습니다.  
  
 다음 샘플에서는 C2012를 생성합니다.  
  
```  
// C2012.cpp  
#include <   // C2012 include the filename to resolve  
```  
  
 해결 방법:  
  
```  
// C2012b.cpp  
// compile with: /c  
#include <stdio.h>  
```