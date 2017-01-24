---
title: "컴파일러 경고 (수준 1) C4364 | Microsoft Docs"
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
  - "C4364"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4364"
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 경고 (수준 1) C4364
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'file' 어셈블리에 대한 \#using이 이전에 location\(line\_number\)에서 as\_friend 특성 없이 사용되었습니다. as\_friend가 적용되지 않습니다.  
  
 지정된 메타데이터 파일에 대해 `#using` 지시문을 반복했지만 처음 실행 시 `as_friend` 한정자를 사용하지 않았습니다. 두 번째 `as_friend`가 컴파일러에서 무시됩니다.  
  
 자세한 내용은 [Friend 어셈블리\(C\+\+\)](../../dotnet/friend-assemblies-cpp.md)을 참조하십시오.  
  
## 예제  
 다음 샘플에서는 구성 요소를 만듭니다.  
  
```  
// C4364.cpp  
// compile with: /clr /LD  
ref class A {};  
```  
  
## 예제  
 다음 샘플에서는 C4364 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4364_b.cpp  
// compile with: /clr /W1 /c  
#using " C4364.dll"  
#using " C4364.dll" as_friend   // C4364  
```