---
title: "-가드 (보호 검사 사용) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 72758e23-70ac-4616-94d7-d767477406d1
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dbc987f7db1e3a1bce0b73f0c21e875b7c9e5eda
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="guard-enable-guard-checks"></a>/GUARD(보호 검사 사용)
실행 가능 이미지에서 제어 흐름 보호 검사에 대한 지원을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
/GUARD:{CF|NO}  
```  
  
## <a name="remarks"></a>설명  
 /GUARD:CF를 지정하면 링커가 .dll 또는 .exe의 헤더를 수정하여 CFG(제어 흐름 보호) 런타임 검사에 대한 지원을 나타냅니다. 또한 링커에서 필요한 제어 흐름 대상 주소 데이터를 헤더에 추가합니다. /GUARD:CF는 기본적으로 사용되지 않습니다. /GUARD:NO를 사용하여 명시적으로 사용하지 않도록 설정할 수 있습니다. 를 적용 하려면 /guard: cf도 필요는 [/DYNAMICBASE (사용 하 여 주소 공간 레이아웃 불규칙화)](../../build/reference/dynamicbase-use-address-space-layout-randomization.md) 링커 옵션을 기본적으로 켜져 있습니다.  
  
 사용 하 여 소스 코드를 컴파일할 때는 [/guard: cf](../../build/reference/guard-enable-control-flow-guard.md) 옵션을 컴파일러는 가능한 대상 주소에 대 한 모든 간접 호출을 검사 하 여 제어 흐름을 분석 합니다. 컴파일러는 간접 호출 명령의 대상 주소가 런타임에 알려진 대상 주소 목록에 있는지 확인하는 코드를 삽입합니다. CFG를 지원하는 운영 체제는 CFG 런타임 검사에 실패하는 프로그램을 중지합니다. 이렇게 하면 공격자가 데이터 손상을 통해 호출 대상을 변경하여 악성 코드를 실행하는 것이 더 어려워집니다.  
  
 CFG 사용 실행 가능 이미지를 만들려면 컴파일러와 링커 둘 다에 /GUARD:CF 옵션을 지정해야 합니다. 코드가 컴파일되었지만 /GUARD:CF를 사용하여 연결되지 않은 경우 런타임 검사 비용이 발생하지만 CFG 보호는 사용되지 않습니다. /Guard: cf 옵션에 지정 된 경우는 `cl` 명령을 컴파일하고 한번 컴파일러에에서 연결 하는 플래그를 링커에 전달 합니다. 경우는 **제어 흐름 보호** Visual Studio에서 속성을 설정 하면 /guard: cf 옵션이 컴파일러와 링커 둘 다에 전달 됩니다. 에 옵션을 명시적으로 지정 해야 개체 파일 또는 라이브러리가 개별적으로 컴파일된 경우는 `link` 명령입니다.  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다. 자세한 내용은 참조 [프로젝트 속성 작업](../../ide/working-with-project-properties.md)합니다.  
  
2.  확장 **구성 속성**, **링커**, **명령줄**합니다.  
  
3.  **추가 옵션**, 입력 `/GUARD:CF`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [/guard (제어 흐름 보호 사용)](../../build/reference/guard-enable-control-flow-guard.md)   
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)