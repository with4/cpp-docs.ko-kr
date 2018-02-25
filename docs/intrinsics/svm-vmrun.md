---
title: __svm_vmrun | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __svm_vmrun
dev_langs:
- C++
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 988a045bc957d5920fee7e3e659d7a0b4f02d8d2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="svmvmrun"></a>__svm_vmrun
**Microsoft 전용**  
  
 지정 된 가상 컴퓨터 제어 블록 (VMCB)에 해당 하는 가상 컴퓨터 게스트 코드의 실행을 시작 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __svm_vmrun(  
   size_t VmcbPhysicalAddress  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `VmcbPhysicalAddress`|VMCB의 실제 주소입니다.|  
  
## <a name="remarks"></a>설명  
 `__svm_vmrun` 함수를 사용 하 여 최소한의 정보는 VMCB에 가상 컴퓨터 게스트 코드 실행을 시작 합니다. 사용 하 여는 [__svm_vmsave](../intrinsics/svm-vmsave.md) 또는 [__svm_vmload](../intrinsics/svm-vmload.md) 복잡 한 인터럽트 처리 하기 위해 또는 다른 게스트로 전환 하는 추가 정보를 필요로 하는 경우에 작동 합니다.  
  
 `__svm_vmrun` 함수는 동일는 `VMRUN` 컴퓨터 명령입니다. 이 함수는 게스트 운영 체제 및 해당 응용 프로그램과 호스트 가상 컴퓨터 모니터의 상호 작용을 지원합니다. 자세한 내용을 보려면 문서에 대 한 검색 "AMD64 아키텍처 프로그래머의 수동 볼륨 2: 시스템 프로그래밍" 문서 번호 24593, 3.11, 아니면 나중에 수정 버전의 [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746) 사이트입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__svm_vmrun`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [__svm_vmsave](../intrinsics/svm-vmsave.md)   
 [__svm_vmload](../intrinsics/svm-vmload.md)