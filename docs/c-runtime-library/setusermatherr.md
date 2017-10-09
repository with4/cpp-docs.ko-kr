---
title: __setusermatherr | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __setusermatherr
apilocation:
- msvcr80.dll
- msvcr90.dll
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __setusermatherr
dev_langs:
- C++
helpviewer_keywords:
- __setusermatherr
ms.assetid: f306818d-381a-4d68-8739-71b92bacb5ea
caps.latest.revision: 2
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: fa4f5b7b60bf4ea6fea0d0d63d2ee911101174b5
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="setusermatherr"></a>__setusermatherr
[_matherr](../c-runtime-library/reference/matherr.md) 루틴 대신 수학 오류를 처리하기 위한 사용자 제공 루틴을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
void __setusermatherr(  
   _HANDLE_MATH_ERROR pf   
   )  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pf`  
 사용자가 제공하는 `_matherr`의 구현에 대한 포인터입니다.  
  
 `pf` 매개 변수의 형식은 `typedef int (__cdecl * _HANDLE_MATH_ERROR)(struct _exception *)`로 선언됩니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
  
|루틴|필수 헤더|  
|-------------|---------------------|  
|__setusermatherr|matherr.c|
