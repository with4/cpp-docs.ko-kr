---
title: "심각한 오류 C1084 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1084
dev_langs:
- C++
helpviewer_keywords:
- C1084
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 828486ee2d3057c4d9c658defc1477de49b6cd0e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1084"></a>심각한 오류 C1084
다음 파일 형식 파일을 읽을 수 없습니다. 'file': message  
  
 이 오류는 일반적으로 컴파일러에서 수행한 내부 시스템 API 호출 실패의 결과입니다. 이 오류는 발생 표시 되는 메시지에서 생성은 [_wcserror_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) 또는 [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351.aspx)합니다.  
  
 다음 단계를 수행하면 C1084 오류를 해결하는 데 도움이 될 수 있습니다.  
  
-   지정한 파일이 있는지 확인합니다.  
  
-   지정한 파일에 액세스하는 데 적절한 권한이 설정되어 있는지 확인합니다.  
  
-   명령줄 구문 아래 요약 된 규칙을 준수 확인 [컴파일러 명령줄 구문](../../build/reference/compiler-command-line-syntax.md)합니다.  
  
-   환경 변수 설정 되어 있는지 확인 **TMP** 및 **TEMP** 집합 뿐만 아니라 이러한 환경 변수가 참조 하는 디렉터리에 액세스 하려면 적절 한 권한이 올바르게 됩니다. 또한 되어 있는지 확인 하 여 참조 하는 드라이브는 **TMP** 및 **TEMP** 환경 변수에 적절 한 양의 사용 가능한 공간을 포함 합니다.  
  
-   "잘못된 파일 번호"라는 메시지가 표시되면 백그라운드에서 컴파일하는 동안 지정한 파일이 전경에서 닫혀 있을 수 있습니다.  
  
 위의 진단을 수행한 후 클린 빌드를 수행합니다.