---
title: __vmx_vmclear | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmclear
dev_langs:
- C++
helpviewer_keywords:
- VMCLEAR instruction
- __vmx_vmclear intrinsic
ms.assetid: e3eb98e4-50fc-4c93-9bac-340fd1f0a466
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8da1e3d2c5b1a2018df0e46f085fede9b923fff8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="vmxvmclear"></a>__vmx_vmclear
**Microsoft 전용**  
  
 (VMCS)의 지정 된 가상 컴퓨터 제어 구조를 초기화 하 고 시작 상태로 설정 `Clear`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned char __vmx_vmclear(  
   unsigned __int64 *VmcsPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `VmcsPhysicalAddress`|지울 VMCS의 실제 주소를 포함 하는 64 비트 메모리 위치에 대 한 포인터입니다.|  
  
## <a name="return-value"></a>반환 값  
  
|값|의미|  
|-----------|-------------|  
|0|작업에 성공했습니다.|  
|1|현재 VMCS의 `VM-instruction error field` 에서 사용할 수 있는 확장된 상태로 작업이 실패했습니다.|  
|2|사용 가능한 상태 없이 작업이 실패했습니다.|  
  
## <a name="remarks"></a>설명  
 응용 프로그램 중 하나를 사용 하 여 VM 시작 작업을 수행할 수는 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 또는 [__vmx_vmresume](../intrinsics/vmx-vmresume.md) 함수입니다. [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 함수는 시작 상태가 인 VMCS 에서만 사용할 수 있습니다 `Clear`, 및 [__vmx_vmresume](../intrinsics/vmx-vmresume.md) 함수는 시작 상태가 인 VMCS 에서만 사용할 수 있습니다 `Launched`합니다. 따라서 사용 하 여는 [__vmx_vmclear](../intrinsics/vmx-vmclear.md) 를 VMCS의 시작 상태를 설정 하려면 함수 `Clear`합니다. 사용 하 여는 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md) 첫 번째 VM 시작 작업에 대 한 함수 및 [__vmx_vmresume](../intrinsics/vmx-vmresume.md) 이후 VM 시작 작업에 대 한 함수입니다.  
  
 `__vmx_vmclear` 함수는 동일는 `VMCLEAR` 컴퓨터 명령입니다. 이 함수는 게스트 운영 체제 및 해당 응용 프로그램과 호스트 가상 머신 모니터의 상호 작용을 지원합니다. 문서 번호 C97063-002, 자세한 내용은 "Intel 가상화 기술 사양에 대 한 the ia-32 Intel 아키텍처" 문서에 대 한 검색에 대 한는 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) 사이트입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__vmx_vmclear`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmlaunch](../intrinsics/vmx-vmlaunch.md)   
 [__vmx_vmresume](../intrinsics/vmx-vmresume.md)