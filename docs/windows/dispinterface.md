---
title: dispinterface | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.dispinterface
dev_langs:
- C++
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18308cc66e2a01aa5e0396f098096ee9d49416bf
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644332"
---
# <a name="dispinterface"></a>dispinterface
.Idl 파일의 인터페이스를 디스패치 인터페이스로 배치합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
[dispinterface]  
```  
  
## <a name="remarks"></a>설명  
 **dispinterface** C++ 특성이 인터페이스 앞에 오면, 생성된 .idl 파일에서 인터페이스가 라이브러리 블록 내부에 배치됩니다.  
  
 기본 클래스를 지정하지 않으면 디스패치 인터페이스가 `IDispatch`에서 파생됩니다. 디스패치 인터페이스의 멤버에 대한 [id](../windows/id.md) 를 지정해야 합니다.  
  
 MIDL 문서에 있는 [dispinterface](http://msdn.microsoft.com/library/windows/desktop/aa366802) 의 사용 예:  
  
```cpp  
dispinterface helloPro   
   { interface hello; };   
```  
  
 **dispinterface** 특성에 대해 유효하지 않습니다.  
  
## <a name="example"></a>예  
 [dispinterface](../windows/bindable.md) 사용법에 대한 예는 **bindable**의 예를 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**interface**|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [용도별 특성](../windows/attributes-by-usage.md)   
 [uuid](../windows/uuid-cpp-attributes.md)   
 [이중](../windows/dual.md)   
 [사용자 지정](../windows/custom-cpp.md)   
 [object](../windows/object-cpp.md)   
 [__interface](../cpp/interface.md)   