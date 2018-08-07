---
title: __vmx_vmptrld | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmptrld
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmptrld intrinsic
- VMPTRLD instruction
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 599e15414a944602ee196f3910a1c5dd561c906d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324852"
---
# <a name="vmxvmptrld"></a>__vmx_vmptrld
**Microsoft 전용**  
  
 현재 가상 컴퓨터 제어 구조 (VMCS)에 지정된 된 주소에서 포인터를 로드합니다.  
  
## <a name="syntax"></a>구문  
  
```  
int __vmx_vmptrld(   
   unsigned __int64 *VmcsPhysicalAddress   
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in] *`VmcsPhysicalAddress`  
 VMCS 포인터 저장 되는 주소입니다.  
  
## <a name="return-value"></a>반환 값  
 0  
 작업에 성공했습니다.  
  
 1  
 현재 VMCS의 `VM-instruction error field` 에서 사용할 수 있는 확장된 상태로 작업이 실패했습니다.  
  
 2  
 사용 가능한 상태 없이 작업이 실패했습니다.  
  
## <a name="remarks"></a>설명  
 VMCS 포인터는 64 비트 물리적 주소입니다.  
  
 `__vmx_vmptrld` 함수는 동일는 `VMPTRLD` 컴퓨터 명령입니다. 이 함수는 게스트 운영 체제 및 해당 응용 프로그램과 호스트 가상 머신 모니터의 상호 작용을 지원합니다. 문서 번호 C97063-002, 자세한 내용은 "Intel 가상화 기술 사양에 대 한 the ia-32 Intel 아키텍처" 문서에 대 한 검색에 대 한는 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) 사이트입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__vmx_vmptrld`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmptrst](../intrinsics/vmx-vmptrst.md)