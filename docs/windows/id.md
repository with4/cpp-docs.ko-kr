---
title: id | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.id
dev_langs:
- C++
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b36a45dad71f2144c3e3d0990ab7715d00e8ff21
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605710"
---
# <a name="id"></a>ID
지정 된 *dispid* (속성 또는 메서드를 인터페이스나 dispinterface의) 멤버 함수에 대 한 매개 변수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ id(  
   dispid  
) ]  
```  
  
### <a name="parameters"></a>매개 변수  
 *dispid*  
 인터페이스 메서드에 대 한 디스패치 ID입니다.  
  
## <a name="remarks"></a>설명  
 합니다 **id** c + + 특성에 동일한 기능을 합니다 [id](http://msdn.microsoft.com/library/windows/desktop/aa367040) MIDL 특성입니다.  
  
## <a name="example"></a>예  
 예를 참조 하세요 [바인딩 가능한](../windows/bindable.md) 사용 하는 방법의 예제 **id**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [메서드 특성](../windows/method-attributes.md)   
 [데이터 멤버 특성](../windows/data-member-attributes.md)   
 [defaultvalue](../windows/defaultvalue.md)   
 [in](../windows/in-cpp.md)   
 [out](../windows/out-cpp.md)   