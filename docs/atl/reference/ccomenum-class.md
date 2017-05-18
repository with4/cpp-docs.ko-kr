---
title: "CComEnum 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComEnum
- atlcom/ATL::CComEnum
dev_langs:
- C++
helpviewer_keywords:
- CComEnum class
ms.assetid: bff7dd7b-eb6e-4d6e-96ed-2706e66c8b3b
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 72c172d7a619bb4fd1bd265e465653b691c0bc7b
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="ccomenum-class"></a>CComEnum 클래스
이 클래스는 배열을 기반으로 하는 COM 열거자 개체를 정의 합니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class Base,
    const IID* piid, class T, class Copy, class ThreadModel = CcomObjectThreadModel>  
class ATL_NO_VTABLE CComEnum : public CComEnumImpl<Base, piid,
 T,
    Copy>,
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
 동종 [복사 정책 클래스](../../atl/atl-copy-policy-classes.md)합니다.  
  
 `ThreadModel`  
 클래스의 스레딩 모델입니다. 이 매개 변수 프로젝트에서 사용 되는 전역 개체 스레드 모델 기본값으로 사용 됩니다.  
  
## <a name="remarks"></a>주의  
 `CComEnum`배열을 기반으로 하는 COM 열거자 개체를 정의 합니다. 이 클래스는 유사 [CComEnumOnSTL](../../atl/reference/ccomenumonstl-class.md) c + + 표준 라이브러리 컨테이너에 기반 하는 열거자를 구현 합니다. 이 클래스를 사용 하기 위한 일반적인 단계는 다음과 같습니다. 자세한 내용은 참조 [ATL 컬렉션 및 열거자](../../atl/atl-collections-and-enumerators.md)합니다.  
  
## <a name="to-use-this-class"></a>이 클래스를 사용 합니다.  
  
- `typedef`이 클래스의 특수화 합니다.  
  
-   사용 하 여 `typedef` 의 특수화에 템플릿 인수로 `CComObject`합니다.  
  
-   인스턴스를 만들고는 `CComObject` 특수화 합니다.  
  
-   열거자 개체를 호출 하 여 초기화 [CComEnumImpl::Init](../../atl/reference/ccomenumimpl-class.md#init)합니다.  
  
-   열거자 인터페이스는 클라이언트에 반환 합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [CComEnumImpl](../../atl/reference/ccomenumimpl-class.md)  
  
 `CComEnum`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlcom.h  
  
## <a name="example"></a>예제  
 아래 표시 된 코드 만들기 및 초기화 열거자 개체에 대 한 다시 사용할 수 있는 함수를 제공 합니다.  
  
 [!code-cpp[NVC_ATL_COM&#32;](../../atl/codesnippet/cpp/ccomenum-class_1.h)]  
  
 이 템플릿 함수를 구현 하는 것은 `_NewEnum` 아래와 같이 컬렉션 인터페이스의 속성:  
  
 [!code-cpp[NVC_ATL_COM&#33;](../../atl/codesnippet/cpp/ccomenum-class_2.h)]  
  
 이 코드에서는 한 `typedef` 에 대 한 `CComEnum` 의 벡터를 노출 하 **VARIANT**통해 s는 **IEnumVariant** 인터페이스입니다. **CVariantArrayCollection** 클래스를 단순히 전문적 **CreateEnumerator** 열거자 개체의 유형 및 필요한 인수 전달이 작업을 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [클래스 개요](../../atl/atl-class-overview.md)   
 [CComObjectThreadModel](atl-typedefs.md#ccomobjectthreadmodel)   
 [CComEnumImpl 클래스](../../atl/reference/ccomenumimpl-class.md)   
 [CComObjectRootEx 클래스](../../atl/reference/ccomobjectrootex-class.md)

