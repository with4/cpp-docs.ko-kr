---
title: "로컬 (c + +) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.local
dev_langs:
- C++
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3543adfe0cb25f7946e6ed6c81c4bd66a7b60324
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="local-c"></a>local(C++)
인터페이스 헤더를 사용할 경우 MIDL 컴파일러 헤더 생성기로 사용할 수 있습니다. 개별 함수를 사용할 경우 로컬 없는 스텁을 생성 되는 프로시저를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
[local]  
  
```  
  
## <a name="remarks"></a>설명  
 `local` c + + 특성에 동일한 기능을는 [로컬](http://msdn.microsoft.com/library/windows/desktop/aa367071) MIDL 특성입니다.  
  
## <a name="example"></a>예  
 참조 [call_as](../windows/call-as.md) 사용 하는 방법의 예 `local`합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|`interface`를 인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|**dispinterface**|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [인터페이스 특성](../windows/interface-attributes.md)   
 [메서드 특성](../windows/method-attributes.md)   
 [call_as](../windows/call-as.md)   
