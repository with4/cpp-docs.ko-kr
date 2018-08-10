---
title: version (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.version
dev_langs:
- C++
helpviewer_keywords:
- version attribute
- version information, version attribute
ms.assetid: db6ce5d8-82c2-4329-b1a8-8ca2f67342cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1ef27e86ae356ddc67555390b7e053daa8d32a09
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013355"
---
# <a name="version-c"></a>version(C++)
클래스의 여러 버전 중에서 특정 버전을 식별합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
[ version(  
   "version"  
) ]  
```  
  
### <a name="parameters"></a>매개 변수  
 *version*  
 버전 번호는 `coclass`합니다. 지정 하지 않으면 1.0.idl 파일에 배치 됩니다.  
  
## <a name="remarks"></a>설명  
 합니다 **버전** c + + 특성에 동일한 기능을 합니다 [버전](http://msdn.microsoft.com/library/windows/desktop/aa367306) MIDL 특성 생성된 된.idl 파일에 전달 됩니다.  
  
## <a name="example"></a>예  
 참조를 [bindable](../windows/bindable.md) 의 샘플 사용에 대 한 예제 **버전**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, **구조체**|  
|**반복 가능**|아니요|  
|**필수 특성**|**coclass**|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 특성](../windows/compiler-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   