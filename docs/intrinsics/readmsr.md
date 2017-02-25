---
title: "__readmsr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readmsr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "모델 특정 레지스터 읽기"
  - "rdmsr 명령"
  - "__readmsr 내장 함수"
ms.assetid: 7ab1f8e8-72cb-4ce4-817d-3e728a3c9716
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __readmsr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성의 `rdmsr` 명령에서 지정한 모델 특정 레지스터를 읽고 `register` 및 해당 값을 반환 합니다.  
  
## 구문  
  
```  
__int64 __readmsr(   
   int register   
);  
```  
  
#### 매개 변수  
 \[in\] `register`  
 읽을 모델 특정 레지스터입니다.  
  
## 반환 값  
 지정 된 레지스터의 값입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__readmsr`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 만이 함수를 커널 모드에서 사용할 수 있습니다 및 루틴만 내장로 사용할 수 있습니다.  
  
 자세한 내용은 AMD 설명서를 참조 하십시오.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)