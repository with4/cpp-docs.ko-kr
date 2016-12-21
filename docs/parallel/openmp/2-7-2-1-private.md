---
title: "2.7.2.1 private | Microsoft Docs"
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
ms.assetid: 079b4b84-f2b3-4050-a0ac-289493c36b3d
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.1 private
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`private` 절 팀에서 각 스레드를 전용으로 변수 목록에서 변수를 선언 합니다.  구문에는 `private` 절은 다음과 같습니다:  
  
```  
private(variable-list)  
```  
  
 동작에 지정 된 변수를 `private` 절은 다음과 같습니다.  자동 저장 기간을 갖는 새 개체 구문에 대 한 할당 됩니다.  크기와 새 개체의 맞춤 변수 유형에 따라 결정 됩니다.  팀에서 각 스레드에 대 한 번이 할당을 발생 하 고 필요 하면 클래스 개체에 대 한 기본 생성자를 호출 합니다. 그렇지 않으면 초기 값은 결정 되지 않습니다.  원래 개체 변수를 통해 참조 된 구조를 동적 범위 내에서 수정 해야, 출구는 구문에서의 결정 되지 않은 값이 구문 때에 결정 되지 않은 값이 있습니다.  
  
 스레드에 의해 할당 된 새 개인 개체 변수를 참조 하는 지시문 구문 어휘 정도.  
  
 제한에는 `private` 절은 다음과 같습니다:  
  
-   지정 된 클래스 형식의 변수는 `private` 절에서 액세스할 수 있는, 명확한 기본 생성자를 갖고 있어야 합니다.  
  
-   지정 된 변수를 `private` 절에 있어야 하지는  **const**\-클래스에 입력 되어 있지 않으면 형식의 정규화 된는 `mutable` 멤버입니다.  
  
-   지정 된 변수를 `private` 절 되었습니다 형식 또는 참조 형식입니다.  
  
-   표시 되는 변수는 `reduction` 절을  **병렬** 지시문에 지정 될 수 없습니다는 `private` 병렬 구문에 바인딩되는 작업 공유 지시문의 절.