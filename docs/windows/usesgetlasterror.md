---
title: usesgetlasterror | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.usesgetlasterror
dev_langs:
- C++
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 399b9fbbcf4b449f5f91beaea89c403d120d0a21
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="usesgetlasterror"></a>usesgetlasterror
해당 함수를 호출할 때 오류가 경우 다음 호출자가 호출할 수 있도록 다음 호출자에 게 지시 `GetLastError` 를 오류 코드를 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
[usesgetlasterror]  
  
```  
  
## <a name="remarks"></a>설명  
 **usesgetlasterror** c + + 특성에 동일한 기능을는 [usesgetlasterror](http://msdn.microsoft.com/library/windows/desktop/aa367297) MIDL 특성입니다.  
  
## <a name="example"></a>예제  
 참조는 [idl_module](../windows/idl-module.md) 사용 하는 방법의 예는 샘플에 대 한 **usesgetlasterror**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**모듈** 특성|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
