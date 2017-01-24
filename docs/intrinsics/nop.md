---
title: "__nop | Microsoft Docs"
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
  - "__nop"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "nop 명령"
  - "__nop 내장 함수"
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __nop
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 없는 작업을 수행 하는 플랫폼별 기계어 코드를 생성 합니다.  
  
## 구문  
  
```  
void __nop();  
```  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__nop`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## Microsoft 특정 끝  
  
## 설명  
 `__nop` 함수는 해당 하는 `NOP` 컴퓨터 명령.  문서에 대 한 자세한 내용은 검색 "인텔 아키텍처 소프트웨어 개발자 설명서 볼륨 2: 명령 세트 참조,"에 [인텔사](http://go.microsoft.com/fwlink/?LinkId=127) 사이트.  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [\_\_noop](../intrinsics/noop.md)