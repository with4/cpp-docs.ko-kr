---
title: 리소스 컴파일러 오류 RC2101 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2101
dev_langs:
- C++
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b07f6211e1cc36bd471b04126e724e42eb610641
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-error-rc2101"></a>리소스 컴파일러 오류 RC2101
전처리 RC 파일에서 잘못 된 지시문  
  
 리소스 컴파일러 파일에 포함 되어는 **#pragma** 지시문입니다.  
  
 사용 하 여 **#ifndef** 전처리기 지시문은 리소스 컴파일러를 정의 하는 include 파일을 처리할 때 RC_INVOKED 상수와 합니다. 위치는 **#pragma** RC_INVOKED 상수 정의 될 때 처리 되지 않은 코드 블록 안에 지시문입니다. C/c + + 컴파일러에 의해서만 및 리소스 컴파일러가 아니라 블록의 코드에서에서 처리 됩니다. 다음 샘플 코드에이 기술을 보여 줍니다.  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 **#pragma** 전처리기 지시문에서 의미가 있는 합니다. RC 파일입니다. **#include** 전처리기 지시문에서 자주 사용 되는 합니다. RC 파일 헤더 파일 (프로젝트 기반 사용자 지정 헤더 파일 또는 제품 중 하나를 Microsoft에서 제공 하는 표준 헤더 파일)을 포함 합니다. 포함 파일 포함 된 **#pragma** 지시문입니다. 헤더 파일을 하나 이상의 다른 헤더 파일, 잘못 된 포함 된 파일을 포함할 수 있으므로 **#pragma** 지시문을 즉시 알아낼 수 있습니다.  
  
 **#ifndef** RC_INVOKED 기술을 프로젝트 기반 헤더 파일의 헤더 파일 포함 하 여 제어할 수 있습니다.