---
title: "심각한 오류 C1084 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1084"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1084"
ms.assetid: b2f273ef-3a14-4d5f-8ce0-7a11a0388fe6
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 심각한 오류 C1084
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

다음 파일 형식 파일을 읽을 수 없습니다. 'file': message  
  
 이 오류는 일반적으로 컴파일러에서 수행한 내부 시스템 API 호출 실패의 결과입니다.  이 오류 발생 시 표시되는 메시지는 일반적으로 [\_wcserror\_s](../../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) 또는 [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351.aspx)에서 생성합니다.  
  
 다음 단계를 수행하면 C1084 오류를 해결하는 데 도움이 될 수 있습니다.  
  
-   지정한 파일이 있는지 확인합니다.  
  
-   지정한 파일에 액세스하는 데 적절한 권한이 설정되어 있는지 확인합니다.  
  
-   명령줄 구문이 [컴파일러 명령줄 구문](../../build/reference/compiler-command-line-syntax.md) 아래 설명된 규칙을 준수하는지 확인합니다.  
  
-   환경 변수 **TMP** 및 **TEMP**와 이러한 환경 변수가 참조하는 디렉터리에 액세스할 수 있는 권한이 적절하게 설정되어 있는지 확인합니다.  또한 **TMP** 및 **TEMP** 환경 변수에서 참조하는 드라이브에 충분한 여유 공간이 있는지도 확인합니다.  
  
-   "잘못된 파일 번호"라는 메시지가 표시되면 백그라운드에서 컴파일하는 동안 지정한 파일이 전경에서 닫혀 있을 수 있습니다.  
  
 위의 진단을 수행한 후 클린 빌드를 수행합니다.