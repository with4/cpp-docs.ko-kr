---
title: "2.7.2.5 default | Microsoft Docs"
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
ms.assetid: c856df07-705c-4ad3-9105-a268dd33e939
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.5 default
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

해당  **기본** 절을 변수의 데이터 공유 특성에 영향을 줄 수 있습니다.  구문에는  **기본** 절은 다음과 같습니다:  
  
```  
default(shared | none)  
```  
  
 지정  **default\(shared\)** 각 현재 보이는 변수를 명시적으로 나열 하는 것과 같습니다는  **공유** 절이 아니라면  **threadprivate** 또는  **단점**`t`\-한정 된.  명시적 없는 경우에서  **기본** 절을 기본 동작은 것 같은 if  **default\(shared\)** 지정 되지 않았습니다.  
  
 지정  **default\(none\)** 다음 중 하나 이상의 병렬 구성의 어휘 범위 변수에 대 한 모든 참조에 대해 true 이어야 합니다.  
  
-   변수는 명시적으로 데이터 공유 특성 절에 대 한 참조를 포함 하는 구문에 나열 되어 있습니다.  
  
-   병렬 구문에 변수를 선언 합니다.  
  
-   변수  **threadprivate**.  
  
-   이 변수는  **const**\-정규화 된 형식.  
  
-   변수가 for 루프 제어 변수는는  **에 대 한** 루프 바로 다음에 오는  **에 대 한** 또는  **병렬에 대 한** 지시문 및 변수 참조 루프 안에 나타납니다.  
  
 변수를 지정 하는  **firstprivate**,  **lastprivate**, 또는  **감소** 절에 동봉 된 지시문의 바깥쪽 컨텍스트에서 변수에 암시적 참조 됩니다.  위에 나열 된 요구 사항에 따라 이러한 암시적 참조를 수도 있습니다.  
  
 하나만  **기본** 절에서 지정할 수 있는  **병렬** 지시문.  
  
 변수의 기본 데이터 공유 특성을 사용 하 여 재정의할 수는  **개인**,  **firstprivate**,  **lastprivate**,  **감소**, 및  **공유** 절은 다음 예제에서와 같이:  
  
```  
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\  
   private(x)  private(r)  lastprivate(i)  
```