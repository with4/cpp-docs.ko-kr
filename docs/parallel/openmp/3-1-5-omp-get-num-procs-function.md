---
title: 3.1.5 omp_get_num_procs 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: bbfbf17b-0c68-4ba6-a25d-07c36ecb551f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 692bf39ea6d67f3ef9b850ddba187bbde98cb64c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="315-ompgetnumprocs-function"></a>3.1.5 omp_get_num_procs 함수
`omp_get_num_procs` 함수는 함수가 호출 되는 시간에 프로그램에 사용할 수 있는 프로세서 수를 반환 합니다. 형식은 다음과 같습니다.  
  
```  
#include <omp.h>  
int omp_get_num_procs(void);  
```