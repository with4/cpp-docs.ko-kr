---
title: "__writeeflags | Microsoft Docs"
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
  - "__writeeflags"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__writeeflags 내장 함수"
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __writeeflags
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

프로그램에 지정 된 값을 기록 상태 \(EFLAGS\) 컨트롤을 등록 합니다.  
  
## 구문  
  
```  
void __writeeflags(unsigned Value);  
void __writeeflags(unsigned __int64 Value);  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|\[in\] `Value`|EFLAGS 레지스터에 쓸 값입니다.  `Value` 매개 변수는 32 비트 플랫폼에 대 한 장기 및 64 비트 32 비트 long 64 비트 플랫폼에 대 한.|  
  
## 설명  
 이러한 루틴은 내장으로만 사용할 수 있습니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__writeeflags`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [\_\_readeflags](../intrinsics/readeflags.md)