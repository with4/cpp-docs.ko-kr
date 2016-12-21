---
title: "2.7.2.7 copyin | Microsoft Docs"
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
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.7 copyin
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Copyin** 절에 동일한 값을 할당 하기 위한 메커니즘을 제공 합니다.  **threadprivate** 각 스레드에 병렬 영역을 실행 하는 팀에 대 한 변수입니다.  지정 된 각 변수의  **copyin** 할당 처럼, 병렬 영역 부분에 스레드\-개인 복사본으로 절을 마스터 스레드 팀의 변수 값 복사 합니다.  구문에는  **copyin** 절은 다음과 같습니다:  
  
```  
  
copyin(  
variable-list  
)  
  
```  
  
 제한에는  **copyin** 절은 다음과 같습니다:  
  
-   지정 된 변수를  **copyin** 절에서 액세스할 수 있는, 분명 복사 할당 연산자에 있어야 합니다.  
  
-   지정 된 변수를  **copyin** 절 여야는  **threadprivate** 변수입니다.