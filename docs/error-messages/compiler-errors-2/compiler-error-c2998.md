---
title: 컴파일러 오류 C2998 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2998
dev_langs:
- C++
helpviewer_keywords:
- C2998
ms.assetid: 8193d491-b5d9-4477-acb1-cf166889c070
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19c37ef7ce1a1257f25c76bdf31efbdc25ae6ae3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2998"></a>컴파일러 오류 C2998
'identifier': 템플릿 정의일 수 없습니다.  
  
 컴파일러에서 템플릿 정의에 사용되는 구문을 처리할 수 없습니다.  
  
 다음 샘플에서는 C2998을 생성합니다.  
  
```  
// C2998.cpp  
// compile with: /c  
template <class T> int x = 1018; // C2998  
```