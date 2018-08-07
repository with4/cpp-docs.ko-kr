---
title: satype | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.satype
dev_langs:
- C++
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a5376e0e830654c15dc31522b07ed53af4492bf
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603396"
---
# <a name="satype"></a>satype
데이터 형식을 지정 합니다 `SAFEARRAY` 구조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ satype(  
   data_type  
) ]  
```  
  
### <a name="parameters"></a>매개 변수  
 *data_type*  
 데이터에 대 한 입력을 `SAFEARRAY` 인터페이스 메서드에 대 한 매개 변수로 전달 되는 데이터 구조입니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|인터페이스 매개 변수를 인터페이스 메서드|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
## <a name="remarks"></a>설명  
 합니다 **satype** c + + 특성의 데이터 형식 지정을 `SAFEARRAY`입니다.  
  
> [!NOTE]
>  간접 참조 수준을에서 삭제 되는 `SAFEARRAY` 생성된 된.idl 파일에서.cpp 파일에서 선언 하는 방법에 대 한 포인터입니다.  
  
## <a name="example"></a>예  
  
```cpp  
// cpp_attr_ref_satype.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="MyModule")];  
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]  
__interface A {  
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 특성](../windows/compiler-attributes.md)   
 [매개 변수 특성](../windows/parameter-attributes.md)   
 [메서드 특성](../windows/method-attributes.md)   
 [ID](../windows/id.md)   