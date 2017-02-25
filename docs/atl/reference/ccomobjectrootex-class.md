---
title: "CComObjectRootEx Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComObjectRootEx"
  - "ATL::CComObjectRootEx<ThreadModel>"
  - "CComObjectRootEx"
  - "ATL::CComObjectRootEx"
  - "ATL.CComObjectRootEx<ThreadModel>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reference counting"
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CComObjectRootEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 개체 참조 개수 관리 끌어냅니다 및 집계 된 개체를 처리 하기 위한 메서드를 제공 합니다.  
  
## 구문  
  
```  
  
      template<  
   class ThreadModel   
>  
class CComObjectRootEx : public CComObjectRootBase  
```  
  
#### 매개 변수  
 `ThreadModel`  
 원하는 스레딩 모델 가진 메서드를 구현 하는 클래스입니다.  설정 하 여 스레딩 모델을 명시적으로 선택할 수 있습니다 `ThreadModel` 에  [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md),  [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), 또는  [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).  설정 하 여 서버의 기본 스레드 모델을 받아들일 수 `ThreadModel` 에  [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) 또는  [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md).  
  
## Members  
  
### 메서드  
  
|||  
|-|-|  
|[CComObjectRootEx](../Topic/CComObjectRootEx::CComObjectRootEx.md)|생성자입니다.|  
|[InternalAddRef](../Topic/CComObjectRootEx::InternalAddRef.md)|집합체에 대 한 참조 횟수를 증가 시킵니다.|  
|[InternalRelease](../Topic/CComObjectRootEx::InternalRelease.md)|집합체에 대 한 참조 횟수를 감소 시킵니다.|  
|[잠금](../Topic/CComObjectRootEx::Lock.md)|스레드 모델을 다중 스레드 되 면 임계 영역 개체의 소유권을 가져옵니다.|  
|[잠금 해제](../Topic/CComObjectRootEx::Unlock.md)|스레드 모델을 다중 스레드 되 면 임계 영역 개체의 소유권을 해제 합니다.|  
  
### CComObjectRootBase 메서드  
  
|||  
|-|-|  
|[FinalConstruct](../Topic/CComObjectRootEx::FinalConstruct.md)|개체에서 필요한 모든 초기화를 수행 하기 위해 클래스를 재정의 합니다.|  
|[FinalRelease](../Topic/CComObjectRootEx::FinalRelease.md)|개체에서 필요한 정리를 수행 하는 클래스에서 재정의 합니다.|  
|[OuterAddRef](../Topic/CComObjectRootEx::OuterAddRef.md)|집계 개체에 대 한 참조 횟수를 증가 시킵니다.|  
|[OuterQueryInterface](../Topic/CComObjectRootEx::OuterQueryInterface.md)|대리자에는 외부  **IUnknown** 의 집합체입니다.|  
|[OuterRelease](../Topic/CComObjectRootEx::OuterRelease.md)|집계 개체에 대 한 참조 횟수를 감소 시킵니다.|  
  
### 정적 함수  
  
|||  
|-|-|  
|[InternalQueryInterface](../Topic/CComObjectRootEx::InternalQueryInterface.md)|위임의  **IUnknown** 의 집합체입니다.|  
|[ObjectMain](../Topic/CComObjectRootEx::ObjectMain.md)|모듈 초기화 및 종료를 위해 파생된 클래스의 개체 맵에 나열 하는 동안 호출 됩니다.|  
  
### 데이터 멤버  
  
|||  
|-|-|  
|[m\_dwRef](../Topic/CComObjectRootEx::m_dwRef.md)|와 `m_pOuterUnknown`, 합집합 부분.  개체의 참조 횟수를 보유할 집계 사용 `AddRef` 및  **릴리스**.|  
|[m\_pOuterUnknown](../Topic/CComObjectRootEx::m_pOuterUnknown.md)|와 `m_dwRef`, 합집합 부분.  개체 포인터를 알 수 없는 외부 채에 집계 되는 경우에 사용 합니다.|  
  
## 설명  
 `CComObjectRootEx`개체 참조 개수 관리 끌어냅니다 및 집계 된 개체를 처리합니다.  개체가 집계 중인 개체가 집계 중인 경우 마우스 포인터를 알 수 없는 외부 보유 경우 개체 참조 카운트를 보유 합니다.  집계 개체에 대 한 `CComObjectRootEx` 방법을 사용 하 여 내부 개체 생성 하는 오류를 처리 하 고 외부 개체에서 내부 인터페이스 출시 되 면 삭제 하거나 내부 개체를 보호 하기 위해 삭제 됩니다.  
  
 COM 서버를 구현 하는 클래스에서 상속 해야 `CComObjectRootEx` 또는  [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md).  
  
 클래스 정의 지정 하는 경우는  [DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md) 매크로, ATL의 인스턴스를 만듭니다  **CComPolyObject \<CYourClass\>** 때  **IClassFactory::CreateInstance** 라고 합니다.  만드는 동안 알 수 없는 외부의 값이 확인 됩니다.  이 경우  **NULL**,  **IUnknown** 집합체를 구현 합니다.  외부 알 수 없는 경우  **NULL**,  **IUnknown** 개체에 대 한 집계를 구현 합니다.  
  
 클래스를 지정 하지 않으면는 `DECLARE_POLY_AGGREGATABLE` 매크로, ATL의 인스턴스를 만듭니다  **CAggComObject \<CYourClass\>** 집계 개체 또는 인스턴스를  **CComObject \<CYourClass\>** 개체를 끌어냅니다.  
  
 장점은 `CComPolyObject` 모두 필요 하지 않는 것입니다 `CComAggObject` 및 `CComObject` 집계 및 끌어냅니다 경우 처리 하는 모듈에서입니다.  단일 `CComPolyObject` 개체는 두 경우 모두 처리 합니다.  따라서 vtable의 복사본 하나만 및 사본이 함수를 모듈에 존재 합니다.  Vtable이 큰 경우이 모듈 크기를 크게 줄일 수 있습니다.  그러나 vtable 작으면 사용 `CComPolyObject` 집계 또는 끌어냅니다 개체에 대 한 적합 하기 때문에 약간 더 큰 모듈 크기에 발생할 수 있습니다으로 `CComAggObject` 및 `CComObject`.  
  
 개체를 집계 하는 경우  [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 는 `CComAggObject` 또는 `CComPolyObject`.  이러한 클래스에 위임 `QueryInterface`, `AddRef`, 및  **릴리스** 호출에 `CComObjectRootEx`의 `OuterQueryInterface`, `OuterAddRef`, 및 `OuterRelease` 를 알 수 없는 외부에 전달할.  일반적으로 재정의 하 여 `CComObjectRootEx::FinalConstruct` 집계 된 모든 개체를 재정의 하 여 클래스에서 `CComObjectRootEx::FinalRelease` 하나를 확보 하려면 개체를 집계 합니다.  
  
 개체가 집계 되지 않는 경우  **IUnknown** 는 `CComObject` 또는 `CComPolyObject`.  이 경우 호출 `QueryInterface`, `AddRef`, 및  **릴리스** 위임 하는 `CComObjectRootEx`의 `InternalQueryInterface`, `InternalAddRef`, 및 `InternalRelease` 실제 작업을 수행 합니다.  
  
## 요구 사항  
 **헤더:**  atlcom.h  
  
## 참고 항목  
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)