---
title: 컴파일러 오류 C2129 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2129
dev_langs:
- C++
helpviewer_keywords:
- C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d151c774672b1788ca893a9812deb3e41100dc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2129"></a>컴파일러 오류 C2129
'function' 정적 함수 선언 되었지만 정의 되지 않았습니다.  
  
 정방향 참조는 `static` 정의 되지 않은 함수입니다.  
  
 A `static` 파일 범위 내에서 함수를 정의 해야 합니다. 를 다른 파일에서 함수를 정의 하는 경우 선언 해야 `extern`합니다.