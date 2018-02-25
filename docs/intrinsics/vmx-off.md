---
title: __vmx_off | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __vmx_off
dev_langs:
- C++
helpviewer_keywords:
- VMXOFF instruction
- __vmx_off intrinsic
ms.assetid: 78a32d46-9291-406c-b982-a550855aff18
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 885df9a8e5e4cb1334a3f18acaf2513d64b91724
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="vmxoff"></a>__vmx_off
**Microsoft 전용**  
  
 프로세서에서 가상 컴퓨터 확장 (VMX) 작업을 비활성화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __vmx_off();  
```  
  
## <a name="remarks"></a>설명  
 `__vmx_off` 함수는 동일는 `VMXOFF` 컴퓨터 명령입니다. 이 함수는 게스트 운영 체제 및 해당 응용 프로그램과 호스트 가상 컴퓨터 모니터의 상호 작용을 지원합니다. 문서 번호 C97063-002, 자세한 내용은 "Intel 가상화 기술 사양에 대 한 the ia-32 Intel 아키텍처" 문서에 대 한 검색에 대 한는 [Intel Corporation](http://go.microsoft.com/fwlink/p/?linkid=127) 사이트입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__vmx_off`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)