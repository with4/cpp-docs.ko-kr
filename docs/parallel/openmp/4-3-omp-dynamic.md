---
title: "4.3 OMP_DYNAMIC | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 4.3 OMP_DYNAMIC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**OMP\_DYNAMIC** 환경 변수 동적 조정 명시적으로 활성화 하거나 비활성화 호출 하면 않는 한 동적 조정의 병렬 영역 실행에 사용할 스레드 수를 사용할지 여부는  **omp\_set\_dynamic** 라이브러리 루틴입니다.  변수 값 이어야 합니다  **TRUE** 또는  **FALSE**.  
  
 경우를 설정  **TRUE**, 시스템 리소스를 최대한 활용 하려면 런타임 환경에 의해 병렬 영역을 실행 하는 데 사용 되는 스레드 수를 조정할 수 있습니다.  경우 설정  **FALSE**, 동적 조정 사용할 수 없습니다.  기본 조건 구현 시 정의 됩니다.  
  
 예를 들면 와 같은 형식입니다.  
  
```  
setenv OMP_DYNAMIC TRUE  
```  
  
## 상호 참조:  
  
-   병렬 영역에 대 한 자세한 내용은  [섹션 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 페이지입니다.  
  
-   **omp\_set\_dynamic** 작동, 참조 하십시오  [섹션 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 페이지에 있습니다.