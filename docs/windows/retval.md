---
title: retval | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.retval
dev_langs:
- C++
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c0bf7ecd989b51a17c853c6d2986db204c3ce34
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33888723"
---
# <a name="retval"></a>retval
멤버의 반환 값을 받는 매개 변수를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
[retval]  
  
```  
  
## <a name="remarks"></a>설명  
 **retval** c + + 특성에 동일한 기능을는 [retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) MIDL 특성입니다.  
  
 **retval** 마지막 인수는 함수 선언에서에 표시 되어야 합니다.  
  
## <a name="example"></a>예제  
 예를 참조 [바인딩 가능한](../windows/bindable.md) 의 샘플 사용에 대 한 **retval**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 매개 변수를 인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|**out**|  
|**잘못된 특성**|**in**|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [매개 변수 특성](../windows/parameter-attributes.md)   
 [메서드 특성](../windows/method-attributes.md)   
