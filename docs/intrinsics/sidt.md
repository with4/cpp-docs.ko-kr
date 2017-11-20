---
title: __sidt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __sidt
dev_langs: C++
helpviewer_keywords:
- sidt instruction
- __sidt intrinsic
ms.assetid: 01e83d14-6e63-4dea-8f64-5a0339d69641
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c952c23af6e1695ca9032e0687334c4ebb881a1f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="sidt"></a>__sidt
**Microsoft 전용**  
  
 지정된 된 메모리 위치에 인터럽트 설명자 테이블 레지스터 (IDTR)의 값을 저장합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __sidt(  
     void *Destination);  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|[in] `Destination`|IDTR 저장 된 메모리 위치에 대 한 포인터입니다.|  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__sidt`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 `__sidt` 함수는 동일는 `SIDT` 컴퓨터 명령입니다. 자세한 내용을 보려면 문서에 대 한 검색 "Intel 아키텍처 소프트웨어 개발자 설명서, 볼륨 2: 명령 집합 참조"에 [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) 사이트입니다.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [__lidt](../intrinsics/lidt.md)