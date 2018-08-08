---
title: includelib (c + +) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.includelib
dev_langs:
- C++
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e10ab341dc4c90a26315ea5e30f03bc71e628b64
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603383"
---
# <a name="includelib-c"></a>includelib(C++)
생성된 된.idl 파일에 포함 될.idl 또는.h 파일을 사용 하면 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ includelib(  
   name.idl  
) ];  
```  
  
### <a name="parameters"></a>매개 변수  
 *name.idl*  
 생성된 된.idl 파일의 일부분으로 포함 하려는.idl 파일의 이름입니다.  
  
## <a name="remarks"></a>설명  
 합니다 **includelib** c + + 특성을 한 후 생성 된.idl 파일에 포함 될.idl 또는.h 파일을 사용 하면는 `importlib` 문입니다.  
  
## <a name="example"></a>예  
 다음 코드는.cpp 파일에 표시 됩니다.  
  
```cpp  
// cpp_attr_ref_includelib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[includelib("includelib.idl")];  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|원하는 위치|  
|**반복 가능**|예|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [독립 실행형 특성](../windows/stand-alone-attributes.md)   
 [가져오기](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [포함](../windows/include-cpp.md)   
 [importlib](../windows/importlib.md)   