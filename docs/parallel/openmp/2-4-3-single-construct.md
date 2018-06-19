---
title: 2.4.3 single 구문 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db3f9ca834fb3f35c95732698fd02e16f31b4225
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690584"
---
# <a name="243-single-construct"></a>2.4.3 single 구문
**단일** 지시문 (반드시 마스터 스레드) 팀에 한 스레드에서만 관련된 구조화 된 블록 실행 되도록 지정 하는 구조를 식별 합니다. 구문은 **단일** 지시문은 다음과 같습니다.  
  
```  
#pragma omp single [clause[[,] clause] ...] new-linestructured-block  
```  
  
 절은 다음 중 하나입니다.  
  
 **private(** *variable-list* **)**  
  
 **firstprivate(** *variable-list* **)**  
  
 **copyprivate (** *변수 목록* **)**  
  
 **nowait**  
  
 후에 암시적 장벽은는 **단일** 하지 않는 경우 만들는 **nowait** 절을 지정 합니다.  
  
 에 대 한 제한 된 **단일** 지시문은 다음과 같습니다.  
  
-   단일 **nowait** 절에 나타날 수 있습니다는 **단일** 지시문입니다.  
  
-   **copyprivate** 절을 함께 사용할 수 해야는 **nowait** 절.  
  
## <a name="cross-references"></a>교차 참조:  
  
-   **개인**, **firstprivate**, 및 **copyprivate** 절에서 참조 [섹션 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 페이지.