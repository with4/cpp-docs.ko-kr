---
title: "__writegsbyte, __writegsdword, __writegsqword, __writegsword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__writegsbyte"
  - "__writegsqword"
  - "__writegsdword"
  - "__writegsword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__writegsqword 내장 함수"
  - "__writegsbyte 내장 함수"
  - "__writegsword 내장 함수"
  - "__writegsdword 내장 함수"
ms.assetid: 7746cf6d-2259-4139-9aab-c07dd75c8037
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# __writegsbyte, __writegsdword, __writegsqword, __writegsword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 메모리는 GS 세그먼트의 시작에 상대적인 오프셋으로 지정한 위치에 기록 합니다.  
  
## 구문  
  
```  
void __writegsbyte(   
   unsigned long Offset,   
   unsigned char Data   
);  
void __writegsword(   
   unsigned long Offset,   
   unsigned short Data   
);  
void __writegsdword(   
   unsigned long Offset,   
   unsigned long Data   
);  
void __writegsqword(   
   unsigned long Offset,   
   unsigned __int64 Data   
);  
```  
  
#### 매개 변수  
 \[in\] `Offset`  
 쓸 수 GS 시작 부분부터의 오프셋입니다.  
  
 \[in\] `Data`  
 쓸 값입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__writegsbyte`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__writegsdword`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__writegsqword`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__writegsword`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이러한 내장 커널 모드 에서만 사용할 수 있으며 이러한 루틴에만 내장으로 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [\_\_readgsbyte, \_\_readgsdword, \_\_readgsqword, \_\_readgsword](../intrinsics/readgsbyte-readgsdword-readgsqword-readgsword.md)   
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)