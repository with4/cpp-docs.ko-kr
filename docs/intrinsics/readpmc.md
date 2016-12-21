---
title: "__readpmc | Microsoft Docs"
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
  - "__readpmc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "읽기 성능 모니터링 카운터 명령"
  - "__readpmc 내장 함수"
  - "rdpmc 명령"
ms.assetid: 14ed45a6-28b6-4635-8437-a597c04b43d4
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __readpmc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성 하는 `rdpmc` 읽기 성능 모니터링 카운터를 지정 하는 명령, `counter`.  
  
## 구문  
  
```  
unsigned __int64 __readpmc(   
   unsigned long counter   
);  
```  
  
#### 매개 변수  
 \[in\] `counter`  
 성능 카운터를 읽으려면입니다.  
  
## 반환 값  
 지정 된 성능 카운터 값입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__readpmc`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 내장이 커널 모드로 가능 하며 루틴만 내장로 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)