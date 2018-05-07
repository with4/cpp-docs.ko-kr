---
title: __svm_vmsave | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_vmsave
dev_langs:
- C++
helpviewer_keywords:
- VMSAVE instruction
- __svm_vmsave intrinsic
ms.assetid: 617a60bd-8514-4ba1-8066-bcf4dd481030
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36b1a76d4dca7a7177a44c56fc7c25832ace89c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="svmvmsave"></a>__svm_vmsave
**Microsoft 전용**  
  
 지정 된 가상 컴퓨터 제어 블록 (VMCB)에서 프로세서 상태의 하위 집합을 저장합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __svm_vmsave(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `VmcbPhysicalAddress`|VMCB의 실제 주소입니다.|  
  
## <a name="remarks"></a>설명  
 `__svm_vmsave` 함수는 동일는 `VMSAVE` 컴퓨터 명령입니다. 이 함수는 게스트 운영 체제 및 해당 응용 프로그램과 호스트 가상 머신 모니터의 상호 작용을 지원합니다. 자세한 내용을 보려면 문서에 대 한 검색 "AMD64 아키텍처 프로그래머의 수동 볼륨 2: 시스템 프로그래밍" 문서 번호 24593, 3.11, 아니면 나중에 수정 버전의 [AMD Corporation](http://go.microsoft.com/fwlink/p/?linkid=23746) 사이트입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__svm_vmsave`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [__svm_vmrun](../intrinsics/svm-vmrun.md)   
 [__svm_vmload](../intrinsics/svm-vmload.md)