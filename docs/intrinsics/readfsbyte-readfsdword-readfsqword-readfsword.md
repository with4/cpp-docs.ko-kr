---
title: "__readfsbyte, __readfsdword, __readfsqword, __readfsword | Microsoft Docs"
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
  - "__readfsword"
  - "__readfsdword"
  - "__readfsbyte"
  - "__readfsqword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readfsword 내장 함수"
  - "readfsword 내장 함수"
  - "__readfsdword 내장 함수"
  - "readfsbyte 내장 함수"
  - "__readfsbyte 내장 함수"
  - "readfsdword 내장 함수"
  - "readfsqword 내장 함수"
  - "__readfsqword 내장 함수"
ms.assetid: f6ee7203-4179-402c-a464-0746c84ce6ac
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __readfsbyte, __readfsdword, __readfsqword, __readfsword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 FS 세그먼트의 시작에 상대적인 오프셋에 의해 지정 된 위치에서 메모리를 읽습니다.  
  
## 구문  
  
```  
unsigned char __readfsbyte(   
   unsigned long Offset   
);  
unsigned short __readfsword(   
   unsigned long Offset   
);  
unsigned long __readfsdword(   
   unsigned long Offset  
);  
unsigned __int64 __readfsqword(   
   unsigned long Offset   
);  
```  
  
#### 매개 변수  
 \[in\] `Offset`  
 시작 부분에서 오프셋 `FS` 에서 읽을 수 있습니다.  
  
## 반환 값  
 메모리 내용을 바이트, 단어, 더블 워드, 또는 quadword \(호출 되는 함수 이름으로 표시 됨\)의 위치에 `FS:[``Offset``]`.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__readfsbyte`|x86|  
|`__readfsdword`|x86|  
|`__readfsqword`|x86|  
|`__readfsword`|x86|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이러한 루틴은 내장으로만 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [\_\_writefsbyte, \_\_writefsdword, \_\_writefsqword, \_\_writefsword](../intrinsics/writefsbyte-writefsdword-writefsqword-writefsword.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)