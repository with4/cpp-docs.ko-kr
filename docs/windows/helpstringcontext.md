---
title: helpstringcontext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.helpstringcontext
dev_langs: C++
helpviewer_keywords: helpstringcontext attribute [C++]
ms.assetid: d4cd135e-d91c-4aa3-9353-8aeb096f52cf
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3c5492d18085d78e20d6654898a6c66647e3bbe0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="helpstringcontext"></a>helpstringcontext
.Hlp 또는.chm 파일 도움말 항목의 ID를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ helpstringcontext(  
   contextID  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `contextID`  
 도움말 파일에는 32 비트 도움말 컨텍스트 식별자입니다.  
  
## <a name="remarks"></a>설명  
 **helpstringcontext** c + + 특성에 동일한 기능을는 [helpstringcontext](http://msdn.microsoft.com/library/windows/desktop/aa366858) ODL 특성입니다.  
  
## <a name="example"></a>예  
  
```  
// cpp_attr_ref_helpstringcontext.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLib")];  
  
[   object,   
   helpstring("help string"),   
   helpstringcontext(1),   
   uuid="11111111-1111-1111-1111-111111111111"  
]  
__interface IMyI   
{  
   HRESULT xx();  
};  
```  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, `interface`, 인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [인터페이스 특성](../windows/interface-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [메서드 특성](../windows/method-attributes.md)   
 [모듈](../windows/module-cpp.md)   
