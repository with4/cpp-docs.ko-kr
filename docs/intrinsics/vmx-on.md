---
title: __vmx_on | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_on
dev_langs:
- C++
helpviewer_keywords:
- VMXON instruction
- __vmx_on intrinsic
ms.assetid: 16804991-6a75-4adf-8ec2-bc95acfa4801
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: faa4325dc55bee53f2a19b192bb0c699dd89eb0b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333094"
---
# <a name="vmxon"></a>__vmx_on
**Microsoft 전용**  
  
 프로세서에서 가상 컴퓨터 확장 (VMX) 작업을 활성화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned char __vmx_on(  
   unsigned __int64 *VmsSupportPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] `VmsSupportPhysicalAddress`  
 가상 컴퓨터 제어 구조 (VMCS)를 가리키는 64 비트 물리적 주소에 대 한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
|값|의미|  
|-----------|-------------|  
|0|작업에 성공했습니다.|  
|1|현재 VMCS의 `VM-instruction error field` 에서 사용할 수 있는 확장된 상태로 작업이 실패했습니다.|  
|2|사용 가능한 상태 없이 작업이 실패했습니다.|  
  
## <a name="remarks"></a>설명  
 `__vmx_on` 에 해당 하는 함수는 `VMXON` 컴퓨터 명령입니다. 이 함수는 게스트 운영 체제 및 해당 응용 프로그램과 호스트 가상 머신 모니터의 상호 작용을 지원합니다. 문서 번호 C97063-002, 자세한 내용은 "Intel 가상화 기술 사양에 대 한 the ia-32 Intel 아키텍처" 문서에 대 한 검색에 대 한는 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) 사이트입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__vmx_on`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)