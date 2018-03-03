---
title: "리소스 컴파일러 오류 RC2001 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC2001
dev_langs:
- C++
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c04110898780495f918c1e37c0068daead340a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rc2001"></a>리소스 컴파일러 오류 RC2001
상수에 줄 바꿈  
  
 문자열 상수는 백슬래시 포함 하지 않고 두 번째 줄에 계속 되었습니다 (**\\**) 또는 닫고 큰따옴표를 열면 (**"**).  
  
 소스 파일에서 두 줄에 있는 문자열 상수를 중단 하려면 다음 중 하나를 수행 합니다.  
  
-   백슬래시가 줄 연속 문자를 첫 번째 줄의 끝입니다.  
  
-   큰따옴표와 첫 번째 줄에 문자열을 닫고 다른 큰따옴표로 다음 줄에서 문자열을 엽니다.  
  
 \N 이스케이프 시퀀스는 문자열 상수에 줄 바꿈 문자를 포함 하기 위한으로 첫 번째 줄의 끝에 충분 하지 않습니다.