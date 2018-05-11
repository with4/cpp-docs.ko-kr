---
title: 수학 오류 M6108 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- M6108
dev_langs:
- C++
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4dfeca48aa04ebfbc097649e5c25253166c50dad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="math-error-m6108"></a>수학 오류 M6108
제곱근  
  
 제곱근 연산에서 피연산자가 음수입니다.  
  
 프로그램은 136 종료 코드로 종료 됩니다.  
  
> [!NOTE]
>  `sqrt` 포트란 내장 함수는 C 런타임 라이브러리의 함수 **SQRT** 이 오류를 생성 하지 않습니다. C `sqrt` 함수는 연산을 수행 하기 전에 인수를 확인 하 고는 피연산자가 음수 이면 오류 값을 반환 합니다. 포트란 **SQRT** 도메인 오류를 생성 하는 함수 [M6201](../../error-messages/tool-errors/math-error-m6201.md) 이 오류는 대신 합니다.