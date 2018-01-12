---
title: "_initterm, _initterm_e | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _initterm_e
- _initterm
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _initterm_e
- initterm
- _initterm
- initterm_e
dev_langs: C++
helpviewer_keywords:
- initterm function
- initterm_e function
- _initterm function
- _initterm_e function
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 95f508b1198cd009abe0cf82cbe9a7aaf553240f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="initterm-initterme"></a>_initterm, _initterm_e
함수 포인터의 테이블을 실행하고 초기화하는 내부 메서드입니다.  
  
 첫 번째 포인터는 테이블의 시작 위치이고 두 번째 포인터는 끝 위치입니다.  
  
## <a name="syntax"></a>구문  
  
```  
void __cdecl _initterm(  
   PVFV *,  
   PVFV *  
);  
  
int __cdecl _initterm_e(  
   PVFV *,  
   PVFV *  
);  
```  
  
## <a name="return-value"></a>반환 값  
 초기화에 실패하면 0이 아닌 값을 반환하고 오류를 throw하고, 오류가 발생하지 않으면 0을 반환합니다.  
  
## <a name="remarks"></a>설명  
 이러한 메서드는 C++ 프로그램 초기화 중 내부적으로만 호출됩니다. 프로그램에서 이러한 메서드를 호출하지 마십시오.  
  
 이러한 메서드가 함수 입력 테이블을 실행할 때 `NULL` 항목은 건너뛴 다음 계속됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [사전순 함수 참조](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)