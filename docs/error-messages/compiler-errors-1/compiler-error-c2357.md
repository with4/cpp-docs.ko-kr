---
title: "컴파일러 오류 C2357 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2357"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2357"
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2357
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 'type' 형식 함수여야 합니다.  
  
 코드에서 컴파일러에 의해 내부적으로 선언된 버전과 일치하지 않는 버전의 `atexit` 함수를 선언했습니다.  `atexit`를 다음과 같이 선언하십시오.  
  
```  
int __cdecl atexit(void (__cdecl *)());  
```  
  
 자세한 내용은 [init\_seg](../../preprocessor/init-seg.md)를 참조하십시오.  
  
 다음 샘플에서는 C2357 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2357.cpp  
// compile with: /c  
// C2357 expected  
#pragma warning(disable : 4075)  
// Uncomment the following line to resolve.  
// int __cdecl myexit(void (__cdecl *)());  
#pragma init_seg(".mine$m",myexit)  
```