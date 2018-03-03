---
title: "수학 오류 M6108 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- M6108
dev_langs:
- C++
helpviewer_keywords:
- M6108
ms.assetid: 054893b4-49bc-45d9-882f-7cb50ba387c0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6db123d9cb96274848a3edd9f845f86f413d8e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="math-error-m6108"></a>수학 오류 M6108
제곱근  
  
 제곱근 연산에서 피연산자가 음수입니다.  
  
 프로그램은 136 종료 코드로 종료 됩니다.  
  
> [!NOTE]
>  `sqrt` 포트란 내장 함수는 C 런타임 라이브러리의 함수 **SQRT** 이 오류를 생성 하지 않습니다. C `sqrt` 함수는 연산을 수행 하기 전에 인수를 확인 하 고는 피연산자가 음수 이면 오류 값을 반환 합니다. 포트란 **SQRT** 도메인 오류를 생성 하는 함수 [M6201](../../error-messages/tool-errors/math-error-m6201.md) 이 오류는 대신 합니다.