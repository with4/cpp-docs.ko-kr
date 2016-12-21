---
title: "__outdwordstring | Microsoft Docs"
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
  - "__outdwordstring"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "outsd 명령"
  - "__outdwordstring 내장 함수"
  - "rep outsd 명령"
ms.assetid: 55b31a65-aab7-4b5c-b61d-d9e2fb0c497a
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __outdwordstring
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 생성은 `rep outsd`명령을 보냅니다 `Count` 부터 더블 워드 개 `Buffer` 가 지정한 I\/O 포트가 아웃 `Port`.  
  
## 구문  
  
```  
void __outdwordstring(   
   unsigned short Port,   
   unsigned long* Buffer,   
   unsigned long Count   
);  
```  
  
#### 매개 변수  
 \[in\] `Port`  
 데이터를 보낼 포트입니다.  
  
 \[in\] `Buffer`  
 지정 된 포트로 보낼 수 있는 데이터에 대 한 포인터입니다.  
  
 \[in\] `Count`  
 보낼 더블 워드 개 개수입니다.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__outdwordstring`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 이 루틴에만 내장로 사용할 수 있습니다.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)