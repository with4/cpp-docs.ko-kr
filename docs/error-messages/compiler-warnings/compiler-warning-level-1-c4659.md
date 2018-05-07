---
title: 컴파일러 경고 (수준 1) C4659 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4659
dev_langs:
- C++
helpviewer_keywords:
- C4659
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 643b599cd11d0935f1769ad37dca4e764f0418e6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4659"></a>컴파일러 경고(수준 1) C4659
\#pragma 'pragma': #pragma 주석 (linker,...)를 사용 하 여, 사용 하 여 예약 된 세그먼트 'segment' 동작이 정의 되지 않았습니다  
  
 .Drectve 옵션을 링커에 옵션 전달 하는 데 사용 되었습니다. Pragma를 사용 하는 대신 [주석](../../preprocessor/comment-c-cpp.md) 링커 옵션을 전달 합니다.  
  
```  
// C4659.cpp  
// compile with: /W1 /LD  
#pragma code_seg(".drectve")   // C4659  
```