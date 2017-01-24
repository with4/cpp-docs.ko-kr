---
title: "코드 페이지 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.international"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "ANSI[C++], 코드 페이지"
  - "문자 집합[C++], 코드 페이지"
  - "코드 페이지[C++], 형식"
  - "로캘 코드 페이지[C++]"
  - "지역화[C++], 코드 페이지"
  - "멀티바이트 코드 페이지[C++]"
  - "시스템 기본값 코드 페이지"
ms.assetid: 4a26fc42-185a-4add-98bf-a7b314ae6186
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 코드 페이지
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`code page` 는 숫자, 문장 부호 및 기타 문자를 포함할 수 있는 문자 집합입니다.  언어와 로캘마다 다른 코드 페이지를 사용할 수 있습니다.  예를 들어, ANSI 코드 페이지 1252는 미국 영어와 대부분의 유럽 언어에 사용되고, OEM 코드 페이지 932는 일본어 간지에 사용됩니다.  
  
 코드 페이지는 문자를 싱글 바이트 값 또는 멀티 바이트 값으로 매핑하는 표로 나타낼 수 있습니다.  여러 코드 페이지는 ASCII 문자 0x00 – 0x7F 범위의 문자 집합을 공유합니다.  
  
 Microsoft 런타임 라이브러리는 다음 유형의 코드 페이지를 사용합니다.  
  
-   시스템 기본값 ANSI 코드 페이지  기본적으로 시작할 때 실행 시간 시스템은 멀티 바이트 코드 페이지를 자동으로 운영 체제로부터 가져온 시스템 기본 ANSI 코드 페이지로 설정합니다.  호출:  
  
    ```  
    setlocale ( LC_ALL, "" );  
    ```  
  
     또한 시스템 기본 ANSI 코드 페이지로 로캘을 설정합니다.  
  
-   로캘 코드 페이지  다양한 런타임 루틴의 동작은 현재 로캘 코드 페이지를 포함하는 로캘 설정에 따라 달라집니다. \(자세한 내용은 [Locale\-Dependent Routines](../c-runtime-library/locale.md)을 참조하십시오.\) 기본적으로 Microsoft 런타임 라이브러리의 모든 로캘 종속 루틴은 C 로캘에 해당하는 코드 페이지를 사용합니다.  [setlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)을 호출하여 런타임에 로캘 코드 페이지를 변경하거나 질의할 수 있습니다.  
  
-   멀티바이트 코드 페이지  런타임 라이브러리에서 멀티 바이트 문자 루틴 동작의 대부분은 현재 멀티 바이트 코드 페이지 설정에 따라 달라집니다.  기본적으로 이러한 루틴은 시스템 기본 ANSI 코드 페이지를 사용합니다.  [\_getmbcp](../c-runtime-library/reference/getmbcp.md) 및 [\_setmbcp](../c-runtime-library/reference/setmbcp.md) 각각을 사용하여 런타임 시 멀티 바이트 코드 페이지를 변경하거나 질의할 수 있습니다.  
  
-   "C" 로캘은 ANSI에 의해 C 프로그램이 전통적으로 실행해 온 로캘로 정의됩니다.  "C" 로캘 코드 페이지\("C" 코드 페이지\)는 ASCII 문자 집합에 해당합니다.  예를 들어, "C" 로캘에서 `islower`는 0x61 – 0x7A 사이의 값에만 true를 반환합니다.  다른 로캘에서 `islower`는 이것들 뿐만 아니라 그 로캘에 의해 정의된 다른 값에도 true를 반환합니다.  
  
## 참고 항목  
 [국제화](../c-runtime-library/internationalization.md)   
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)