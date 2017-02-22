---
title: "IPersistStorageImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IPersistStorageImpl"
  - "ATL::IPersistStorageImpl<T>"
  - "ATL.IPersistStorageImpl<T>"
  - "IPersistStorageImpl"
  - "ATL.IPersistStorageImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPersistStorageImpl class"
  - "저장소, ATL"
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IPersistStorageImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에서 구현 된  [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) 인터페이스.  
  
> [!IMPORTANT]
>  이 클래스와 해당 멤버를 실행 하는 응용 프로그램에서 사용할 수 있는 [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## 구문  
  
```  
  
      template <  
class T  
>  
class ATL_NO_VTABLE IPersistStorageImpl :  
public IPersistStorage  
```  
  
#### 매개 변수  
 `T`  
 파생 클래스에서 `IPersistStorageImpl`.  
  
## Members  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[IPersistStorageImpl::GetClassID](../Topic/IPersistStorageImpl::GetClassID.md)|개체의 CLSID를 검색합니다.|  
|[IPersistStorageImpl::HandsOffStorage](../Topic/IPersistStorageImpl::HandsOffStorage.md)|모든 저장소 개체를 해제 하 고 HandsOff 모드 입력 개체에 지시 합니다.  ATL 구현을 반환 `S_OK`.|  
|[IPersistStorageImpl::InitNew](../Topic/IPersistStorageImpl::InitNew.md)|새 저장소를 초기화합니다.|  
|[IPersistStorageImpl::IsDirty](../Topic/IPersistStorageImpl::IsDirty.md)|마지막으로 저장 된 이후 개체의 데이터가 변경 되었는지 여부를 확인 합니다.|  
|[IPersistStorageImpl::Load](../Topic/IPersistStorageImpl::Load.md)|개체의 속성에 지정 된 저장소에서 로드합니다.|  
|[IPersistStorageImpl::Save](../Topic/IPersistStorageImpl::Save.md)|개체의 속성에 지정 된 저장소에 저장합니다.|  
|[IPersistStorageImpl::SaveCompleted](../Topic/IPersistStorageImpl::SaveCompleted.md)|개체를 저장소 개체에 쓸 수 있는 표준 모드를 반환할 수 알립니다.  ATL 구현을 반환 `S_OK`.|  
  
## 설명  
 `IPersistStorageImpl`구현 된  [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) 개체 로드를 요청 하는 클라이언트 수 있도록 인터페이스와 영구 저장소를 사용 하 여 데이터를 저장 합니다.  
  
 클래스는이 클래스의 구현에 필요한 `T` 을 구현 하는 `IPersistStreamInit` 인터페이스를 통해 사용할 수 있는 `QueryInterface`.  일반적으로 해당 클래스 즉, `T` 파생 되어야  [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), 항목을 제공 `IPersistStreamInit` 에  [COM 맵](../Topic/BEGIN_COM_MAP.md)을, 하는  [속성 맵](../Topic/BEGIN_PROP_MAP.md) 클래스의 영구 데이터를 설명 합니다.  
  
 **관련된 기사** [ATL 자습서](../../atl/active-template-library-atl-tutorial.md),  [ATL 프로젝트 만들기](../../atl/reference/creating-an-atl-project.md)  
  
## 상속 계층 구조  
 `IPersistStorage`  
  
 `IPersistStorageImpl`  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [Storages and Streams](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [IPersistStreamInitImpl Class](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [IPersistPropertyBagImpl Class](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)