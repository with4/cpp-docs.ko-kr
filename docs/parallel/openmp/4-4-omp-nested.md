---
title: "4.4 OMP_NESTED | Microsoft Docs"
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
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 4.4 OMP_NESTED
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`OMP_NESTED` 환경 변수가 활성화 또는 비활성화를 호출 하 여 중첩 된 병렬 처리 하지 않으면 중첩 된 병렬 처리를 사용할지 여부는 `o`**mp\_set\_nested** 라이브러리 루틴.  경우를 설정  **TRUE**, 중첩 된 병렬 처리 기능을 사용 합니다. 이 설정 되어 있으면  **FALSE**의 중첩 된 병렬 처리를 사용할 수 없습니다.  기본값은  **FALSE**.  
  
 예를 들면 와 같은 형식입니다.  
  
```  
setenv OMP_NESTED TRUE  
```  
  
## 상호 참조:  
  
-   `omp_set_nested`작동, 참조 하십시오  [섹션 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 페이지에 있습니다.