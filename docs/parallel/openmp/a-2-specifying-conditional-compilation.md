---
title: 조건부 컴파일 지정 a. 2가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: de4a21b9-f987-4738-9f13-c4795f6f2dff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d54245a2df2f38bed2674a3bb3923f8212d35459
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="a2---specifying-conditional-compilation"></a>A.2   조건부 컴파일 지정
다음 예에서는 조건부 컴파일 OpenMP 매크로 사용 하 여 사용법을 보여 줍니다. `_OPENMP` ([섹션 2.2](../../parallel/openmp/2-2-conditional-compilation.md) 8 페이지에). OpenMP 컴파일을 사용한는 `_OPENMP` 매크로가 정의 됩니다.  
  
```  
# ifdef _OPENMP   
    printf_s("Compiled by an OpenMP-compliant implementation.\n");  
# endif  
```  
  
 정의 된 전처리기 연산자는 둘 이상의 매크로 단일 지시문에서 테스트할 수 있습니다.  
  
```  
# if defined(_OPENMP) && defined(VERBOSE)  
    printf_s("Compiled by an OpenMP-compliant implementation.\n");  
# endif  
```