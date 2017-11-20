---
title: __nop | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __nop
dev_langs: C++
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aecf1c0ad205d2cbf0685797cc9527f1fc4684d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="nop"></a>__nop
**Microsoft 전용**  
  
 없는 작업을 수행 하는 플랫폼 특정 기계어 코드를 생성 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __nop();  
```  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__nop`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
**Microsoft 전용 종료**  
  
## <a name="remarks"></a>설명  
 `__nop` 함수는 동일는 `NOP` 컴퓨터 명령입니다. 자세한 내용을 보려면 문서에 대 한 검색 "Intel 아키텍처 소프트웨어 개발자 설명서, 볼륨 2: 명령 집합 참조"에 [Intel Corporation](http://go.microsoft.com/fwlink/?LinkId=127) 사이트입니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [__noop](../intrinsics/noop.md)