---
title: "환경 변수 매크로 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, environment variable macros
- environment variables, macros in NMAKE
- macros, environment-variable
ms.assetid: f8e96635-0906-47b0-9f56-12a6fdf5e347
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69fae15b7a12d990d2fb2c8e457bfdc0407f7702
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="environment-variable-macros"></a>환경 변수 매크로
NMAKE는 매크로 정의 대 한 세션을 시작 하기 전에 존재 하는 환경 변수를 상속 합니다. 변수를 설정한 경우 운영 체제 환경에서 NMAKE 매크로로 제공 됩니다. 상속 된 이름은 대문자로 변환 됩니다. 상속 전처리 하기 전에 발생합니다. 메이크파일의에 같은 이름의 모든 매크로 재정의 하려면 환경 변수에서 상속 하는 매크로를 /E 옵션을 사용 합니다.  
  
 환경 변수 매크로 세션에서 다시 정의할 수 있습니다 및 이렇게 하면 해당 환경 변수를 변경 합니다. SET 명령 사용 하 여 환경 변수를 변경할 수 있습니다. 그러나 세션에서 환경 변수를 변경 하려면 SET 명령을 사용 하 여 변경 되지 않습니다 해당 매크로.  
  
 예:  
  
```  
PATH=$(PATH);\nonesuch  
  
all:  
    echo %PATH%  
```  
  
 이 예제에서는 변경 `PATH` 해당 환경 변수를 변경 `PATH`; 추가 `\nonesuch` 를 사용자의 경로입니다.  
  
 환경 변수는 메이크파일의 구문상 올바른 것을 문자열로 정의 된 경우 매크로가 만들어지지 않고 고 경고가 생성 됩니다. 변수 값에 달러 기호 ($)이 있으면 NMAKE 매크로 호출의 시작으로 해석 합니다. 매크로 사용 하 여 예기치 않은 동작이 발생할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [특수 NMake 매크로](../build/special-nmake-macros.md)