---
title: __halt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __halt
- __halt_cpp
dev_langs:
- C++
helpviewer_keywords:
- __halt intrinsic
- HLT instruction
ms.assetid: a074f44a-101c-45a5-8a5e-cfd223c34002
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1d2d3a530fe5e300c59cfd9ffa1d509b3b41b0f2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="halt"></a>__halt
**Microsoft 전용**  
  
 활성화 된 인터럽트, 마스크 불가능 인터럽트 (NMI) 또는 다시 설정 수행 될 때까지 마이크로프로세서를 중단 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __halt( void );  
```  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__halt`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 `__halt` 함수는 동일는 `HLT` 컴퓨터, 명령 및 커널 모드 에서만 사용할 수 있습니다. 자세한 내용을 보려면 문서에 대 한 검색 "Intel 아키텍처 소프트웨어 개발자 설명서, 볼륨 2: 명령 집합 참조"에 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) 사이트입니다.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)