---
title: "__vmx_vmlaunch | Microsoft Docs"
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
  - "__vmx_vmlaunch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VMLAUNCH 명령"
  - "__vmx_vmlaunch 내장 함수"
ms.assetid: 708f7c38-b7c1-4ee7-bfc4-0daeb9cc9360
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmlaunch
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 현재 가상 컴퓨터 제어 구조 \(VMCS\)를 사용 하 여 호출 응용 프로그램에서 VMX 루트가 아닌 작업 상태 \(VM 입력\)를 배치 합니다.  
  
## 구문  
  
```  
unsigned char __vmx_vmlaunch(  
   void);  
```  
  
## 반환 값  
  
|값|의미|  
|-------|--------|  
|0|작업이 성공 했습니다.|  
|1|작업 실패와 확장 된 상태에서 사용할 수 있는 `VM-instruction error field` 현재 VMCS의.|  
|2|사용 가능한 상태가 없으면 작업이 실패 했습니다.|  
  
## 설명  
 응용 프로그램 중 하나를 사용 하 여 VM 입력 작업을 수행할 수 있는 [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) 또는 [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) 함수.  [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) 함수 시작 상태가 VMCS에만 사용할 수 있습니다 `Clear`, 및 [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) 함수 시작 상태가 VMCS에만 사용할 수 있습니다 `Launched`.  따라서 사용는 [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md) 하는 VMCS의 실행 상태를 설정 하는 함수 `Clear`, 다음 사용 하는 [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) 함수를 첫 번째 VM 입력 작업이 및 [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md) 후속 VM 입력 작업을 위한 함수.  
  
 `__vmx_vmlaunch` 함수는 해당 하는 `VMLAUNCH` 컴퓨터 명령.  이 기능은 상호 작용 하는 호스트의 가상 컴퓨터 모니터의 게스트 운영 체제와 응용 프로그램을 지원 합니다.  검색 문서, "인텔 가상화 기술 사양에는 ia\-32 인텔 아키텍처"에 대 한 자세한 내용은 번호 C97063\-002에서를 문서는 [인텔사](http://go.microsoft.com/fwlink/?LinkId=127) 사이트.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__vmx_vmlaunch`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmresume](../intrinsics/vmx-vmresume.md)   
 [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md)