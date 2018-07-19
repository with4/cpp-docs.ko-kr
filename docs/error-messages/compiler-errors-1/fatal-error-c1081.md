---
title: 심각한 오류 C1081 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1081
dev_langs:
- C++
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b5ea18ff3f2714d9621d4372cf541be2f9b225a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230524"
---
# <a name="fatal-error-c1081"></a>심각한 오류 C1081
'symbol': 파일 이름이 너무 깁니다.  
  
 파일 경로 이름 길이 초과 `_MAX_PATH` (STDLIB.h에서 260 자 정의 됨). 파일의 이름을 줄이십시오.  
  
 짧은 파일 이름으로 CL.exe를 호출 하면 컴파일러 전체 경로 이름을 생성 해야 할 수 있습니다. 예를 들어 `cl -c myfile.cpp` 생성 하도록 컴파일러에 발생할 수 있습니다.  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```