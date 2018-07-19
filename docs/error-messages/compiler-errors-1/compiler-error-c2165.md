---
title: 컴파일러 오류 C2165 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2165
dev_langs:
- C++
helpviewer_keywords:
- C2165
ms.assetid: b108313b-b8cb-4dce-b2ec-f2b31c9cdc87
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db8d434993ad913efca3fdff58fb7ed9cc0715e5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170481"
---
# <a name="compiler-error-c2165"></a>컴파일러 오류 C2165
'keyword': 데이터에 대한 포인터를 수정할 수 없습니다.  
  
 `__stdcall`, `__cdecl`또는 `__fastcall` 키워드가 데이터에 대한 포인터를 수정하려고 시도합니다.  
  
 다음 샘플에서는 C2165를 생성합니다.  
  
```  
// C2165.cpp  
// compile with: /c  
char __cdecl *p;   // C2165  
char *p;   // OK  
```