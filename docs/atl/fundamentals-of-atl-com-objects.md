---
title: "Fundamentals of ATL COM Objects | Microsoft Docs"
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
  - "ATL COM objects"
  - "ATL, COM"
  - "COM 개체, ATL"
  - "COM, 및 ATL"
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
caps.latest.revision: 25
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fundamentals of ATL COM Objects
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 그림은 ATL COM 개체를 정의 하는 인터페이스와 클래스 간의 관계를 보여 줍니다.  
  
 ![ATL 구조](../atl/media/vc307y1.png "vc307Y1")  
  
> [!NOTE]
>  이 다이어그램은 보여 주는 `CComObject` 에서 파생 된 `CYourClass` 반면 `CComAggObject` 및 `CComPolyObject` 포함 `CYourClass` 멤버 변수로.  
  
 ATL COM 개체를 정의 하는 방법은 다음 세 가지가 있습니다.  표준 옵션을 사용 하는 것은 `CComObject` 에서 파생 된 클래스 `CYourClass`.  두 번째 옵션을 사용 하 여 집합체를 만드는 것은 `CComAggObject` 클래스입니다.  세 번째 옵션을 사용 하는 것은 `CComPolyObject` 클래스입니다.  `CComPolyObject`혼합으로 역할: 작동할 수 있습니다는 `CComObject` 클래스 또는 as는 `CComAggObject` 먼저 생성 방법에 따라 클래스.  `CComPolyObject` 클래스를 사용하는 방법에 대한 자세한 내용은 [CComPolyObject Class](../atl/reference/ccompolyobject-class.md)를 참조하십시오.  
  
 표준 ATL COM을 사용 하면 두 개체 사용: 내부 개체와 외부 개체입니다.  외부 클라이언트가 내부 개체의 기능에 액세스할 외부 개체에 정의 된 래퍼 함수를 통해.  외부 개체의 형식인 `CComObject`.  
  
 외부 개체가 집계 된 개체를 사용 하면 래퍼 내부 개체의 기능을 제공 하지 않습니다.  대신, 외부 개체 외부 클라이언트에서 직접 액세스할 수 있는 포인터를 제공 합니다.  이 시나리오에서는 외부 개체의 형식인 `CComAggObject`.  내부 개체는 외부 개체의 멤버 변수,의 형식인 `CYourClass`.  
  
 클라이언트를 통해 외부 개체가 내부 개체와 상호 작용할 수 없기 때문에 집계 된 개체를 더욱 효율적입니다.  또한 인터페이스는 집계 개체의 클라이언트에서 직접 사용할 수 있는 외부 개체는 집합체의 기능을 알 필요가 없습니다.  그러나 모든 개체를 집계할 수 있습니다.  집계할 개체에에서 집계를 디자인 해야 합니다.  
  
 ATL 구현  [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 두 단계에서:  
  
-   [CComObject](../atl/reference/ccomobject-class.md),  [CComAggObject](../atl/reference/ccomaggobject-class.md), 또는  [CComPolyObject](../atl/reference/ccompolyobject-class.md) 구현 된  **IUnknown** 방법.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) 또는  [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) 외부 포인터의 참조 횟수 관리  **IUnknown**.  
  
 ATL COM 개체의 다른 측면은 다른 클래스에서 처리 됩니다.  
  
-   [CComCoClass](../atl/reference/ccomcoclass-class.md) 개체의 기본 클래스 팩터리 및 집계 모델을 정의 합니다.  
  
-   [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 의 기본 구현을 제공 된 `IDispatch Interface` 개체에서 이중 인터페이스 부분.  
  
-   [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) 구현 된  **ISupportErrorInfo**  제대로 호출 체인을 사용 하 여 오류 정보를 확인 하는 인터페이스를 전파 합니다.  
  
## 단원 내용  
 [CComObjectRootEx 구현](../atl/implementing-ccomobjectrootex.md)  
 예제 구현에 대 한 COM 맵을 표시 `CComObjectRootEx`.  
  
 [CComObject, CComAggObject 및 CComPolyObject 구현](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)  
 설명에  **DECLARE\_ \* \_AGGREGATABLE** 매크로의 사용에 영향을 `CComObject`, `CComAggObject`, 및 `CComPolyObject`.  
  
 [Idispatch와 Ierrorinfo를 지원합니다.](../atl/supporting-idispatch-and-ierrorinfo.md)  
 나열 ATL 구현 클래스를 지 원하는 데 사용 하는 `IDispatch` 및  **IErrorInfo** 인터페이스.  
  
 [IDispEventImpl 지원](../atl/supporting-idispeventimpl.md)  
 클래스에 대 한 연결 지점을 구현 하는 단계에 설명 합니다.  
  
 [기본 클래스 팩터리 및 집합체 모델 변경](../atl/changing-the-default-class-factory-and-aggregation-model.md)  
 기본 클래스 팩터리 및 집계 모델을 변경 하려면 사용 하는 매크로 표시 합니다.  
  
 [집합체 만들기](../atl/creating-an-aggregated-object.md)  
 집합체를 만드는 단계를 나열 합니다.  
  
## 관련 단원  
 [ATL 프로젝트 만들기](../atl/reference/creating-an-atl-project.md)  
 ATL COM 개체를 만드는 방법에 설명 합니다.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 액티브 템플릿 라이브러리를 사용 하 여 프로그래밍 하는 방법에 개념 항목에 대 한 링크를 제공 합니다.  
  
## 참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)