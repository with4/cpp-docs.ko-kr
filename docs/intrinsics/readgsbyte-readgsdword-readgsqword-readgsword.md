---
title: "__readgsbyte, __readgsdword, __readgsqword, __readgsword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readgsbyte"
  - "__readgsdword"
  - "__readgsqword"
  - "__readgsword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readgsword 내장 함수"
  - "__readgsdword 내장 함수"
  - "__readgsqword 내장 함수"
  - "__readgsbyte 내장 함수"
ms.assetid: f822632d-854c-4558-a71b-cdfc3eea2236
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# __readgsbyte, __readgsdword, __readgsqword, __readgsword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 GS 세그먼트의 시작에 상대적인 오프셋에 의해 지정 된 위치에서 메모리를 읽습니다.  
  
## 구문  
  
```  
unsigned char __readgsbyte(   
   unsigned long Offset   
);  
unsigned short __readgsword(   
   unsigned long Offset   
);  
unsigned long __readgsdword(   
   unsigned long Offset  
);  
unsigned __int64 __readgsqword(   
   unsigned long Offset   
);  
```  
  
#### 매개 변수  
 \[in\] `Offset`  
 시작 부분에서 오프셋 `GS` 에서 읽을 수 있습니다.  
  
## 반환 값  
 메모리 내용을 바이트, 단어, 이중 단어 또는 quadword \(호출 되는 함수 이름으로 표시 됨\)의 위치에 `GS:[``Offset``]`.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__readgsbyte`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__readgsdword`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__readgsqword`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__readgsword`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이러한 내장 커널 모드로 가능 하 고 루틴만 내장으로 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [\_\_writegsbyte, \_\_writegsdword, \_\_writegsqword, \_\_writegsword](../intrinsics/writegsbyte-writegsdword-writegsqword-writegsword.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)