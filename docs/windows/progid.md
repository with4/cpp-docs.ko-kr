---
title: progid | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.progid
dev_langs:
- C++
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: efbf2910fb025370e3373b91b418a4e2a2df5bc5
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40015783"
---
# <a name="progid"></a>progid
COM 개체의 ProgID를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
[ progid(  
   name  
) ];  
```  
  
### <a name="parameters"></a>매개 변수  
 *name*  
 개체를 나타내는 ProgID입니다.  
  
 Progid는 COM/ActiveX 개체를 식별 하는 데 클래스 식별자 (CLSID)의 알기 쉬운 버전을 제공 합니다.  
  
## <a name="remarks"></a>설명  
 합니다 **progid** c + + 특성을 사용 하면 COM 개체의 ProgID를 지정할 수 있습니다. 형식은 ProgID *name1.name2.version*합니다. 지정 하지 않으면 경우는 *버전* ProgID, 기본 버전은 1입니다. 지정 하지 않는 경우 *name1.name2*, 기본 이름인 *classname.classname*합니다. 지정 하지 않는 경우 **progid** 지정 하면 `vi_progid`, *name1.name2* 에서 가져온 `vi_progid` (다음 일련 번호) 및 버전 추가 됩니다.  
  
 특성 블록을 사용 하는 경우 **progid** 도 사용 하지 않습니다 **uuid**, 컴파일러는 경우를 확인 하려면 레지스트리를 확인 하는 **uuid** 지정 된 존재 **progid** . 하는 경우 **progid** 지정 하지 않으면 버전 (및 coclass 이름에는 coclass를 만드는 경우) 데 사용할 생성을 **progid**합니다.  
  
 **progid** 의미 합니다 `coclass` 지정 하는 경우, 특성 **progid**, 다릅니다 지정 하는 것을 `coclass` 및 **progid** 특성입니다.  
  
 합니다 **progid** 특성을 사용 하면 지정 된 이름으로 자동으로 등록 하는 클래스입니다. 생성된 된.idl 파일 표시 되지 것입니다 합니다 **progid** 값입니다.  
  
 ATL을 사용 하는 프로젝트 내에서이 특성을 사용 하면 특성의 동작을 변경 합니다. 위 동작 외에도이 특성을 사용 하 여 지정 된 정보는를 `GetProgID` 함수에 의해 삽입 된 `coclass` 특성입니다. 자세한 내용은 참조는 [coclass](../windows/coclass.md) 특성입니다.  
  
## <a name="example"></a>예  
 예를 참조 하세요 [coclass](../windows/coclass.md) 의 샘플 사용에 대 한 **progid**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, **구조체**|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
 [ProgID 키](http://msdn.microsoft.com/library/windows/desktop/dd542719)   