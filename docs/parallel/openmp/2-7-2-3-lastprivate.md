---
title: "2.7.2.3 lastprivate | Microsoft Docs"
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
ms.assetid: 77f6a5c9-704f-4a88-8476-29db852ed800
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.3 lastprivate
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`lastprivate` 절 상위 집합에서 제공 하는 기능을 제공는 `private` 절.  구문에는 `lastprivate` 절은 다음과 같습니다:  
  
```  
lastprivate(variable-list)  
```  
  
 지정 된 변수를  *변수 목록* 가 `private` 절의 의미 합니다.  경우는 `lastprivate` 절 각각의 값은 작업 공유 구문을 식별 지시문에 나타납니다 `lastprivate` 변수 연결 된 루프 또는 어휘 적으로 마지막 섹션 지시문을 순차적으로 마지막 반복에서 변수의 원래 개체에 할당 됩니다.  되지 않은 변수에 할당 된 값의 마지막 반복에서의  **에 대 한** 또는  **병렬에 대 한**, 나는 어휘 적으로 마지막 구역으로  **섹션** 또는  **평행 단면** 은 지시문을 구문 후 결정 되지 않은 값이 있는.  하위 할당 되지 않은 개체는 결정 되지 않은 값 구문 이후에 합니다.  
  
 제한에는 `lastprivate` 절은 다음과 같습니다:  
  
-   모든 제한 사항에 대 한 `private` 를 적용 합니다.  
  
-   지정한 클래스 형식의 변수 `lastprivate` 액세스할 수 있는, 분명 복사 할당 연산자가 있어야 합니다.  
  
-   변수는 병렬 영역 내부에서는 개인 또는 표시에 `reduction` 절에  **병렬** 지시문에 지정 될 수 없습니다는 `lastprivate` 병렬 구문에 바인딩되는 작업 공유 지시문의 절.