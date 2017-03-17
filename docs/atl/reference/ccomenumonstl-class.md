---
title: "CComEnumOnSTL 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComEnumOnSTL
- atlcom/ATL::CComEnumOnSTL
dev_langs:
- C++
helpviewer_keywords:
- CComEnumOnSTL class
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 23e234f82ce8c77a6ebde50070475deeab59f362
ms.lasthandoff: 02/24/2017

---
# <a name="ccomenumonstl-class"></a>CComEnumOnSTL 클래스
이 클래스는 c + + 표준 라이브러리 컬렉션에 따라 COM 열거자 개체를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class CollType, class ThreadModel = CComObjectThreadModel>  
class ATL_NO_VTABLE CComEnumOnSTL : public IEnumOnSTLImpl<Base, piid,
 T,
    Copy,
 CollType>,
    public CComObjectRootEx<ThreadModel>
```  
  
#### <a name="parameters"></a>매개 변수  
 `Base`  
 COM 열거자 ( [IEnumXXXX](https://msdn.microsoft.com/library/ms680089.aspx)) 인터페이스입니다.  
  
 `piid`  
 열거자 인터페이스의 인터페이스 ID에 대 한 포인터입니다.  
  
 `T`  
 열거자 인터페이스에 의해 노출 되는 항목의 형식입니다.  
  
 `Copy`  
 A [정책을 복사](../../atl/atl-copy-policy-classes.md) 클래스입니다.  
  
 `CollType`  
 C + + 표준 라이브러리 컨테이너 클래스입니다.  
  
## <a name="remarks"></a>주의  
 `CComEnumOnSTL`c + + 표준 라이브러리 컬렉션에 따라 COM 열거자 개체를 정의 합니다. 이 클래스는 자체적으로 또는 함께에서 사용할 수 [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md)합니다. 이 클래스를 사용 하기 위한 일반적인 단계는 다음과 같습니다. 자세한 내용은 참조 [ATL 컬렉션 및 열거자](../../atl/atl-collections-and-enumerators.md)합니다.  
  
## <a name="to-use-this-class-with-icollectiononstlimpl"></a>이 클래스를 ICollectionOnSTLImpl 사용:  
  
- `typedef`이 클래스의 특수화 합니다.  
  
-   사용 하 여 `typedef` 의 특수화에 최종 템플릿 인수로 `ICollectionOnSTLImpl`합니다.  
  
 참조 [ATL 컬렉션 및 열거자](../../atl/atl-collections-and-enumerators.md) 대 한 예제입니다.  
  
## <a name="to-use-this-class-independently-of-icollectiononstlimpl"></a>이 클래스를 사용 하려면이 ICollectionOnSTLImpl 독립적으로:  
  
- `typedef`이 클래스의 특수화 합니다.  
  
-   사용 하 여 `typedef` 의 특수화에 템플릿 인수로 `CComObject`합니다.  
  
-   인스턴스를 만들고는 `CComObject` 특수화 합니다.  
  
-   열거자 개체를 호출 하 여 초기화 [IEnumOnSTLImpl::Init](../../atl/reference/ienumonstlimpl-class.md#init)합니다.  
  
-   열거자 인터페이스는 클라이언트에 반환 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)  
  
 `CComEnumOnSTL`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
## <a name="example"></a>예제  
 아래 표시 된 코드 생성 및 열거자 개체의 초기화를 처리 하는 제네릭 함수를 제공 합니다.  
  
 [!code-cpp[NVC_ATL_COM&#34;](../../atl/codesnippet/cpp/ccomenumonstl-class_1.h)]  
  
 이 템플릿 함수를 구현 하는 것은 `_NewEnum` 아래와 같이 컬렉션 인터페이스의 속성:  
  
 [!code-cpp[#35 NVC_ATL_COM](../../atl/codesnippet/cpp/ccomenumonstl-class_2.h)]  
  
 이 코드에서는 한 `typedef` 에 대 한 `CComEnumOnSTL` 의 벡터를 노출 하 `CComVariant`방법으로 s는 **IEnumVariant** 인터페이스입니다. **CVariantCollection** 클래스를 단순히 전문적 **CreateSTLEnumerator** 이 형식의 열거자 개체를 사용 하도록 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)   
 [ATLCollections 샘플: ICollectionOnSTLImpl, CComEnumOnSTL 및 사용자 지정 복사 정책 클래스](../../visual-cpp-samples.md)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [IEnumOnSTLImpl 클래스](../../atl/reference/ienumonstlimpl-class.md)

