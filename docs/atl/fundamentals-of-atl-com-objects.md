---
title: ATL COM 개체의 기본 사항 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- COM, and ATL
- ATL, COM
- ATL COM objects
- COM objects, ATL
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 955f8f6be96feeaf0f22f02c125dcdeaceb8e7f8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="fundamentals-of-atl-com-objects"></a>ATL COM 개체의 기본 사항
다음 그림에서는 클래스 및 ATL COM 개체를 정의 하는 데 사용 되는 인터페이스 간의 관계를 보여 줍니다.  
  
 ![ATL 구조](../atl/media/vc307y1.gif "vc307y1")  
  
> [!NOTE]
>  이 다이어그램을 보여 줍니다 `CComObject` 에서 파생 된 `CYourClass` 반면 `CComAggObject` 및 `CComPolyObject` 포함 `CYourClass` 멤버 변수로 합니다.  
  
 ATL COM 개체를 정의 하는 방법은 세 가지가 있습니다. 표준 옵션은 사용 하 여 `CComObject` 클래스에서 파생 된 `CYourClass`합니다. 두 번째 옵션에서 사용 하 여 집계 개체를 만드는 것은 `CComAggObject` 클래스입니다. 세 번째 옵션은 사용 하 여 `CComPolyObject` 클래스입니다. `CComPolyObject` 역할을 하이브리드: 작동할 수 있습니다는 `CComObject` 클래스 또는 `CComAggObject` 처음 생성 되는 방법에 따라 클래스입니다. 사용 하는 방법에 대 한 자세한 내용은 `CComPolyObject` 클래스를 참조 하십시오. [CComPolyObject 클래스](../atl/reference/ccompolyobject-class.md)합니다.  
  
 두 개체를 사용 하는 표준 ATL COM을 사용 하는 경우: 외부 개체 및 내부 개체입니다. 외부 클라이언트 외부 개체에 정의 된 래퍼 함수를 통해 내부 개체의 기능에 액세스 합니다. 외부 개체에 유형임 `CComObject`합니다.  
  
 집계 개체를 사용 하면 외부 개체는 내부 개체의 기능에 대 한 래퍼 제공 하지 않습니다. 대신, 외부 개체가 외부 클라이언트에서 직접 액세스 하는 포인터를 제공 합니다. 이 시나리오에서 외부 개체 형식의 `CComAggObject`합니다. 내부 개체는 외부 개체의 멤버 변수 아니며 형식의 `CYourClass`합니다.  
  
 클라이언트 내부 개체와 상호 작용 하는 외부 개체를 진행할 수 없기 때문에 집계 개체는 일반적으로 더 효율적입니다. 또한 외부 개체가 없는 집계 된 개체의 기능에 알아야 집계 된 개체의 인터페이스는 클라이언트에서 직접 사용할 수 있다고 가정 합니다. 그러나 일부 개체를 집계할 수 있습니다. 집계 개체에 대 한 집계 고려에서 하 여 디자인 해야 합니다.  
  
 ATL 구현 [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) 이라는 두 단계로 진행에서 합니다.  
  
-   [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), 또는 [CComPolyObject](../atl/reference/ccompolyobject-class.md) 구현 하는 **IUnknown** 메서드.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) 또는 [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) 관리의 외부 포인터 및 참조 횟수 **IUnknown**합니다.  
  
 ATL COM 개체의 다른 측면은 다른 클래스에 의해 처리 됩니다.  
  
-   [CComCoClass](../atl/reference/ccomcoclass-class.md) 개체의 기본 클래스 팩터리와 집계 모델을 정의 합니다.  
  
-   [IDispatchImpl](../atl/reference/idispatchimpl-class.md) 의 기본 구현을 제공는 `IDispatch Interface` 개체에는 이중 인터페이스의 부분입니다.  
  
-   [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) 구현 하는 **ISupportErrorInfo** 인터페이스 오류 정보를 호출 체인 올바르게 전파 될 수 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [CComObjectRootEx 구현](../atl/implementing-ccomobjectrootex.md)  
 예제에서는 COM 맵 엔트리를 구현 하기 위한 표시 `CComObjectRootEx`합니다.  
  
 [CComObject, CComAggObject 및 CComPolyObject 구현](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)  
 에 대해 설명 방법을 **DECLARE_\*_AGGREGATABLE** 매크로의 사용에 영향을 `CComObject`, `CComAggObject`, 및 `CComPolyObject`합니다.  
  
 [IDispatch 및 IErrorInfo 지원](../atl/supporting-idispatch-and-ierrorinfo.md)  
 지 원하는 데 ATL 구현 클래스를 나열는 `IDispatch` 및 **IErrorInfo** 인터페이스입니다.  
  
 [IDispEventImpl 지원](../atl/supporting-idispeventimpl.md)  
 클래스에 대 한 연결 지점을 구현 하는 단계를 설명 합니다.  
  
 [기본 클래스 팩터리 및 집계 모델 변경](../atl/changing-the-default-class-factory-and-aggregation-model.md)  
 기본 클래스 팩터리와 집계 모델을 변경 하는 데 매크로 대해 설명 합니다.  
  
 [집계 개체 만들기](../atl/creating-an-aggregated-object.md)  
 집계 개체를 만드는 단계를 나열 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [ATL 프로젝트 만들기](../atl/reference/creating-an-atl-project.md)  
 ATL COM 개체를 만드는 방법에 대 한 정보를 제공 합니다.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 액티브 템플릿 라이브러리를 사용하여 프로그래밍하는 방법에 대한 개념 항목의 링크를 제공합니다.  
  
## <a name="see-also"></a>참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)

