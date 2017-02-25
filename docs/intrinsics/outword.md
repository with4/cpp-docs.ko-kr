---
title: "__outword | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__outword"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__outword 내장 함수"
  - "out 명령"
ms.assetid: 995f8834-0f50-4b4f-a7a2-af0e7c371cda
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# __outword
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성은 `out` 단어를 전송 하는 명령 `Data` 가 지정한 I\/O 포트가 아웃 `Port`.  
  
## 구문  
  
```  
void __outword(   
   unsigned short Port,   
   unsigned short Data   
);  
```  
  
#### 매개 변수  
 \[in\] `Port`  
 데이터를 보낼 포트입니다.  
  
 \[in\] `Data`  
 전송 될 데이터입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__outword`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)