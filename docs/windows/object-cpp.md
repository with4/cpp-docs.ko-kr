---
title: object (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.object
dev_langs:
- C++
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2c0705c5d841b63cd3f537ab39dbbe9122fea869
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607912"
---
# <a name="object-c"></a>object(C++)
사용자 지정 인터페이스를 식별합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[object]  
```  
  
## <a name="remarks"></a>설명  
 인터페이스 정의 이전 하는 경우는 **개체** c + + 특성을 사용 하면 사용자 지정 인터페이스.idl 파일에 배치 하는 인터페이스입니다.  
  
 개체를 사용 하 여 표시 된 모든 인터페이스에서 상속 해야 `IUnknown`합니다. 기본 인터페이스에서 상속 하는 경우이 조건이 만족 `IUnknown`합니다. 상속 된 기본 인터페이스가 없는 경우 `IUnknown`, 컴파일러에 표시 된 인터페이스 하면 **개체** 에서 파생 `IUnknown`합니다.  
  
## <a name="example"></a>예  
 참조 [nonbrowsable](../windows/nonbrowsable.md) 사용 하는 방법의 예제 **개체**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**interface**|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [인터페이스 특성](../windows/interface-attributes.md)   
 [이중](../windows/dual.md)   
 [Dispinterface](../windows/dispinterface.md)   
 [사용자 지정](../windows/custom-cpp.md)   
 [__interface](../cpp/interface.md)   