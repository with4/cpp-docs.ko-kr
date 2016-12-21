---
title: "IPropertyNotifySinkCP Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IPropertyNotifySinkCP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "연결 지점[C++], 관리"
  - "IPropertyNotifySinkCP class"
  - "sinks, notifying of changes"
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPropertyNotifySinkCP Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에서 노출  [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) 인터페이스로 연결 가능 개체에 보내기 인터페이스.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template< class   
      T  
      , class  
      CDV   
      = CComDynamicUnkArray >  
class IPropertyNotifySinkCP :   
public IConnectionPointImpl< T, &IID_IPropertyNotifySink, CDV>  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IPropertyNotifySinkCP`.  
  
 `CDV`  
 연결 지점 및 해당 싱크 간의 연결을 관리 하는 클래스입니다.  기본값은  [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), 무제한 연결을 허용 합니다.  또한 사용할 수 있습니다  [CComUnkArray](../../atl/reference/ccomunkarray-class.md), 고정 된 연결의 수를 지정 합니다.  
  
## 설명  
 `IPropertyNotifySinkCP`모든 메서드는 기본 클래스를 통해 상속  [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md).  
  
 [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) 인터페이스는 싱크 개체에 대 한 속성 변경 알림을 받을 수 있습니다.  클래스 `IPropertyNotifySinkCP` 으로 연결 가능 개체에 보내기 인터페이스에이 인터페이스를 노출 합니다.  클라이언트 구현 해야는 `IPropertyNotifySink` 메서드를 싱크 합니다.  
  
 파생 클래스에서 `IPropertyNotifySinkCP` 나타내는 연결 지점을 만드는 시기는 `IPropertyNotifySink` 인터페이스.  
  
 ATL 연결 지점 사용에 대 한 자세한 내용은  [연결점](../../atl/atl-connection-points.md).  
  
## 요구 사항  
 **헤더:**  atlctl.h  
  
## 참고 항목  
 [IConnectionPointImpl Class](../../atl/reference/iconnectionpointimpl-class.md)   
 [IConnectionPointContainerImpl Class](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)