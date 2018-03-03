---
title: version (c + +) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.version
dev_langs:
- C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db6c31df932890799f68e2ae466b0a927f0f999f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="version-c"></a>version(C++)
클래스의 여러 버전 간에 특정 버전을 식별합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ version(  
   "version"  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *version*  
 Coclass의 버전 번호입니다. 지정 하지 않으면 1.0.idl 파일에 배치 됩니다.  
  
## <a name="remarks"></a>설명  
 **버전** c + + 특성에 동일한 기능을는 [버전](http://msdn.microsoft.com/library/windows/desktop/aa367306) MIDL 특성과 생성된 된.idl 파일에 전달 됩니다.  
  
## <a name="example"></a>예  
 참조는 [바인딩 가능한](../windows/bindable.md) 의 샘플 사용에 대 한 예제 **버전**합니다.  
  
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
 [컴파일러 특성](../windows/compiler-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
