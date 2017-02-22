---
title: "링커 도구 오류 LNK1312 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1312"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1312"
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 링커 도구 오류 LNK1312
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

잘못되었거나 손상된 파일: 어셈블리를 가져올 수 없습니다.  
  
 어셈블리를 빌드할 때 **\/clr**를 사용하여 컴파일한 모듈이나 어셈블리가 아닌 다른 파일을 **\/ASSEMBLYMODULE** 링커 옵션에 전달했습니다.  개체 파일을 **\/ASSEMBLYMODULE**에 전달한 경우 **\/ASSEMBLYMODULE**이 아닌 링커에 직접 개체를 전달해야 합니다.  
  
## 예제  
 다음 샘플에서는 .obj 파일을 만듭니다.  
  
```  
// LNK1312.cpp  
// compile with: /clr /LD  
public ref class A {  
public:  
   int i;  
};  
```  
  
## 예제  
 다음 샘플에서는 LNK1312가 발생합니다.  
  
```  
// LNK1312_b.cpp  
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj  
// LNK1312 error expected  
public ref class M {};  
```