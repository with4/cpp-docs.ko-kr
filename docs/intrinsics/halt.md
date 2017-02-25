---
title: "__halt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__halt"
  - "__halt_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__halt 내장 함수"
  - "HLT 명령"
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __halt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 사용 가능한 인터럽트는 마스크 불가능 인터럽트 \(NMI\), 다시 발생할 때까지 마이크로프로세서를 중지 합니다.  
  
## 구문  
  
```  
void __halt( void );  
```  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__halt`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## 설명  
 `__halt` 함수는 해당 하는 `HLT` 명령, 가공 및 커널 모드 에서만 사용할 수 있습니다.  문서에 대 한 자세한 내용은 검색 "인텔 아키텍처 소프트웨어 개발자 설명서 볼륨 2: 명령 세트 참조,"에 [인텔사](http://go.microsoft.com/fwlink/?LinkId=127) 사이트.  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)