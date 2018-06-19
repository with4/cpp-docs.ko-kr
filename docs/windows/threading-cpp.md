---
title: 스레딩 (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.threading
dev_langs:
- C++
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f21ea8c16b4e09a5ad1845a10797be00f91b0d8f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891326"
---
# <a name="threading-c"></a>threading(C++)
COM 개체에 대 한 스레딩 모델을 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ threading(  
   model=enumeration  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 ***모델*** (선택 사항)  
 다음 스레딩 모델 중 하나입니다.  
  
-   **아파트** (아파트 스레딩)  
  
-   **중립** (사용자 인터페이스 없이.NET Framework 구성 요소)  
  
-   **단일** (단순 스레딩)  
  
-   **무료** (자유 스레딩)  
  
-   **둘 다** (아파트 및 자유 스레딩)  
  
 기본값은 **아파트**합니다.  
  
## <a name="remarks"></a>설명  
 **스레딩** c + + 특성 생성된 된.idl 파일에 표시 되지 않지만 COM 개체의 구현에 사용 됩니다.  
  
 ATL 프로젝트의 경우는 [coclass](../windows/coclass.md) 특성이 있으면도에서 지정한 스레딩 모델 *모델* 를 템플릿 매개 변수로 전달 되는 [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) 클래스 의해 삽입 된 **coclass** 특성입니다.  
  
 **스레딩** 특성에 대 한 액세스를 보호도 [event_source](../windows/event-source.md)합니다.  
  
## <a name="example"></a>예제  
 참조는 [사용이 허가 된](../windows/licensed.md) 의 샘플 사용에 대 한 예제 **스레딩**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**class**, `struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|**coclass**|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [COM 특성](../windows/com-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [이전 코드 (Visual c + +)를 위한 다중 스레딩 지원](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [중립 아파트](http://msdn.microsoft.com/library/windows/desktop/ms681813)   
