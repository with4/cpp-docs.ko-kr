---
title: "__vmx_vmresume | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__vmx_vmresume"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__vmx_vmresume 내장 함수"
  - "VMRESUME 명령"
ms.assetid: 233fe1b6-c727-493a-a484-1b2363732281
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# __vmx_vmresume
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 현재 VMCS\(가상 컴퓨터 제어 구조\)를 사용하여 VMX 루트가 아닌 작업을 다시 시작합니다.  
  
## 구문  
  
```  
unsigned char __vmx_vmresume(  
   void);  
```  
  
## 반환 값  
  
|값|의미|  
|-------|--------|  
|0|작업에 성공했습니다.|  
|1|현재 VMCS의 `VM-instruction error field`에서 사용할 수 있는 확장된 상태로 작업이 실패했습니다.|  
|2|사용 가능한 상태 없이 작업이 실패했습니다.|  
  
## 설명  
 응용 프로그램에서 [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md) 또는 `__vmx_vmresume` 함수를 사용하여 VM 시작 작업을 수행할 수 있습니다.`__vmx_vmlaunch` 함수는 시작 상태가 `Clear`인 VMCS에서만 사용할 수 있으며, `__vmx_vmresume` 함수는 시작 상태가 `Launched`인 VMCS에서만 사용할 수 있습니다. 따라서 [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md) 함수를 사용하여 VMCS의 시작 상태를 `Clear`로 설정한 다음 첫 번째 VM 시작 작업에는 `__vmx_vmlaunch` 함수를 사용하고 이후 VM 시작 작업에는 `__vmx_vmresume` 함수를 사용합니다.  
  
 `__vmx_vmresume` 함수는 `VMRESUME` 컴퓨터 명령에 해당합니다. 이 함수는 게스트 운영 체제 및 해당 응용 프로그램과 호스트 가상 컴퓨터 모니터의 상호 작용을 지원합니다. 자세한 내용을 보려면 [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) 사이트에서 "IA\-32 Intel 아키텍처에 대한 Intel 가상화 기술 사양"\(문서 번호 C97063\-002\) PDF 문서를 검색하세요.  
  
## 요구 사항  
  
|내장 함수|아키텍처|  
|-----------|----------|  
|`__vmx_vmresume`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [\_\_vmx\_vmclear](../intrinsics/vmx-vmclear.md)