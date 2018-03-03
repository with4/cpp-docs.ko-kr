---
title: "NMAKE 심각한 오류 U1056 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1056
dev_langs:
- C++
helpviewer_keywords:
- U1056
ms.assetid: da855728-b69e-413c-83ed-df912126215e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 41db646e2559051c11de5265900dde8ad0a03214
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1056"></a>NMAKE 심각한 오류 U1056
명령 처리기를 찾을 수 없습니다.  
  
 명령 처리기에 지정 된 경로에 없습니다.는 **COMSPEC** 또는 **경로** 환경 변수입니다.  
  
 NMAKE 모드를 사용할지 COMMAND.COM cmd. Exe 명령을 실행할 때 명령 처리기로 사용 합니다. 에 설정 된 경로에 명령 처리기를 먼저 찾고 **COMSPEC**합니다. 경우 **COMSPEC** NMAKE 검색에 지정 된 디렉터리가 존재 하지 않는 **경로**합니다.