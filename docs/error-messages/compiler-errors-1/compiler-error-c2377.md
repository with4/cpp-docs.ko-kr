---
title: 컴파일러 오류 C2377 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2377
dev_langs:
- C++
helpviewer_keywords:
- C2377
ms.assetid: f7660965-bf4c-4cd9-8307-1bd7016678a1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7d76b94ef099c2ac84ee7f048539ed56549d2e0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2377"></a>컴파일러 오류 C2377
'identifier': 재정의. 다른 기호를 사용하여 형식 정의를 오버로드할 수 없습니다.  
  
 `typedef` 식별자가 다시 정의되었습니다.  
  
 다음 샘플에서는 C2377을 생성합니다.  
  
```  
// C2377.cpp  
// compile with: /c  
typedef int i;  
int i;   // C2377  
int j;   // OK  
```