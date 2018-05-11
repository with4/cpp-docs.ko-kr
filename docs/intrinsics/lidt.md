---
title: __lidt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __lidt
- __lidt_cpp
dev_langs:
- C++
helpviewer_keywords:
- LIDT instruction
- __lidt intrinsic
ms.assetid: 8298d25d-a19e-4900-828d-6b3b09841882
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8dd972d2a7e8d75f7149b2dc2766ffca86b0b2e5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="lidt"></a>__lidt
**Microsoft 전용**  
  
 지정된 된 메모리 위치에 값을 가진 인터럽트 설명자 테이블 레지스터 (IDTR)를 로드합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __lidt(  
     void *Source);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `Source`|IDTR에 복사할 값에 대 한 포인터입니다.|  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__lidt`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 `__lidt` 함수는 동일는 `LIDT` 컴퓨터, 명령 및 커널 모드 에서만 사용할 수 있습니다. 자세한 내용을 보려면 문서에 대 한 검색 "Intel 아키텍처 소프트웨어 개발자 설명서, 볼륨 2: 명령 집합 참조"에 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) 사이트입니다.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [__sidt](../intrinsics/sidt.md)