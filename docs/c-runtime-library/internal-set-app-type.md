---
title: "__set_app_type | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "__set_app_type"
  - "_set_app_type"
apilocation: 
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__set_app_type"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__set_app_type"
ms.assetid: f0ac0f4d-70e6-4e96-9e43-eb9d1515490c
caps.latest.revision: 2
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __set_app_type
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 디버그 형식을 설정합니다.  
  
## 구문  
  
```cpp  
void __set_app_type (  
   int at  
   )  
```  
  
#### 매개 변수  
 `at`  
 응용 프로그램 형식을 나타내는 값입니다.  가능한 값은 다음과 같습니다.  
  
|값|설명|  
|-------|--------|  
|알려지지 않은 응용프로그램 입니다.|알 수 없는 응용 프로그램 종류입니다.|  
|CONSOLE|\(명령줄\) 콘솔 응용 프로그램입니다.|  
|\_GUI\_APP|\(Windows\)GUI 응용 프로그램|  
  
## 설명  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|\_\_set\_app\_type|internal.h|