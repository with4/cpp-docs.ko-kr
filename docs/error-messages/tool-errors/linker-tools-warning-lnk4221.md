---
title: "링커 도구 경고 LNK4221 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4221"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4221"
ms.assetid: 8e2eb2de-9532-4b85-908a-8c9ff5c4cccb
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# 링커 도구 경고 LNK4221
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 개체 파일은 기존에 정의되지 않은 공용 기호를 정의하지 않으므로 이 라이브러리를 사용하는 링크 작업에 사용되지 않습니다.  
  
 다음 두 가지 코드 조각을 참조하십시오.  
  
```  
// a.cpp  
#include <atlbase.h>  
```  
  
```  
// b.cpp  
#include <atlbase.h>  
int function()  
{  
   return 0;  
}  
  
```  
  
 파일을 컴파일하고 두 개체 파일을 만들려면 명령 프롬프트에서 **cl \/c a.cpp b.cpp**를 실행합니다.  **link \/lib \/out:test.lib a.obj b.obj**를 실행하여 개체 파일을 링크하면 LNK4221 경고가 표시됩니다.  **link \/lib \/out:test.lib b.obj a.obj**를 실행하여 개체를 링크하면 경고가 표시되지 않습니다.  
  
 링커는 LIFO\(후입 선출\) 방식으로 작동하므로 두 번째 시나리오에서 경고가 발생하지 않습니다.  첫 번째 시나리오에서는 b.obj가 a.obj보다 먼저 처리되고 a.obj에 새 기호가 추가되지 않습니다.  링커가 a.obj를 먼저 처리하도록 지시하면 경고를 방지할 수 있습니다.  
  
 이 오류는 일반적으로 두 소스 파일에서 **미리 컴파일된 헤더** 필드에 같은 헤더 파일 이름을 사용하여 [\/Yc\(미리 컴파일된 헤더 파일 만들기\)](../../build/reference/yc-create-precompiled-header-file.md) 옵션을 지정하는 경우에 발생합니다.  이 문제의 일반적인 원인은 stdafx.h로 해결할 수 있습니다. 기본적으로 stdafx.cpp는 stdafx.h를 포함하므로 새 기호를 추가하지 않습니다.  다른 소스 파일에 **\/Yc**를 사용하는 stdafx.h가 포함되어 있고 관련된 .obj 파일이 stdafx.obj 전에 처리되는 경우 링커에서 LNK4221을 throw합니다.  
  
 이 문제를 해결하는 한 가지 방법은 미리 컴파일된 각 헤더에 대해 **\/Yc**를 사용하는 헤더가 포함된 소스 파일이 하나뿐인지 확인하는 것입니다.  다른 모든 소스 파일에서는 미리 컴파일된 헤더를 사용해야 합니다.  이 설정을 변경하는 방법에 대한 자세한 내용은 [\/Yu\(미리 컴파일된 헤더 파일 사용\)](../../build/reference/yu-use-precompiled-header-file.md)를 참조하십시오.