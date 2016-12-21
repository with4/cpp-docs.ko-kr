---
title: "__lidt | Microsoft Docs"
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
  - "__lidt"
  - "__lidt_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LIDT 명령"
  - "__lidt 내장 함수"
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __lidt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 값이 지정 된 메모리 위치에 인터럽트 설명자 테이블 레지스터 \(IDTR\)를 로드합니다.  
  
## 구문  
  
```  
void __lidt(  
     void *Source);  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|\[in\] `Source`|포인터를 IDTR에 복사 될 값입니다.|  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__lidt`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 `__lidt` 함수는 해당 하는 `LIDT` 명령, 가공 및 커널 모드 에서만 사용할 수 있습니다.  문서에 대 한 자세한 내용은 검색 "인텔 아키텍처 소프트웨어 개발자 설명서 볼륨 2: 명령 세트 참조,"에 [인텔사](http://go.microsoft.com/fwlink/?LinkId=127) 사이트.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [\_\_sidt](../intrinsics/sidt.md)