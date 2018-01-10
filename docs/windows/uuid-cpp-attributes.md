---
title: "uuid (c + + 특성) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.uuid
dev_langs: C++
helpviewer_keywords: uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ba35dc89ae2567a499d4623f0c74293d2dbdcca2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="uuid-c-attributes"></a>uuid(C++ 특성)
클래스 또는 인터페이스에 대 한 고유 ID를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      [ uuid(  
   "uuid"  
) ]  
```  
  
#### <a name="parameters"></a>매개 변수  
 *uuid*  
 128 비트, 고유 식별자입니다.  
  
## <a name="remarks"></a>설명  
 인터페이스 또는 클래스의 정의 지정 하지 않은 경우는 `uuid` 하나는 c + + 특성을 설정한 다음 Visual c + + 컴파일러 제공 합니다. 지정 하는 경우는 `uuid`, 인용 부호를 포함 해야 합니다.  
  
 지정 하지 않으면 `uuid`, 컴파일러는 컴퓨터에서 서로 다른 특성을 프로젝트의 인터페이스 또는 동일한 이름 가진 클래스에 대해 동일한 GUID를 생성 합니다.  
  
 사용자 고유의 고유 Id를 생성 하려면 Uuidgen.exe 또는 Guidgen.exe를 사용할 수 있습니다. (이러한 도구 중 하나를 실행 하려면 클릭 **시작** 클릭 **실행** 메뉴. 필요한 도구의 이름을 입력 합니다.)  
  
 또한 ATL을 사용 하지는 않는 프로젝트를 사용할 경우 지정 하는 `uuid` 특성을 지정 하는 것과 같습니다는 [uuid](../cpp/uuid-cpp.md) __declspec 한정자입니다. 검색 하는 `uuid` 사용할 수는 클래스의 [__uuidof](../cpp/uuidof-operator.md)  
  
## <a name="example"></a>예  
 참조는 [바인딩 가능한](../windows/bindable.md) 의 샘플 사용에 대 한 예제 `uuid`합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="attribute-context"></a>특성 컨텍스트  
  
|||  
|-|-|  
|**적용 대상**|**클래스**, `struct`, `interface`, **union**,`enum`|  
|**반복 가능**|아니요|  
|**필수 특성**|없음|  
|**잘못된 특성**|없음|  
  
 특성 컨텍스트에 대한 자세한 내용은 [특성 컨텍스트](../windows/attribute-contexts.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [IDL 특성](../windows/idl-attributes.md)   
 [인터페이스 특성](../windows/interface-attributes.md)   
 [클래스 특성](../windows/class-attributes.md)   
 [Typedef, Enum, Union 및 Struct 특성](../windows/typedef-enum-union-and-struct-attributes.md)   
 [uuid](http://msdn.microsoft.com/library/windows/desktop/aa367302)   
