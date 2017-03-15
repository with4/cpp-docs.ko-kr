---
title: "__writemsr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__writemsr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "모델 특정 레지스터 쓰기 명령"
  - "wrmsr 명령"
  - "__writemsr 내장 함수"
ms.assetid: 938b1553-51a8-4822-a818-6bed79b0fde5
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __writemsr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 모델 특정 레지스터에 쓰기를 생성 \(`wrmsr`\) 명령.  
  
## 구문  
  
```  
void __writemsr(   
   unsigned long Register,   
   unsigned __int64 Value   
);  
```  
  
#### 매개 변수  
 \[in\] `Register`  
 모델 특정 레지스터입니다.  
  
 \[in\] `Value`  
 쓸 값입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__writemsr`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이 함수는 커널 모드로 사용할 수 있습니다 및이 루틴에만 내장로 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)