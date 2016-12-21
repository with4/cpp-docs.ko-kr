---
title: "컴파일러 오류 C2393 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2393"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2393"
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2393
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbol' : 'segment' 세그먼트에 appdomain별 기호를 할당할 수 없습니다.  
  
 [appdomain](../../cpp/appdomain.md) 변수를 사용하는 것은 **\/clr:pure** 또는 **\/clr:safe**를 사용하여 컴파일함을 의미하며, 안전 또는 순수 이미지에 데이터 세그먼트가 포함될 수 없습니다.  
  
 자세한 내용은 [\/clr\(공용 언어 런타임 컴파일\)](../../build/reference/clr-common-language-runtime-compilation.md)를 참조하십시오.  
  
## 예제  
 다음 샘플에서는 C2393 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2393.cpp  
// compile with: /clr:pure /c  
#pragma data_seg("myseg")  
int n = 0;   // C2393  
```