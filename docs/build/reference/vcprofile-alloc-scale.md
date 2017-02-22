---
title: "VCPROFILE_ALLOC_SCALE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VCPROFILE_ALLOC_SCALE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VCPROFILE_ALLOC_SCALE 환경 변수"
ms.assetid: 5cb5ce27-f9b8-489b-b46c-d6e9bcab2d34
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# VCPROFILE_ALLOC_SCALE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로필 데이터를 보관하기 위해 할당된 메모리의 양을 수정합니다.  
  
## 구문  
  
```  
VCPROFILE_ALLOC_SCALE=scale_value  
```  
  
#### 매개 변수  
 `scale_value`  
 테스트 시나리오를 실행하기 위한 메모리 양의 배율 값입니다.  기본값은 1입니다.  
  
## 설명  
 드물기는 하지만 테스트 시나리오를 실행할 때 사용 가능한 메모리가 부족하여 프로필 데이터를 수집할 수 없는 경우가 있습니다.  이러한 경우에는 `VCPROFILE_ALLOC_SCALE`을 사용하여 메모리의 양을 늘릴 수 있습니다.  
  
 테스트 실행 과정에서 메모리가 부족하다는 오류 메시지가 나타나면 메모리 부족 오류가 발생하지 않고 테스트 실행이 완료될 수 있도록 `VCPROFILE_ALLOC_SCALE`에 더 큰 값을 할당합니다.  
  
## 예제  
  
```  
set VCPROFILE_ALLOC_SCALE=2  
```  
  
## 참고 항목  
 [프로필 기반 최적화 환경 변수](../../build/reference/environment-variables-for-profile-guided-optimizations.md)