---
title: "__invlpg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__invlpg"
  - "__invlpg_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invlpg 명령"
  - "__invlpg 내장 함수"
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __invlpg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 X86 생성 `invlpg` 가 가리키는 메모리와 관련 된 페이지를 번역 tlb \(TLB\)을 무효화 하는 명령, `Address`.  
  
## 구문  
  
```  
void __invlpg(  
   void* Address  
);  
```  
  
#### 매개 변수  
 \[in\] `Address`  
 64 비트 주소입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__invlpg`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 내장의 `__invlpg` 에 대 한 권한 있는 명령 울리고만 0 권한 수준 \(CPL\) 커널 모드에서 사용할 수 있습니다.  
  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)