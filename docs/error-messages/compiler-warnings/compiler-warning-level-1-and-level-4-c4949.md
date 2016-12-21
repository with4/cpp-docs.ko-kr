---
title: "컴파일러 경고(수준 1 및 수준 4) C4949 | Microsoft Docs"
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
  - "C4949"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4949"
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고(수준 1 및 수준 4) C4949
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

pragma 'managed' 및 'unmanaged'는 '\/clr\[:option\]'을 지정하여 컴파일한 경우에만 의미가 있습니다.  
  
 소스 코드를 컴파일하는 데 [\/clr](../../build/reference/clr-common-language-runtime-compilation.md)를 사용하지 않은 경우 컴파일러는 [managed](../../preprocessor/managed-unmanaged.md) 및 unmanaged pragma를 무시합니다.  이 경고는 정보를 제공하기 위한 것입니다.  
  
 다음 샘플에서는 C4949 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4949.cpp  
// compile with: /LD /W1  
#pragma managed   // C4949  
```  
  
 **\/clr** 없이 **\#pragma unmanaged**를 사용하는 경우 C4949 경고는 수준 4입니다.  
  
 다음 샘플에서는 C4949 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4949b.cpp  
// compile with: /LD /W4  
#pragma unmanaged   // C4949  
```