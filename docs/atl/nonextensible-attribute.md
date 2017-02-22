---
title: "nonextensible Attribute | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "nonextensible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "이중 인터페이스, nonextensible attribute"
  - "nonextensible attribute"
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# nonextensible Attribute
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이중 인터페이스 실행된 시 확장 될 경우 \(즉, 메서드 또는 속성을 통해 제공 되지 않습니다  **IDispatch::Invoke** vtable을 통해 사용할 수 없는\)을 적용 해야는  **nonextensible** 인터페이스 정의에 특성.  이 특성에 전체 코드를 컴파일 타임에 확인할 수 있도록 사용할 수 있는 클라이언트 언어 \(예: Visual Basic\) 정보를 제공 합니다.  이 특성을 지정 하지 않으면 버그 런타임까지 클라이언트 코드에서 숨겨진 남아 있을 수 있습니다.  
  
 에 대 한 자세한 내용은  **nonextensible** 특성과 참조 하십시오 예를 들어,  [nonextensible](../windows/nonextensible.md).  
  
## 참고 항목  
 [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md)