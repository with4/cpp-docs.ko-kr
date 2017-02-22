---
title: "__svm_vmrun | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__svm_vmrun"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__svm_vmrun 내장 함수"
  - "VMRUN 명령"
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# __svm_vmrun
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 지정한 가상 시스템이 제어 블록 \(VMCB\)에 해당 하는 가상 머신 게스트 코드의 실행을 시작 합니다.  
  
## 구문  
  
```  
void __svm_vmrun(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### 매개 변수  
  
|Parameter|설명|  
|---------------|--------|  
|\[in\] `VmcbPhysicalAddress`|실제 주소는 VMCB입니다.|  
  
## 설명  
 `__svm_vmrun` 함수를 사용 하는 최소한의 정보 VMCB에 게스트 가상 머신 코드 실행을 시작 합니다.  사용은 [\_\_svm\_vmsave](../intrinsics/svm-vmsave.md) 또는 [\_\_svm\_vmload](../intrinsics/svm-vmload.md) 복잡 한 인터럽트를 처리 하기 위해 또는 다른 게스트를 전환 하려면 자세한 정보가 필요할 경우 작동 합니다.  
  
 `__svm_vmrun` 함수는 해당 하는 `VMRUN` 컴퓨터 명령.  이 기능은 상호 작용 하는 호스트의 가상 컴퓨터 모니터의 게스트 운영 체제와 응용 프로그램을 지원 합니다.  문서에 대 한 자세한 내용은 검색 "AMD64 아키텍처 프로그래머의 수동 볼륨 2: 시스템 프로그래밍," 문서 번호 24593, 버전 3.11 또는 나중에 [AMD 회사](http://go.microsoft.com/fwlink/?LinkId=23746) 사이트.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__svm_vmrun`|x 86[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [\_\_svm\_vmsave](../intrinsics/svm-vmsave.md)   
 [\_\_svm\_vmload](../intrinsics/svm-vmload.md)