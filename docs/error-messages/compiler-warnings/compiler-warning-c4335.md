---
title: "컴파일러 경고 C4335 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4335"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4335"
ms.assetid: e66467ad-a10b-4438-8c7c-e8e8d11d39bb
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 컴파일러 경고 C4335
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mac 파일 형식이 발견되었습니다. 소스 파일을 DOS나 UNIX 형식으로 변환하십시오.  
  
 소스 파일에서 첫 번째 줄의 종결 문자가 UNIX 스타일\(‘\\n’\) 또는 DOS 스타일\(‘\\r\\n’\)이 아닌 Macintosh 스타일\(‘\\r’\)입니다.  
  
 이 경고는 항상 오류로서 발생합니다.  이 경고를 비활성화하는 방법에 대한 자세한 내용은 [경고](../../preprocessor/warning.md) pragma를 참조하십시오.  또한 이 경고는 컴파일 대상에 대해 한 번씩만 발생합니다.  따라서 Mac 형식으로 파일을 지정하는 `#include` 지시문이 여러 개 있더라도 C4335는 한 번만 발생합니다.  
  
 Macintosh 형식으로 파일을 생성하는 방법 중 하나로 Visual Studio에서 **파일** 메뉴의 **저장 고급 옵션**을 사용할 수도 있습니다.  
  
## 예제  
 다음 샘플에서는 C4335 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4335 expected  
#include "c4335.h"   // assume both include files are in Macintosh format  
#include "c4335_2.h"  
```