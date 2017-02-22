---
title: "컴파일러 오류 C3115 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3115"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3115"
ms.assetid: 51726145-9782-4ec9-84b9-286f366d9cbd
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 오류 C3115
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute': 이 특성은 'construct'에 사용할 수 없습니다.  
  
 구문에 적용한 특성이 해당 구문에 사용할 수 없는 특성입니다.  자세한 내용은 [Attributes by Usage](../../windows/attributes-by-usage.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C3115 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3115.cpp  
// compile with: /c  
#include <unknwn.h>  
[module(name="xx")];  
  
[object, helpstringdll(xx.dll), uuid("00000000-0000-0000-0000-000000000001")]   // C3115  
// try the following line instead  
// [object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IMyI {  
   HRESULT xx();  
};  
```