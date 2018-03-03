---
title: importlib | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.importlib
dev_langs:
- C++
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7c62db5b1e10f115a57da1ea00cd87760b96a71f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="importlib"></a>importlib
다른 형식 라이브러리에 이미 컴파일된 형식을 만들고 있는 형식 라이브러리에서 사용할 수 있도록 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ importlib(  
   "tlb_file"  
) ];  
```  
  
#### <a name="parameters"></a>매개 변수  
 *tlb_file*  
 현재 프로젝트의 형식 라이브러리로 가져오려는 .tlb 파일의 이름으로, 따옴표로 묶습니다.  
  
## <a name="remarks"></a>설명  
 **importlib** c + + 특성을 사용 하면는 `importlib` 문이 생성된 된.idl 파일의 라이브러리 블록에 배치 됩니다. **importlib** 특성와 동일한 기능에는 [importlib](http://msdn.microsoft.com/library/windows/desktop/aa367050) MIDL 특성입니다.  
  
## <a name="example"></a>예  
 다음 코드를 사용 하는 방법의 예를 보여 줍니다. **importlib**:  
  
```  
// cpp_attr_ref_importlib.cpp  
// compile with: /LD  
[module(name="MyLib")];  
[importlib("importlib.tlb")];  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|원하는 위치|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 특성](../windows/compiler-attributes.md)   
 [독립 실행형 특성](../windows/stand-alone-attributes.md)   
 [가져오기](../windows/import.md)   
 [importidl](../windows/importidl.md)   
 [포함](../windows/include-cpp.md)   
 [includelib](../windows/includelib-cpp.md)