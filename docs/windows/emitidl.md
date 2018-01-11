---
title: emitidl | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.emitidl
dev_langs: C++
helpviewer_keywords: emitidl attribute
ms.assetid: 85b80c56-578e-4392-ac03-8443c74ebb7d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 55fc74eef3d2ead7312f7dca46f20c3a1ed7ba91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="emitidl"></a>emitidl
모든 후속 IDL 특성 처리 되 고 생성된 된.idl 파일에 배치 하는지 여부를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```
[ emitidl(state, defaultimports=boolean) ];
```  
  
### <a name="parameters"></a>매개 변수  
*state*  
다음 값 중 하나: **true**, **false**, **강제**, **제한**, **푸시**, 또는 **pop**합니다.  
  
-   경우 **true**, 소스 코드 파일에서 발생 한 모든 IDL 범주 특성 생성된 된.idl 파일에 배치 됩니다. 이 값에 대 한 기본 설정 **emitidl**합니다.  
  
-   경우 **false**, 소스 코드 파일에서 발생 한 모든 IDL 범주 특성 생성된 된.idl 파일에 저장 되지 않습니다.  
  
-   경우 **제한 된**, IDL 특성 없이 파일에 포함 되도록 허용 된 [모듈](../windows/module-cpp.md) 특성입니다. 컴파일러는.idl 파일을 생성 하지 않습니다.  
  
-   경우 **강제**, 후속 재정의 **제한** 특성을 파일에는 **모듈** 파일 특성이 있는 경우 IDL 특성입니다.  
  
-   **푸시** 현재 저장할 수 있습니다. **emitidl** 내부 설정을 **emitidl** 스택 및 **pop** 설정할 수 있습니다 **emitidl**내부 맨 위에 있는 모든 값은에 **emitidl** 스택 합니다.  
  
`defaultimports=`*부울* \(선택 사항)  
-   경우 *부울* 은 **true**, docobj.idl 생성된 된.idl 파일을 가져오면 됩니다. 또한.idl 파일에는.h 이름이 파일 경우 `#include` 생성된 된.idl 파일 해당.idl 파일에 대 한 import 문을 포함 한 다음 소스에 코드.h 파일과 동일한 디렉터리에 있습니다.  
  
-   경우 *부울* 은 **false**, docobj.idl는 생성된 된.idl 파일 가져올 수 없습니다. .Idl 파일을 명시적으로 가져와야 [가져올](../windows/import.md)합니다.  
  
## <a name="remarks"></a>설명  
이후에 **emitidl** 소스 코드 파일에서 c + + 특성이 있으면, IDL 범주 특성 생성된 된.idl 파일에 배치 됩니다. 없는 경우 없는 **emitidl** 특성, IDL 특성 소스 코드 파일에서 생성된 된.idl 파일에 출력 됩니다.  
  
여러 개 있을 수는 **emitidl** 소스 코드 파일의 특성입니다. 경우 `[emitidl(false)];` 후속 없이 파일에서 발생 `[emitidl(true)];`, 특성이 없습니다. 생성 된.idl 파일에 처리 됩니다.  
  
컴파일러는 새 파일을 발견 될 때마다 **emitidl** 로 암시적으로 설정 된 **true**합니다.  
  
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
[특성 샘플](http://msdn.microsoft.com/en-us/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)