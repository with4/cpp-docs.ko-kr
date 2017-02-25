---
title: "ActiveX 컨트롤에 이벤트 처리기 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], 이벤트"
  - "이벤트[C++], ActiveX 컨트롤"
ms.assetid: c076386f-c78b-4dc9-9201-a544252d5337
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ActiveX 컨트롤에 이벤트 처리기 설정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ActiveX 컨트롤을 프로그래밍하여 이벤트에 응답할 수 있습니다.  **ControlEvents** 속성을 사용하여 컨트롤에서 사용할 수 있는 이벤트를 보고 이벤트 처리기를 만들 수 있습니다.  일반적으로 이벤트 처리는 데이터 소스 쿼리의 변경 내용을 트래핑하기 위해 수행됩니다.  변경 내용에는 다음이 포함됩니다.  
  
-   조회 구현.  DBCombo 상자와 같은 컨트롤에서 값을 변경하면 변경 이벤트를 트래핑하여 데이터 컨트롤의 쿼리를 업데이트합니다.  
  
-   마스터\-세부 관계 구현.  두 데이터 컨트롤 중 하나는 대화 상자의 마스터 부분에 추가되고 다른 하나는 대화 상자의 세부 정보 부분에 추가됩니다.  첫 번째 데이터 소스가 변경될 때마다 두 번째 데이터 소스의 쿼리는 이벤트 처리기를 통해 업데이트됩니다.  
  
-   오류 트래핑.  대부분의 컨트롤에는 오류 이벤트가 있으며, 이 오류 이벤트에서 오류 처리기를 작성할 수 있습니다. [오류 트래핑](../../data/ado-rdo/error-trapping.md)을 참조하십시오.  
  
 자세한 내용은 [함수에 메시지 매핑](../../mfc/reference/mapping-messages-to-functions.md)을 참조하십시오.  
  
## 참고 항목  
 [ActiveX 컨트롤 사용](../../data/ado-rdo/using-activex-controls.md)