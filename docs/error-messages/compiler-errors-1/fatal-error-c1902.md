---
title: 심각한 오류 C1902 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1902
dev_langs:
- C++
helpviewer_keywords:
- C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b23507b6531f9ee4e5ce5efd5b60a1977206635c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1902"></a>심각한 오류 C1902
프로그램 데이터베이스 관리자 일치 하지 않습니다. 설치를 확인 하십시오  
  
프로그램 데이터베이스 파일 (.pdb) 집니다의 최신 버전을 사용 하 여 만들어진*XXX*컴파일러 시스템에서 찾은 것 보다는.dll입니다. 이 오류는 일반적으로 mspdbsrv.exe 또는 mspdbcore.dll 누락 되었거나이 서로 다른 버전을 집니다 보다 나타냅니다*XXX*.dll입니다. (의 *XXX* 자리 표시자는 집니다에*XXX*각 제품 릴리스와.dll 파일 이름 변경 합니다. 예를 들어, Visual Studio 2015의 파일 이름이 mspdb140.dll.)  
  
일치 하는 버전의 mspdbsrv.exe, mspdbcore.dll, 및 집니다 확인*XXX*.dll 시스템에 설치 됩니다. 버전이 일치 하지 않는 대상 플랫폼에 대 한 컴파일러 및 연결 도구를 포함 하는 디렉터리에 복사 되지가 있는지 확인 합니다. 예를 들어 있습니다 복사 했을 수 파일 설정 하지 않고 명령 프롬프트에서 컴파일러 또는 링크 도구를 호출할 수 있도록는 **경로** 환경 변수가 적절 하 게 합니다.