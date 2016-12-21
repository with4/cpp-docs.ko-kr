---
title: "__svm_clgi | Microsoft Docs"
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
  - "__svm_clgi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLGI 명령"
  - "__svm_clgi 내장 함수"
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __svm_clgi
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 글로벌 인터럽트 플래그를 지웁니다.  
  
## 구문  
  
```  
void __svm_clgi( void );  
```  
  
## 설명  
 `__svm_clgi` 함수는 해당 하는 `CLGI` 컴퓨터 명령.  글로벌 인터럽트 플래그 마이크로프로세서 무시, 연기, 또는 I\/O 완료, 하드웨어 온도 경고, 디버그 예외와 같은 이벤트 때문에 인터럽트를 처리 하는지 여부를 결정 합니다.  
  
 이 기능은 상호 작용 하는 호스트의 가상 컴퓨터 모니터의 게스트 운영 체제와 응용 프로그램을 지원 합니다.  문서에 대 한 자세한 내용은 검색 "AMD64 아키텍처 프로그래머의 수동 볼륨 2: 시스템 프로그래밍," 문서 번호 24593, 3.11, 개정에는 [AMD 회사](http://go.microsoft.com/fwlink/?LinkId=23746) 사이트.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__svm_clgi`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_stgi](../intrinsics/svm-stgi.md)