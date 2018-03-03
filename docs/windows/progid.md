---
title: progid | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.progid
dev_langs:
- C++
helpviewer_keywords:
- progid attribute
ms.assetid: afcf559c-e432-481f-aa9a-bd3bb72c02a8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 862629af7e279cf1f03a5e9adc9424b330ee1d90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="progid"></a>progid
COM 개체에 대 한 ProgID를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ progid(  
   name  
) ];  
```  
  
#### <a name="parameters"></a>매개 변수  
 *name*  
 개체를 나타내는 ProgID입니다.  
  
 Progid의 CLSID (클래스 식별자) COM/ActiveX 개체를 식별 하는 데의 이해 하기 쉬운 버전을 제공 합니다.  
  
## <a name="remarks"></a>설명  
 **progid** c + + 특성을 사용 하면 COM 개체에 대 한 ProgID를 지정할 수 있습니다. ProgID에 형식은 *name1.name2.version*합니다. 지정 하지 않는 경우는 *버전* ProgID에 대 한 기본 버전은 1입니다. 지정 하지 않으면 *name1.name2*, 기본 이름은 *classname.classname*합니다. 지정 하지 않으면 **progid** 지정 않으면 **vi_progid**, *name1.name2* 에서 가져온 **vi_progid** 및 (다음 순차적 버전 번호)이 추가 됩니다.  
  
 특성 블록을 사용 하는 경우 **progid** 도 사용 하지 않는 `uuid`, 컴파일러는 있는지 레지스트리를 확인 하는 한 `uuid` 지정 된 항목에 대 한 **progid**합니다. 경우 **progid** 를 지정 하지 않으면 버전 (및 coclass를 만드는 경우 coclass 이름)를 생성 하기 위해 사용할 됩니다는 **progid**합니다.  
  
 **progid** 의미는 **coclass** 지정 하는 경우, 즉 특성 **progid**, 지정과 같은 작업을 이기는 **coclass** 및  **progid** 특성입니다.  
  
 **progid** 특성을 사용 하면 클래스를 지정 된 이름에 자동으로 등록 해야 합니다. 생성된 된.idl 파일 표시 되지 것입니다는 **progid** 값입니다.  
  
 ATL을 사용 하는 프로젝트 내에서이 특성을 사용 하는 경우 특성의 동작이 변경 됩니다. 위의 동작 외에도이 특성으로 지정 된 정보에 사용 되는 **GetProgID** 함수에 의해 삽입 된 **coclass** 특성입니다. 자세한 내용은 참조는 [coclass](../windows/coclass.md) 특성입니다.  
  
## <a name="example"></a>예  
 예를 참조 [coclass](../windows/coclass.md) 의 샘플 사용에 대 한 **progid**합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**class**, `struct`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
 [ProgID 키](http://msdn.microsoft.com/library/windows/desktop/dd542719)   
