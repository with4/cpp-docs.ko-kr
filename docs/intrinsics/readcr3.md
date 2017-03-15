---
title: "__readcr3 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__readcr3"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__readcr3 내장 함수"
ms.assetid: e24392c3-cad7-4788-8f31-94bf2e9e0053
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __readcr3
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 CR3 레지스터를 읽고 해당 값을 반환 합니다.  
  
## 구문  
  
```  
unsigned __int64 __readcr3(void);  
```  
  
## 반환 값  
 CR3 레지스터 값입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__readcr3`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이 내장만 커널 모드에서 사용할 수 있으며 루틴만 내장로 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)