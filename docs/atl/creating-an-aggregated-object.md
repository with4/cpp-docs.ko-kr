---
title: "Creating an Aggregated Object | Microsoft Docs"
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
  - "aggregate objects [C++], 만들기"
  - "aggregation [C++], creating aggregated objects"
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating an Aggregated Object
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

집계 대리자  **IUnknown** 호출을 외부 개체에 대 한 포인터를 제공 합니다.  **IUnknown** 내부 개체입니다.  
  
### 집계 개체를 만들려면  
  
1.  추가 된  **IUnknown** 클래스에 대 한 포인터 및 개체를 초기화  **NULL** 생성자에.  
  
2.  재정의  [FinalConstruct](../Topic/CComObjectRootEx::FinalConstruct.md) 집계를 만들 수 있습니다.  
  
3.  사용 된  **IUnknown** 포인터를 1 단계에서 두 번째 매개 변수로 정의  [COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md) 매크로.  
  
4.  재정의  [FinalRelease](../Topic/CComObjectRootEx::FinalRelease.md) 를 해제 하는  **IUnknown** 포인터.  
  
> [!NOTE]
>  사용 하 고 인터페이스 집합체 중에서 해제 하는 경우 `FinalConstruct`, 추가 해야는  [DECLARE\_PROTECT\_FINAL\_CONSTRUCT](../Topic/DECLARE_PROTECT_FINAL_CONSTRUCT.md) 매크로 클래스 개체를 정의 합니다.  
  
## 참고 항목  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)