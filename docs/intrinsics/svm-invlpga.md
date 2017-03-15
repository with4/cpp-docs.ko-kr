---
title: "__svm_invlpga | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_invlpga"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__svm_invlpga 내장 함수"
  - "INVLPGA 명령"
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __svm_invlpga
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 컴퓨터의 번역 look\-aside 버퍼 주소 매핑 항목을 무효화합니다.  가상 주소 및 주소 공간 식별자 무효화 페이지의 매개 변수를 지정 합니다.  
  
## 구문  
  
```  
void __svm_invlpga(  
     void *Va,  
     int ASID);  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|\[in\] `Va`|가상 주소 무효화 하는 페이지입니다.|  
|\[in\] `ASID`|주소 공간 \(ASID\)의 식별자 무효화 하십시오.|  
  
## 설명  
 `__svm_invlpga` 함수는 해당 하는 `INVLPGA` 컴퓨터 명령.  이 기능은 상호 작용 하는 호스트의 가상 컴퓨터 모니터의 게스트 운영 체제와 응용 프로그램을 지원 합니다.  문서에 대 한 자세한 내용은 검색 "AMD64 아키텍처 프로그래머의 수동 볼륨 2: 시스템 프로그래밍," 문서 번호 24593, 3.11, 개정에는 [AMD 회사](http://go.microsoft.com/fwlink/?LinkId=23746) 사이트.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__svm_invlpga`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)