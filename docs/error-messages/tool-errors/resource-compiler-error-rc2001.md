---
title: 리소스 컴파일러 오류 RC2001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2001
dev_langs:
- C++
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ef1fd5d29fc5784ee418a8456cacec37e943b73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-error-rc2001"></a>리소스 컴파일러 오류 RC2001
상수에 줄 바꿈  
  
 문자열 상수는 백슬래시 포함 하지 않고 두 번째 줄에 계속 되었습니다 (**\\**) 또는 닫고 큰따옴표를 열면 (**"**).  
  
 소스 파일에서 두 줄에 있는 문자열 상수를 중단 하려면 다음 중 하나를 수행 합니다.  
  
-   백슬래시가 줄 연속 문자를 첫 번째 줄의 끝입니다.  
  
-   큰따옴표와 첫 번째 줄에 문자열을 닫고 다른 큰따옴표로 다음 줄에서 문자열을 엽니다.  
  
 \N 이스케이프 시퀀스는 문자열 상수에 줄 바꿈 문자를 포함 하기 위한으로 첫 번째 줄의 끝에 충분 하지 않습니다.