---
title: "__p__fmode | Microsoft Docs"
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
  - "__p__fmode"
apilocation: 
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "__p__fmode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__p__fmode"
ms.assetid: 1daa1394-81eb-43aa-a71b-4cc6acf3207b
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __p__fmode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

파일 I\/O 연산자에 대한 기본 *file translation mode* 를 지정하는 `_fmode` 전역 변수를 가르키는 포인터 입니다.  
  
## 구문  
  
```cpp  
int* __p__fmode(  
   );  
```  
  
## 반환 값  
 `_fmode` 전역 변수에 대한 포인터 입니다.  
  
## 설명  
 `__p__fmode`는 함수 내부 에서만 사용 되며 사용자 코드에서 호출할 수 없습니다.  
  
 파일 변환 모드는 [\_open](../c-runtime-library/reference/open-wopen.md) 및 [\_pipe](../c-runtime-library/reference/pipe.md) I\/O 연산자에 대해 `binary` 또는 `text` 변환을 지정합니다.  자세한 내용은 [\_fmode](../c-runtime-library/fmode.md)을 참조하십시오.  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|\_\_p\_\_fmode|stdlib.h|