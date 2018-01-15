---
title: "조건부 컴파일 지정 a. 2가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: de4a21b9-f987-4738-9f13-c4795f6f2dff
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93557eaae2c8661697f7bda383b50f2e1ba9e2cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
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