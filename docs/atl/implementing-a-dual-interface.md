---
title: "Implementing a Dual Interface | Microsoft Docs"
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
  - "이중 인터페이스, 구현"
  - "IDispatchImpl 클래스, implementing dual interfaces"
ms.assetid: d1da3633-b445-4dcd-8a0a-3efdafada3ea
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Implementing a Dual Interface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

사용 하 여 이중 인터페이스를 구현할 수는  [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 의 기본 구현을 제공 하는 클래스는 `IDispatch` 이중 인터페이스의 메서드.  자세한 내용은 [Implementing the IDispatch Interface](http://msdn.microsoft.com/ko-kr/0e171f7f-0022-4e9b-ac8e-98192828e945)를 참조하십시오.  
  
 이 클래스를 사용.  
  
-   형식 라이브러리에서 이중 인터페이스를 정의 합니다.  
  
-   클래스의 특수화에서 파생 될 `IDispatchImpl` \(정보 인터페이스 및 형식 라이브러리에 대 한 템플릿 인수로 전달\).  
  
-   \(또는 항목\)을 이중 인터페이스를 통해 노출 하는 COM 맵에 추가 `QueryInterface`.  
  
-   인터페이스의 vtable 부분 클래스에 구현 합니다.  
  
-   런타임에 인터페이스 정의가 포함 된 형식 라이브러리에 개체를 사용할 수 있는지 확인 하십시오.  
  
## ATL 단순 개체 마법사  
 새 인터페이스와이 구현 하는 새 클래스를 만들려면 수는  [ATL 클래스 추가 대화 상자](../ide/add-class-dialog-box.md), 다음의  [ATL 단순 개체 마법사](../atl/reference/atl-simple-object-wizard.md).  
  
## 인터페이스 구현 마법사  
 기존 인터페이스를 사용할 경우 사용할 수 있는  [인터페이스 구현 마법사](../atl/reference/adding-a-new-interface-in-an-atl-project.md) 필요한 기본 클래스, COM 맵을 뼈대 메서드 구현은 기존 클래스에 추가 합니다.  
  
> [!NOTE]
>  형식 라이브러리의 주 버전과 부 버전 번호를 템플릿 인수로 전달 되도록 생성 된 기본 클래스를 조정 해야 하면 `IDispatchImpl` 기본 클래스입니다.  인터페이스 구현 마법사는 형식 라이브러리 버전 번호를 검사 하지 않습니다.  
  
## IDispatch 구현  
 사용할 수는 `IDispatchImpl` 기본 바로 해당 항목의 COM 맵에 지정 된 dispinterface의 구현을 제공 하는 클래스 \(사용 하는  [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md) 또는  [COM\_INTERFACE\_ENTRY\_IID](../Topic/COM_INTERFACE_ENTRY_IID.md) 매크로\) 해당 이중 인터페이스를 설명 하는 형식 라이브러리를가지고 있다면.  매우 일반적인 구현 되는 `IDispatch` 예를 들어 이런 방식이으로 인터페이스.  ATL 단순 개체 마법사 및 구현 된 인터페이스 두 가정 구현 하려는 마법사 `IDispatch` 이 이렇게 하므로 이러한 추가 됩니다 해당 항목 지도에.  
  
> [!NOTE]
>  ATL에서 제공 된  [IDispEventImpl](../atl/reference/idispeventimpl-class.md) 및  [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) dispinterfaces 호환 이중 인터페이스 정의를 포함 하는 형식 라이브러리 없이 구현 하는 데 도움이 되는 클래스.  
  
## 참고 항목  
 [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md)