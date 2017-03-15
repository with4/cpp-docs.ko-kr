---
title: "원격 자동화의 기능은 무엇입니까? | Microsoft Docs"
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
helpviewer_keywords: 
  - "원격 자동화, DCOM"
ms.assetid: 269ad218-e164-40ef-9b87-25fcc8ba21de
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 원격 자동화의 기능은 무엇입니까?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

원격 자동화를 사용하면 프로그램이  `IDispatch`  에서 다른 한 컴퓨터에서 구현하도록 호출할 수 있습니다.  또한 자동화가 필요한 다른 인터페이스를 지원합니다. 특히 컬렉션 지원에 대한 **IEnumVARIANT** 일반적인 자동화같은 다른 COM 인터페이스를 배포하는 기능은 제공하지 않습니다 \(**IUnknown**를 제외한\), 자동화에 의해 지원 되는 데이터 형식에 대해서만 마샬링이 지원이 포함됩니다.  
  
 시설의 이 세트는 프로그램이 네트워크를 통해 액세스 노드에서 실행되는 개체의 컬렉션이나 자동화 개체를 반환하는 것을 포함하여 메서드와 속성을 액세스 할 수 있습니다.  클라이언트 시스템이 적절한 소프트웨어를 실행하는 경우, 그것은 서버가 \(이벤트에 개념적으로 비슷하지만 이것이 유일한 32 비트 및 64 비트 클라이언트를 위해 일하는 자동화 기능을 사용하여 다시 클라이언트에 콜백하는 것은 가능합니다\) 동일한 메커니즘을 사용하지 않습니다.  
  
 어플리케이션은 원격 자동화 서버로 동작 할 경우, 그것은 \(즉 "로컬 서버"라고하기보다는 "INPROC 서버"\) 실행으로 구현되어야 합니다.  
  
## 참고 항목  
 [원격 자동화가 필요한 경우](../mfc/where-does-remote-automation-fit-in-q.md)   
 [DCOM의 역사](../mfc/history-of-dcom.md)