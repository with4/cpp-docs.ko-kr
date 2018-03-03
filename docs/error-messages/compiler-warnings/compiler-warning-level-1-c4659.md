---
title: "컴파일러 경고 (수준 1) C4659 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4659
dev_langs:
- C++
helpviewer_keywords:
- C4659
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd974c730a67489d9197b448f02a5042f77159f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4659"></a>컴파일러 경고(수준 1) C4659
\#pragma 'pragma': #pragma 주석 (linker,...)를 사용 하 여, 사용 하 여 예약 된 세그먼트 'segment' 동작이 정의 되지 않았습니다  
  
 .Drectve 옵션을 링커에 옵션 전달 하는 데 사용 되었습니다. Pragma를 사용 하는 대신 [주석](../../preprocessor/comment-c-cpp.md) 링커 옵션을 전달 합니다.  
  
```  
// C4659.cpp  
// compile with: /W1 /LD  
#pragma code_seg(".drectve")   // C4659  
```