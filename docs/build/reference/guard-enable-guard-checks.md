---
title: "/GUARD(보호 검사 사용) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 72758e23-70ac-4616-94d7-d767477406d1
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /GUARD(보호 검사 사용)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

실행 가능 이미지에서 제어 흐름 보호 검사에 대한 지원을 지정합니다.  
  
## 구문  
  
```  
/GUARD:{CF|NO}  
```  
  
## 설명  
 \/GUARD:CF를 지정하면 링커가 .dll 또는 .exe의 헤더를 수정하여 CFG\(제어 흐름 보호\) 런타임 검사에 대한 지원을 나타냅니다.  또한 링커에서 필요한 제어 흐름 대상 주소 데이터를 헤더에 추가합니다.  \/GUARD:CF는 기본적으로 사용되지 않습니다.  \/GUARD:NO를 사용하여 명시적으로 사용하지 않도록 설정할 수 있습니다.  \/GUARD:CF를 적용하려면 기본적으로 사용되는 [\/DYNAMICBASE\(주소 공간 레이아웃을 임의로 지정\)](../../build/reference/dynamicbase-use-address-space-layout-randomization.md) 링커 옵션도 필요합니다.  
  
 [\/guard:cf](../../build/reference/guard-enable-control-flow-guard.md) 옵션을 사용하여 소스 코드를 컴파일하는 경우 컴파일러에서 가능한 대상 주소에 대한 모든 간접 호출을 검사하여 제어 흐름을 분석합니다.  컴파일러는 간접 호출 명령의 대상 주소가 런타임에 알려진 대상 주소 목록에 있는지 확인하는 코드를 삽입합니다.  CFG를 지원하는 운영 체제는 CFG 런타임 검사에 실패하는 프로그램을 중지합니다.  이렇게 하면 공격자가 데이터 손상을 통해 호출 대상을 변경하여 악성 코드를 실행하는 것이 더 어려워집니다.  
  
 CFG 사용 실행 가능 이미지를 만들려면 컴파일러와 링커 둘 다에 \/GUARD:CF 옵션을 지정해야 합니다.  코드가 컴파일되었지만 \/GUARD:CF를 사용하여 연결되지 않은 경우 런타임 검사 비용이 발생하지만 CFG 보호는 사용되지 않습니다.  `cl` 명령에 \/GUARD:CF 옵션을 지정하여 한 단계로 컴파일 및 연결하는 경우 컴파일러가 플래그를 링커에 전달합니다.  Visual Studio에서 **제어 흐름 보호** 속성을 설정하면 \/GUARD:CF 옵션이 컴파일러와 링커 둘 다에 전달됩니다.  개체 파일 또는 라이브러리가 개별적으로 컴파일된 경우 `link` 명령에서 옵션을 명시적으로 지정해야 합니다.  
  
### Visual Studio에서 이 링커 옵션을 설정하려면  
  
1.  프로젝트 **속성 페이지** 대화 상자를 엽니다.  자세한 내용은 [방법: 프로젝트 속성 페이지 열기](../../misc/how-to-open-project-property-pages.md)를 참조하세요.  
  
2.  **구성 속성**, **링커**, **명령줄**을 차례로 확장합니다.  
  
3.  **추가 옵션**에서 `/GUARD:CF`를 입력합니다.  
  
## 참고 항목  
 [\/guard\(제어 흐름 보호 사용\)](../../build/reference/guard-enable-control-flow-guard.md)   
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)   
 [링커 옵션](../../build/reference/linker-options.md)