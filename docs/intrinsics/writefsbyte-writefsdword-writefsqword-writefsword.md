---
title: "__writefsbyte, __writefsdword, __writefsqword, __writefsword | Microsoft Docs"
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
  - "__writefsword"
  - "__writefsbyte"
  - "__writefsqword"
  - "__writefsdword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "writefsbyte 내장 함수"
  - "__writefsword 내장 함수"
  - "writefsqword 내장 함수"
  - "writefsdword 내장 함수"
  - "__writefsdword 내장 함수"
  - "__writefsqword 내장 함수"
  - "__writefsbyte 내장 함수"
  - "writefsword 내장 함수"
ms.assetid: 23ac6e8e-bc91-4e90-a4c6-da02993637ad
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __writefsbyte, __writefsdword, __writefsqword, __writefsword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 메모리는 FS 세그먼트의 시작에 상대적인 오프셋으로 지정한 위치에 기록 합니다.  
  
## 구문  
  
```  
void __writefsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __writefsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __writefsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
void __writefsqword(   
   unsigned long Offset,   
   unsigned __int64 Data   
);  
```  
  
#### 매개 변수  
 \[in\] `Offset`  
 FS 쓸 시작 부분부터의 오프셋입니다.  
  
 \[in\] `Data`  
 쓸 값입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__writefsbyte`|x86|  
|`__writefsword`|x86|  
|`__writefsdword`|x86|  
|`__writefsqword`|x86|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이러한 루틴은 내장으로만 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [\_\_readfsbyte, \_\_readfsdword, \_\_readfsqword, \_\_readfsword](../intrinsics/readfsbyte-readfsdword-readfsqword-readfsword.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)