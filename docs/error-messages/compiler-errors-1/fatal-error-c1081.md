---
title: "심각한 오류 C1081 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1081
dev_langs: C++
helpviewer_keywords: C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8bac4aaf0d4aebcbc34f74b6ccb91170fd4224e4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1081"></a>심각한 오류 C1081
'symbol': 파일 이름이 너무 깁니다.  
  
 파일 경로 이름 길이 초과 `_MAX_PATH` (STDLIB.h에서 260 자 정의 됨). 파일의 이름을 줄이십시오.  
  
 짧은 파일 이름으로 CL.exe를 호출 하면 컴파일러 전체 경로 이름을 생성 해야 할 수 있습니다. 예를 들어 `cl -c myfile.cpp` 생성 하도록 컴파일러에 발생할 수 있습니다.  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```