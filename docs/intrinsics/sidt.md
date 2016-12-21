---
title: "__sidt | Microsoft Docs"
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
  - "__sidt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sidt 명령"
  - "__sidt 내장 함수"
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __sidt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 지정 된 메모리 위치에 인터럽트 설명자 테이블 \(IDTR\) 레지스터의 값을 저장합니다.  
  
## 구문  
  
```  
void __sidt(  
     void *Destination);  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|\[in\] `Destination`|메모리 위치를 IDTR에 저장 되는 위치에 대 한 포인터입니다.|  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__sidt`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 `__sidt` 함수는 해당 하는 `SIDT` 컴퓨터 명령.  문서에 대 한 자세한 내용은 검색 "인텔 아키텍처 소프트웨어 개발자 설명서 볼륨 2: 명령 세트 참조,"에 [인텔사](http://go.microsoft.com/fwlink/?LinkId=127) 사이트.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [\_\_lidt](../intrinsics/lidt.md)