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
ms.openlocfilehash: 252a5d953dd05edc494daf8c4a45322d5511f979
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="includelib-c"></a>includelib(C++)
.idl or.h 파일 생성된 된.idl 파일에 포함 하면 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ includelib(  
   name.idl  
) ];  
```  
  
#### <a name="parameters"></a>매개 변수  
 *name.idl*  
 원하는 생성된 된.idl 파일의 일부로 포함 하는.idl 파일의 이름입니다.  
  
## <a name="remarks"></a>설명  
 `includelib` c + + 특성으로 인해 이후 생성 된.idl 파일에 포함 되어야 하는.idl 또는.h 파일의 `importlib` 문.  
  
## <a name="example"></a>예제  
 다음 코드는.cpp 파일에 표시 됩니다.  
  
```  
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
