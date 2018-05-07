---
title: __svm_skinit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __svm_skinit
dev_langs:
- C++
helpviewer_keywords:
- SKINIT instruction
- __svm_skinit intrinsic
ms.assetid: 787ec781-4cf2-40a2-aa20-5192334b131a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95e47608b7ec58e433d9be5e2f2178a825b6be2e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="svmskinit"></a>__svm_skinit
**Microsoft 전용**  
  
 가상 컴퓨터 모니터와 같은 확인할 수 있는 보안 소프트웨어의 로딩을 시작 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __svm_skinit(  
   int SLB  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`SLB`|64k 바이트의 실제 32 비트 주소 Secure 로더 블록 SLB ().|  
  
## <a name="remarks"></a>설명  
 `__svm_skinit` 함수는 동일는 `SKINIT` 컴퓨터 명령입니다. 이 함수는 프로세서 및 신뢰할 수 있는 플랫폼 모듈 (TPM) 확인 하 고 신뢰할 수 있는 소프트웨어 (디스크)에 대 한 보안 커널 라는 로드를 사용 하는 보안 시스템의 일부입니다. 가상 컴퓨터 모니터는 보안에 대 한 커널의 예시입니다. 보안 시스템 프로그램 구성 요소 초기화 프로세스 중에 로드 하 고 컴퓨터가 다중 프로세서 인터럽트, 장치 액세스 또는 다른 응용 프로그램에서 조작 으로부터 보호 하는 구성 요소를 확인 합니다.  
  
 `SLB` 라는 메모리 64k 블록의 실제 주소를 지정 하는 매개 변수는 *로더 블록 Secure* (SLB). SLB는 컴퓨터에 대 한 운영 환경을 설정 하 고 이후에 보안 커널을 로드 하는 보안 로더를 호출 하는 프로그램을 포함 합니다.  
  
 이 함수는 게스트 운영 체제 및 해당 응용 프로그램과 호스트 가상 머신 모니터의 상호 작용을 지원합니다. 자세한 내용을 보려면 문서에 대 한 검색 "AMD64 아키텍처 프로그래머의 수동 볼륨 2: 시스템 프로그래밍" 24593, 3.11, 수정 버전 번호에 문서는 [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746) 사이트입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__svm_skinit`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)