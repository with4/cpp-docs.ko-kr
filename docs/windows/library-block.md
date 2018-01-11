---
title: library_block | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.library_block
dev_langs: C++
helpviewer_keywords: library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ab7c4c8c65d23dc252fb3ce228313fb36aa7e032
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="libraryblock"></a>library_block
IDL library 블록 내부는 구문을 배치합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
[library_block]  
  
```  
  
## <a name="remarks"></a>설명  
 라이브러리 블록 안에 예외가 구문을 배치 하면 형식 라이브러리 참조 하는지 여부에 관계 없이 전달할 수는 확인할 수 있습니다. 기본적으로 유일한 구문에 의해 수정 된 [coclass](../windows/coclass.md), [dispinterface](../windows/dispinterface.md), 및 [idl_module](../windows/idl-module.md) 특성 라이브러리 블록에 배치 됩니다.  
  
## <a name="example"></a>예  
 다음 코드에서 사용자 지정 인터페이스 라이브러리 블록 안에 배치 됩니다.  
  
```  
// cpp_attr_ref_library_block.cpp  
// compile with: /LD  
#include <windows.h>  
[module(name="MyLib")];  
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]  
__interface IMyInterface {  
   HRESULT f1();  
};  
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
