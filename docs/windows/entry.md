---
title: 항목 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.entry
dev_langs:
- C++
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 933fc1db2a890fedd9d725c49bbeb6c363e2f4c8
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569640"
---
# <a name="entry"></a>entry
DLL의 진입점을 식별 하 여 모듈에는 내보낸된 함수 또는 상수를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ entry(  
   id  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *ID*  
 진입점의 ID입니다.  
  
## <a name="remarks"></a>설명  
 합니다 **항목** c + + 특성에 동일한 기능을 합니다 [항목](http://msdn.microsoft.com/library/windows/desktop/aa366815) MIDL 특성입니다.  
  
## <a name="example"></a>예  
 예를 참조 하세요 [idl_module](../windows/idl-module.md) 의 사용 예에 대 한 **항목**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|`idl_module` 특성|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   