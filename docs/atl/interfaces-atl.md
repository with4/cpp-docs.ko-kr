---
title: "Interfaces (ATL) | Microsoft Docs"
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
  - "COM 인터페이스"
  - "인터페이스, COM"
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Interfaces (ATL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

인터페이스는 개체 기능을 외부로 노출 하는 방식입니다.  COM에서 인터페이스 테이블 개체에 의해 구현 되는 함수 포인터 \(예: C\+\+ vtable\)입니다.  테이블 인터페이스를 나타내며 가리키는 함수는 해당 인터페이스의 메서드입니다.  개체는 선택한 만큼의 인터페이스를 노출할 수 있습니다.  
  
 각 인터페이스에서 기본 COM 인터페이스를 기반으로  [IUnknown](../atl/iunknown.md).  메서드를  **IUnknown** 개체에서 노출 하는 다른 인터페이스에 대 한 탐색을 허용 합니다.  
  
 또한, 각 인터페이스는 고유한 IID \(인터페이스 ID\) 지정 됩니다.  이 고유성 쉽게 인터페이스 버전 관리를 지원할 수 있습니다.  새 버전의 인터페이스는 새로운 IID 가진 새 인터페이스 간단 하 게 됩니다.  
  
> [!NOTE]
>  표준 COM 및 OLE 인터페이스 Iid 미리 정의 됩니다.  
  
## 참고 항목  
 [COM 소개](../atl/introduction-to-com.md)   
 [COM Objects and Interfaces](http://msdn.microsoft.com/library/windows/desktop/ms690343)