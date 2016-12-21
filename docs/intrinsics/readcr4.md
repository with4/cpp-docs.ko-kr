---
title: "__readcr4 | Microsoft Docs"
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
  - "__readcr4"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readcr4 내장 함수"
ms.assetid: b841a27b-fe0d-4ee9-b76b-f91d3eb061fa
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __readcr4
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 CR4 레지스터를 읽고 해당 값을 반환 합니다.  
  
## 구문  
  
```  
unsigned __int64 __readcr4(void);  
```  
  
## 반환 값  
 레지스터 CR4 값입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__readcr4`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이 내장만 커널 모드에서 사용할 수 있으며 루틴만 내장로 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)