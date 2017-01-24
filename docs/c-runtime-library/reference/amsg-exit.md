---
title: "_amsg_exit | Microsoft Docs"
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
  - "_amsg_exit"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_amsg_exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_amsg_exit"
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
caps.latest.revision: 2
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _amsg_exit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

지정 된 런타임 오류 메세지를 내보내고 오류 코드 255를 사용하여 응용 프로그램을 종료 합니다.  
  
## 구문  
  
```cpp  
void _amsg_exit (  
   int rterrnum  
   )  
  
```  
  
#### 매개 변수  
 `rterrnum`  
 시스템 정의 런타임 오류 메세지의 ID 번호입니다.  
  
## 설명  
 이 함수에서 런타임 오류 메시지를 내보냅니다. **stderr** 콘솔 응용 프로그램 또는 Windows 응용 프로그램에 대한 메시지에서 메시지 상자를 표시 합니다.  디버그 모드에서 디버거를 종료 하기 전에 호출할 수 있습니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|\_amsg\_exit|internal.h|