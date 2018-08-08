---
title: propputref | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.propputref
dev_langs:
- C++
helpviewer_keywords:
- propputref attribute
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fc11561401ff34b629fecdc31a00ffb845d6a2d8
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606802"
---
# <a name="propputref"></a>propputref
값 대신 참조를 사용 하는 속성 설정 함수를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[propputref]  
```  
  
## <a name="remarks"></a>설명  
 합니다 **propputref** c + + 특성에 동일한 기능을 합니다 [propputref](http://msdn.microsoft.com/library/windows/desktop/aa367147) MIDL 특성입니다.  
  
## <a name="example"></a>예  
 예를 참조 하세요 [bindable](../windows/bindable.md) 의 샘플 사용에 대 한 **propputref**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|`propget`, `propput`|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [메서드 특성](../windows/method-attributes.md)   
 [propget](../windows/propget.md)   
 [propput](../windows/propput.md)   