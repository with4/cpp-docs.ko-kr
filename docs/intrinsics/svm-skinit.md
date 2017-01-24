---
title: "__svm_skinit | Microsoft Docs"
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
  - "__svm_skinit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SKINIT 명령"
  - "__svm_skinit 내장 함수"
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __svm_skinit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 가상 머신 모니터 같은 확인할 수 있는 보안 소프트웨어의 로딩을 시작합니다.  
  
## 구문  
  
```  
void __svm_skinit(  
   int SLB  
);  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|`SLB`|64 K 바이트 32 비트 실제 주소 보안 로더 블록 \(SLB\).|  
  
## 설명  
 `__svm_skinit` 함수는 해당 하는 `SKINIT` 컴퓨터 명령.  이 함수는 프로세서와 신뢰할 수 있는 플랫폼 모듈 \(TPM\)을 사용 하 여 확인 하 고 보안 커널 \(SK\) 라는 신뢰할 수 있는 소프트웨어를 로드 하는 보안 시스템의 일부입니다.  가상 머신 모니터 보안 커널의 예입니다.  프로그램 구성 요소를 초기화 하는 동안 로드 되 고 구성 요소가 다중 프로세서 컴퓨터인 경우 인터럽트, 장치 액세스 또는 다른 프로그램으로 위조를 방지 합니다. 보안 시스템을 확인 합니다.  
  
 `SLB` 매개 변수 지정 이라는 메모리 64 K 블록의 실제 주소는  *보안 로더 블록* \(SLB\).  SLB는 라는 컴퓨터 운영 환경을 설정 하 고 보안 커널 이후에 로드 보안 로더 프로그램을 포함 합니다.  
  
 이 기능은 상호 작용 하는 호스트의 가상 컴퓨터 모니터의 게스트 운영 체제와 응용 프로그램을 지원 합니다.  문서에 대 한 자세한 내용은 검색 "AMD64 아키텍처 프로그래머의 수동 볼륨 2: 시스템 프로그래밍," 문서 번호 24593, 3.11, 개정에는 [AMD 회사](http://go.microsoft.com/fwlink/?LinkId=23746) 사이트.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__svm_skinit`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)