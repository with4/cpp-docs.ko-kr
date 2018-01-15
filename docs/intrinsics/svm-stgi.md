---
title: __svm_stgi | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __svm_stgi
dev_langs: C++
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 94e386827ae747fb3289354ba380d390756359ff
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2018
---
# <a name="svmstgi"></a>__svm_stgi
**Microsoft 전용**  
  
 전역 인터럽트 플래그를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __svm_stgi(void);  
```  
  
## <a name="remarks"></a>설명  
 `__svm_stgi` 함수는 동일는 `STGI` 컴퓨터 명령입니다. 전역 인터럽트 플래그 하는지를 결정 합니다. 마이크로프로세서 무시은, I/O 완료, 하드웨어 온도 경고 또는 디버그 예외와 같은 이벤트 때문 인터럽트를 처리 합니다.  
  
 이 함수는 게스트 운영 체제 및 해당 응용 프로그램과 호스트 가상 컴퓨터 모니터의 상호 작용을 지원합니다. 자세한 내용을 보려면 문서에 대 한 검색 "AMD64 아키텍처 프로그래머의 수동 볼륨 2: 시스템 프로그래밍" 24593, 3.11, 수정 버전 번호에 문서는 [AMD corporation](http://go.microsoft.com/fwlink/p/?linkid=23746) 사이트입니다.  
  
## <a name="requirements"></a>요구 사항  
  
|내장 함수|아키텍처|  
|---------------|------------------|  
|`__svm_stgi`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **헤더 파일** \<. h >  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)   
 [__svm_clgi](../intrinsics/svm-clgi.md)