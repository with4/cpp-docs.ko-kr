---
title: "환경 변수 매크로 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "환경 변수, NMAKE의 매크로"
  - "매크로, 환경 변수"
  - "NMAKE 프로그램, 환경 변수 매크로"
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 환경 변수 매크로
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE는 세션 시작 전에 존재하는 환경 변수의 매크로 정의를 상속합니다.  운영 체제 환경에 변수가 설정된 경우 NMAKE 매크로를 사용할 수 있습니다.  상속된 이름은 대문자로 변환되고  전처리를 수행하기 전에 상속됩니다.  환경 변수로부터 매크로를 상속하여 메이크파일에 있는 같은 이름의 모든 매크로를 재정의하려면 \/E 옵션을 사용합니다.  
  
 환경 변수 매크로는 세션에서 다시 정의할 수 있으며 환경 변수 매크로가 다시 정의되면 해당 환경 변수가 변경됩니다.  SET 명령을 사용하여 환경 변수를 변경할 수도 있습니다.  그러나 SET 명령을 사용하여 세션의 환경 변수를 변경해도 해당 매크로는 변경되지 않습니다.  
  
 예를 들면 다음과 같습니다.  
  
```  
PATH=$(PATH);\nonesuch  
  
all:  
    echo %PATH%  
```  
  
 이 예제에서 `PATH`를 변경하면 해당 환경 변수 `PATH`가 변경되어 경로에 `\nonesuch`를 추가합니다.  
  
 환경 변수가 잘못된 구문이 있는 문자열로 메이크파일에 정의된 경우 매크로가 만들어지지 않고 경고도 생성되지 않습니다.  변수 값에 달러 기호\($\)가 포함된 경우 NMAKE는 이 기호를 매크로 호출의 시작으로 해석합니다.  매크로를 사용하면 예상치 못한 동작이 발생할 수 있습니다.  
  
## 참고 항목  
 [특수 NMake 매크로](../build/special-nmake-macros.md)