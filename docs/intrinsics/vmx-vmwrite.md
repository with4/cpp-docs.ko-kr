---
title: __vmx_vmwrite | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __vmx_vmwrite
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 08cd68256e1219df36ce6f9ea22165938fba44af
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="vmxvmwrite"></a>__vmx_vmwrite
**Microsoft 전용**  
  
 현재 가상 컴퓨터 제어 구조 (VMCS)에 지정된 된 필드에 지정 된 값을 씁니다.  
  
## <a name="syntax"></a>구문  
  
```  
unsigned char __vmx_vmwrite(   
   size_t Field,  
   size_t FieldValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `Field`|쓸 VMCS 필드입니다.|  
|[in] `FieldValue`|VMCS 필드에 쓸 값입니다.|  
  
## <a name="return-value"></a>반환 값  
 0  
 작업에 성공했습니다.  
  
 1  
 현재 VMCS의 `VM-instruction error field` 에서 사용할 수 있는 확장된 상태로 작업이 실패했습니다.  
  
 2  
 사용 가능한 상태 없이 작업이 실패했습니다.  
  
## <a name="remarks"></a>설명  
 `__vmx_vmwrite` 함수는 동일는 `VMWRITE` 컴퓨터 명령입니다. 값은 `Field` 매개 변수는 Intel 설명서에 설명 되어 있는 인코딩된 필드 인덱스입니다. 문서 번호 C97063-002, 자세한 내용은 "Intel 가상화 기술 사양에 대 한 the ia-32 Intel 아키텍처" 문서에 대 한 검색에 대 한는 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) 사이트 하 고 다음의 부록 C을 참조 하십시오. 문서입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__vmx_vmwrite`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [__vmx_vmread](../intrinsics/vmx-vmread.md)