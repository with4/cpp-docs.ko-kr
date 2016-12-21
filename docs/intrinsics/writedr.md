---
title: "__writedr | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__writedr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__writedr 내장 함수"
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __writedr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정 된 디버그 레지스터에 지정 된 값을 씁니다.  
  
## 구문  
  
```  
void __writedr(unsigned DebugRegister, unsigned DebugValue);  
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue);  
```  
  
#### 매개 변수  
 \[in\] `DebugRegister`  
 디버그를 식별 하는 0부터 7 까지의 숫자를 등록 합니다.  
  
 \[in\] `DebugValue`  
 디버그에 쓸 값을 등록 합니다.  
  
## 설명  
 이러한 내장 커널 모드에서 사용할 수 있으며 루틴을 내장으로만 사용할 수 있습니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__writedr`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [\_\_readdr](../intrinsics/readdr.md)