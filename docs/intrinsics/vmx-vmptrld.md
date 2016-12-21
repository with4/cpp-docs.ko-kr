---
title: "__vmx_vmptrld | Microsoft Docs"
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
  - "__vmx_vmptrld"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__vmx_vmptrld 내장 함수"
  - "VMPTRLD 명령"
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __vmx_vmptrld
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
 포인터가 현재 가상 컴퓨터 제어 구조 \(VMCS\)에 지정 된 주소에서 로드합니다.  
  
## 구문  
  
```  
int __vmx_vmptrld(   
   unsigned __int64 *VmcsPhysicalAddress   
);  
```  
  
#### 매개 변수  
 \[in\] \*`VmcsPhysicalAddress`  
 VMCS 포인터가 저장 되는 위치는 주소입니다.  
  
## 반환 값  
 0  
 작업이 성공 했습니다.  
  
 1  
 작업 실패와 확장 된 상태에서 사용할 수 있는 `VM-instruction error field` 현재 VMCS의.  
  
 2  
 사용 가능한 상태가 없으면 작업이 실패 했습니다.  
  
## 설명  
 VMCS 포인터는 64 비트 물리적 주소입니다.  
  
 `__vmx_vmptrld` 함수는 해당 하는 `VMPTRLD` 컴퓨터 명령.  이 기능은 상호 작용 하는 호스트의 가상 컴퓨터 모니터의 게스트 운영 체제와 응용 프로그램을 지원 합니다.  검색 문서, "인텔 가상화 기술 사양에는 ia\-32 인텔 아키텍처"에 대 한 자세한 내용은 번호 C97063\-002에서를 문서는 [인텔사](http://go.microsoft.com/fwlink/?LinkId=127) 사이트.  
  
## 요구 사항  
  
|내장|아키텍처|  
|--------|----------|  
|`__vmx_vmptrld`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<intrin.h\>  
  
## Microsoft 특정 끝  
  
## 참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [\_\_vmx\_vmptrst](../intrinsics/vmx-vmptrst.md)