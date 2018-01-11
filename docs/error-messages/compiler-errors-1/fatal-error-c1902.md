---
title: "심각한 오류 C1902 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1902
dev_langs: C++
helpviewer_keywords: C1902
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4e5f6c22ea848a49a12cc85508fd80a4cfcb90e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1902"></a>심각한 오류 C1902
프로그램 데이터베이스 관리자 일치 하지 않습니다. 설치를 확인 하십시오  
  
프로그램 데이터베이스 파일 (.pdb) 집니다의 최신 버전을 사용 하 여 만들어진*XXX*컴파일러 시스템에서 찾은 것 보다는.dll입니다. 이 오류는 일반적으로 mspdbsrv.exe 또는 mspdbcore.dll 누락 되었거나이 서로 다른 버전을 집니다 보다 나타냅니다*XXX*.dll입니다. (의 *XXX* 자리 표시자는 집니다에*XXX*각 제품 릴리스와.dll 파일 이름 변경 합니다. 예를 들어, Visual Studio 2015의 파일 이름이 mspdb140.dll.)  
  
일치 하는 버전의 mspdbsrv.exe, mspdbcore.dll, 및 집니다 확인*XXX*.dll 시스템에 설치 됩니다. 버전이 일치 하지 않는 대상 플랫폼에 대 한 컴파일러 및 연결 도구를 포함 하는 디렉터리에 복사 되지가 있는지 확인 합니다. 예를 들어 있습니다 복사 했을 수 파일 설정 하지 않고 명령 프롬프트에서 컴파일러 또는 링크 도구를 호출할 수 있도록는 **경로** 환경 변수가 적절 하 게 합니다.