---
title: "__inbyte | Microsoft Docs"
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
  - "__inbyte"
  - "__inbyte_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "in 명령"
  - "__inbyte 내장 함수"
ms.assetid: 03b61799-2a08-474d-adc4-2cbf7c81a4d5
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __inbyte
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성 하는 `in` 1 바이트를 반환 명령을 읽고 지정 된 포트에서 `Port`.  
  
## 구문  
  
```  
unsigned char __inbyte(  
   unsigned short Port  
);  
```  
  
#### 매개 변수  
 \[in\] `Port`  
 읽기 포트입니다.  
  
## 반환 값  
 지정 된 포트에서 바이트를 읽습니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__inbyte`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## Microsoft 특정 끝  
  
## 설명  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)