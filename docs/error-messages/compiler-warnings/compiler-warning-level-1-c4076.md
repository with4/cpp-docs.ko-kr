---
title: 컴파일러 경고 (수준 1) C4076 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4076
dev_langs:
- C++
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1cfa28469e099dbf2b6bd43213073c304d0b2894
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275475"
---
# <a name="compiler-warning-level-1-c4076"></a>컴파일러 경고(수준 1) C4076
'typemod': 'typename' 형식과 함께 사용할 수 없습니다.  
  
 **signed** 또는 `unsigned`인지에 관계없이 형식 한정자는 정수가 아닌 형식과 함께 사용할 수 없습니다. ***typemod*** 는 무시됩니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C4076을 생성합니다.  
  
```  
// C4076.cpp  
// compile with: /W1 /LD  
unsigned double x;   // C4076  
```