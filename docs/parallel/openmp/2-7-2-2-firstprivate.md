---
title: "2.7.2.2 firstprivate | Microsoft Docs"
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
ms.assetid: ece6ff12-2be1-4e4f-866c-d39345fd87b5
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.2 firstprivate
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Firstprivate** 절 상위 집합에서 제공 하는 기능을 제공는  **개인** 절.  구문에는  **firstprivate** 절은 다음과 같습니다:  
  
```  
firstprivate(variable-list)  
```  
  
 지정 된 변수  *변수 목록* 가  **개인** 절 구문에 설명 된 대로,  [섹션 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) 25 페이지.  초기화 또는 생성 구문에는 스레드를 실행 하기 전에 스레드 당 한 번만 수행 됩니다 경우에 발생 합니다.  에 있는  **firstprivate** 절을 병렬 구문에 새 private 개체의 초기 값입니다 발견 한 스레드에 대 한 병렬 구문 바로 이전에 있는 원래 개체의 값입니다.  에 있는  **firstprivate** 절 작업 공유 생성자에서 작업 공유 생성자를 실행 하는 각 스레드에 대 한 개인 새 개체의 초기 값은 시간에 동일한 스레드에서 작업 공유 생성자를 발견 한 시점 이전에 원래 개체의 값입니다.  또한 C\+\+ 개체에 대 한 새 개인 개체 각 스레드에 대 한 원본 개체에서 생성 된 복사본입니다.  
  
 제한에는  **firstprivate** 절은 다음과 같습니다:  
  
-   지정 된 변수를  **firstprivate** 절 되었습니다 형식 또는 참조 형식입니다.  
  
-   지정한 클래스 형식의 변수  **firstprivate** 액세스할 수 있는, 분명 복사 생성자가 있어야 합니다.  
  
-   변수는 병렬 영역 내부에서는 개인 또는 해당 표시를  **감소** 절에  **병렬** 지시문에 지정 될 수 없습니다는  **firstprivate** 병렬 구문에 바인딩되는 작업 공유 지시문의 절.