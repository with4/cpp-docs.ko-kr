---
title: "형식 검사(CRT) | Microsoft Docs"
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
  - "c.types"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "형식 검사"
  - "형식 검사"
  - "가변 인수 함수"
ms.assetid: 1ba7590b-d1c0-4636-b6a0-e231395abdad
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 형식 검사(CRT)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

컴파일러는 아래와 같이 가변 개수의 인수를 받는 함수에서 제한된 형식 검사를 수행합니다.  
  
|함수 호출|인수 형식 검사|  
|-----------|--------------|  
|`_cprintf_s`, `_cscanf_s`, `printf_s`, `scanf_s`|첫 번째 인수 \(string 형식\)|  
|`fprintf_s`, `fscanf_s`, `sprintf_s`, `sscanf_s`|처음 두 개의 인수 \(파일 또는 버퍼 및 형식 문자열\)|  
|`_snprintf_s`|처음 세 인수 \(파일 또는 버퍼, 개수 및 형식 문자열\)|  
|`_open`|처음 두 개의 인수 \(경로 및 `_open` 플래그\)|  
|`_sopen_s`|처음 세 인수 \(경로, `_open` 플래그 및 공유 모드\)|  
|`_execl`, `_execle`, `_execlp`, `_execlpe`|처음 두 개의 인수 \(경로 첫 번째 인수 포인터\)|  
|`_spawnl`, `_spawnle`, `_spawnlp`, `_spawnlpe`|처음 세 인수 \(모드 플래그, 경로 및 첫 번째 인수 포인터\)|  
  
 컴파일러는 이러한 함수의 와이드 문자 대응에서 같은 제한된 형식 검사를 수행합니다.  
  
## 참고 항목  
 [CRT 라이브러리 기능](../c-runtime-library/crt-library-features.md)