---
title: vtordisp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.vtordisp
- vtordisp_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, vtordisp
- vtordisp pragma
ms.assetid: 05b7d73c-43fa-4b62-8c8a-170a9e427391
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 502425728fcd97d2ae8d2efe406dc73370de1272
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33841774"
---
# <a name="vtordisp"></a>vtordisp
**C + + 전용**  
  
 숨겨진 vtordisp 생성/소멸 치환 멤버의 추가를 제어합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
#pragma vtordisp([push,] n)  
#pragma vtordisp(pop)  
#pragma vtordisp()  
#pragma vtordisp([push,] {on | off})  
```  
  
#### <a name="parameters"></a>매개 변수  
 `push`  
 내부 컴파일러 스택에서 현재 vtordisp 설정을 푸시하고 새 vtordisp 설정을 `n`으로 지정합니다.  `n`을 지정하지 않으면 현재 vtordisp 설정이 변경되지 않습니다.  
  
 `pop`  
 내부 컴파일러 스택에서 상위 레코드를 제거하고 vtordisp 설정을 제거된 값으로 복원합니다.  
  
 `n`  
 Vtordisp 설정에 대해 새 값을 지정합니다. 지정 가능한 값은 각각 /vd0, /vd1, /vd2 컴파일러 옵션에 해당하는 0, 1, 2입니다. 자세한 내용은 참조 [/vd (생성 치환 비활성화)](../build/reference/vd-disable-construction-displacements.md)합니다.  
  
 `on`  
 `#pragma vtordisp(1)`와 같습니다.  
  
 `off`  
 `#pragma vtordisp(0)`와 같습니다.  
  
## <a name="remarks"></a>설명  
 `vtordisp` pragma는 가상 기본을 사용하는 코드에만 적용됩니다. 파생 클래스가 가상 기본 클래스에서 상속된 가상 함수를 재정의하고 파생 클래스의 생성자 또는 소멸자가 가상 기본 클래스에 대한 포인터를 사용하여 해당 함수를 호출하는 경우, 컴파일러는 추가로 숨겨진 `vtordisp` 필드를 가상 기본 클래스에 사용할 수 있습니다.  
  
 `vtordisp` pragma는 뒤에 오는 클래스의 레이아웃에 영향을 줍니다. /vd0, /vd1 및 /vd2 옵션은 완료된 모듈에 대해 동일한 동작을 지정합니다. `0` 또는 `off`를 지정하면 숨겨진 `vtordisp` 멤버가 표시되지 않습니다. `vtordisp` 포인터가 가리키는 개체에 대해 클래스 생성자 및 소멸자가 가상 함수를 호출할 가능성이 없는 경우에만 `this`를 해제하십시오.  
  
 `1` 또는 `on`(기본값)을 지정하면 숨겨진 `vtordisp` 멤버가 필요한 위치에서 활성화됩니다.  
  
 지정 `2` 숨겨진 수 있도록 `vtordisp` 가상 함수에 모든 가상 기본에 대 한 멤버입니다.  `vtordisp(2)` 올바른 성능을 보장 하기 위해 필요할 수 있습니다 `dynamic_cast` 부분적으로 생성 된 개체에 있습니다. 자세한 내용은 참조 [컴파일러 경고 (수준 1) C4436](../error-messages/compiler-warnings/compiler-warning-level-1-c4436.md)합니다.  
  
 인수를 포함하지 않고 `#pragma vtordisp()`를 사용하는 경우 vtordisp 설정이 초기 설정으로 복원됩니다.  
  
```  
#pragma vtordisp(push, 2)  
class GetReal : virtual public VBase { ... };  
#pragma vtordisp(pop)  
```  
  
 **C + + 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)