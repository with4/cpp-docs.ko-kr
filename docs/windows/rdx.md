---
title: rdx | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.rdx
dev_langs:
- C++
helpviewer_keywords:
- rdx attribute
ms.assetid: ff8e4312-c1ad-4934-bdaa-86f54409651e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7647ca56e3159564826efa9caf438456b9ae3568
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878959"
---
# <a name="rdx"></a>rdx
레지스트리 키를 만들거나 기존 레지스트리 키를 수정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ rdx(   
   key,   
   valuename=NULL,   
   regtype   
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 `key`  
 만들거나 열 키의 이름입니다.  
  
 `valuename`(선택 사항)  
 설정할 값 필드를 지정 합니다. 이 이름 가진 값 필드는 아직 없으면 키에 추가 됩니다.  
  
 *regtype*  
 추가 되는 레지스트리 키의 형식입니다. 다음 중 하나일 수 있습니다: **텍스트**, **dword**, **이진**, 또는 `CString`합니다.  
  
## <a name="remarks"></a>설명  
 **rdx** c + + 특성을 만들거나 기존 COM 구성 요소에 대 한 레지스트리 키를 수정 합니다. 특성 대상 멤버를 구현 하는 개체에 BEGIN_RDX_MAP 매크로 추가 합니다. `RegistryDataExchange`레지스트리 및 데이터 멤버 간에 데이터를 전송 BEGIN_RDX_MAP 매크로 결과로 삽입 하는 함수를 사용할 수 있습니다  
  
 이 특성은 함께에서 사용할 수 있습니다는 [coclass](../windows/coclass.md), [progid](../windows/progid.md), 또는 [vi_progid](../windows/vi-progid.md) 특성 또는 다음 중 하나를 의미 하는 기타 특성입니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**클래스** 또는 `struct` 멤버|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 다음 코드는 MyValue CMyClass COM 구성 요소를 설명 하는 시스템에 라는 레지스트리 키를 추가 합니다.  
  
```  
// cpp_attr_ref_rdx.cpp  
// compile with: /LD /link /OPT:NOREF  
#define _ATL_ATTRIBUTES  
#include "atlbase.h"  
  
[module (name="MyLib")];  
  
class CMyClass {  
public:  
   CMyClass() {  
      strcpy_s(m_sz, "SomeValue");  
   }  
  
   [ rdx(key = "HKCR\\MyApp.MyApp.1", valuename = "MyValue", regtype = "text")]   
   char m_sz[256];  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [COM 특성](../windows/com-attributes.md)   
 [registration_script](../windows/registration-script.md)   
