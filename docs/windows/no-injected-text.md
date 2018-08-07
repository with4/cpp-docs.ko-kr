---
title: no_injected_text | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.no_injected_text
dev_langs:
- C++
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c1b629f805cf07736dd7988cac6afb857a23b5e5
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603422"
---
# <a name="noinjectedtext"></a>no_injected_text
컴파일러 특성 사용으로 인해 코드를 삽입 하지 못하도록 방지 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ no_injected_text(  
   boolean  
) ];  
```  
  
#### <a name="parameters"></a>매개 변수  
 *부울* (선택 사항)  
 **true 이면** 없는 코드를 삽입 하려는 경우 **false** 코드를 삽입할 수 있도록 합니다. **true** 가 기본값입니다.  
  
## <a name="remarks"></a>설명  
 가장 일반적으로 사용 합니다 **no_injected_text** 에서 c + + 특성은는 [/Fx](../build/reference/fx-merge-injected-code.md) 삽입 하는 컴파일러 옵션을를 **no_injected_text** 특성이.mrg 파일에.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|원하는 위치|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 특성](../windows/compiler-attributes.md)   