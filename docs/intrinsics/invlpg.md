---
title: __invlpg | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __invlpg
- __invlpg_cpp
dev_langs:
- C++
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e6977d9a8cb21cf1eeefb404ddbff263643189d9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/23/2018
---
# <a name="invlpg"></a>__invlpg
**Microsoft 전용**  
  
 X86 생성 `invlpg` translation lookaside 버퍼 (TLB)를 통해 메모리와 관련 된 페이지에 대 한 무효화 명령 `Address`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __invlpg(  
   void* Address  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 [in]  `Address`  
 64 비트 주소입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__invlpg`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
## <a name="remarks"></a>설명  
 내장 `__invlpg` 특수 명령을 내보냅니다 하며 0의 권한 수준 (CPL)를 사용 하 여 커널 모드에서 사용할 수만 있습니다.  
  
 이 루틴은 내장 루틴으로만 사용할 수 있습니다.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)