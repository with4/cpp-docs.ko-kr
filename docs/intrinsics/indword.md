---
title: "__indword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__indword_cpp"
  - "__indword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "in 명령"
  - "__indword 내장 함수"
ms.assetid: 1068d686-586e-4e36-b962-d1d7c3315260
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# __indword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 사용 하 여 지정 된 포트에서 이중 단어 하나에 데이터를 읽고 있는 `in` 명령.  
  
## 구문  
  
```  
unsigned long __indword(  
   unsigned short Port  
);  
```  
  
#### 매개 변수  
 \[in\] `Port`  
 읽기 포트입니다.  
  
## 반환 값  
 포트에서 단어를 읽습니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__indword`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)