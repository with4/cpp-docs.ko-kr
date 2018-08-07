---
title: 컴파일러 오류 C2042 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2042
dev_langs:
- C++
helpviewer_keywords:
- C2042
ms.assetid: e111788f-41ce-405a-9824-a4c1c26059e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5b0442371b210f40d58a10b6bf1107979ea88db
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164026"
---
# <a name="compiler-error-c2042"></a>컴파일러 오류 C2042
signed/unsigned 키워드는 함께 사용할 수 없습니다.  
  
 키워드 `signed` 및 `unsigned` 가 단일 선언에서 사용되었습니다.  
  
 다음 샘플에서는 C2042를 생성합니다.  
  
```  
// C2042.cpp  
unsigned signed int i;   // C2042  
```  
  
 해결 방법:  
  
```  
// C2042b.cpp  
// compile with: /c  
unsigned int i;  
signed int ii;  
```