---
title: "2.4.3 single 구문 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 72dc551986f149bda668c438ac5f51d01d530c51
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="243-single-construct"></a>2.4.3 single 구문
**단일** 지시문 (반드시 마스터 스레드) 팀에 한 스레드에서만 관련된 구조화 된 블록 실행 되도록 지정 하는 구조를 식별 합니다. 구문은 **단일** 지시문은 다음과 같습니다.  
  
```  
#pragma omp single [clause[[,] clause] ...] new-linestructured-block  
```  
  
 절은 다음 중 하나입니다.  
  
 **개인 (** *변수 목록* **)**  
  
 **firstprivate (** *변수 목록* **)**  
  
 **copyprivate (** *변수 목록* **)**  
  
 **nowait**  
  
 후에 암시적 장벽은는 **단일** 하지 않는 경우 만들는 **nowait** 절을 지정 합니다.  
  
 에 대 한 제한 된 **단일** 지시문은 다음과 같습니다.  
  
-   단일 **nowait** 절에 나타날 수 있습니다는 **단일** 지시문입니다.  
  
-   **copyprivate** 절을 함께 사용할 수 해야는 **nowait** 절.  
  
## <a name="cross-references"></a>교차 참조:  
  
-   **개인**, **firstprivate**, 및 **copyprivate** 절에서 참조 [섹션 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 페이지.