---
title: "__incfsbyte, __incfsword, __incfsdword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__incfsword"
  - "__incfsbyte_cpp"
  - "__incfsbyte"
  - "__incfsdword"
  - "__incfsword_cpp"
  - "__incfsdword_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__incfsword 내장 함수"
  - "__incfsdword 내장 함수"
  - "__incfsbyte 내장 함수"
ms.assetid: 820457fb-e35e-42d3-bcb6-725da3281c64
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# __incfsbyte, __incfsword, __incfsdword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 오프셋 시작 부분을 기준으로 하 여 지정 된 메모리 위치에 값 추가 `FS` 세그먼트.  
  
## 구문  
  
```  
void __incfsbyte(   
   unsigned long Offset   
);  
void __incfsword(   
   unsigned long Offset   
);  
void __incfsdword(   
   unsigned long Offset  
);  
```  
  
#### 매개 변수  
 \[in\] `Offset`  
 시작 부분에서 오프셋 `FS`.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__incfsbyte`|x86|  
|`__incfsword`|x86|  
|`__incfsdword`|x86|  
  
## 설명  
 이러한 내장 커널 모드로 가능 하 고 루틴만 내장으로 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [\_\_addfsbyte, \_\_addfsword, \_\_addfsdword](../intrinsics/addfsbyte-addfsword-addfsdword.md)   
 [\_\_readfsbyte, \_\_readfsdword, \_\_readfsqword, \_\_readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)   
 [\_\_writefsbyte, \_\_writefsdword, \_\_writefsqword, \_\_writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)