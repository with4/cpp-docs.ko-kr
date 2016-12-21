---
title: "_commit | Microsoft Docs"
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
  - "_commit"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_commit"
  - "commit"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_commit 함수"
  - "commit 함수"
  - "디스크에 파일 커밋"
  - "파일[C++], 플러시"
  - "디스크에 파일 플러시"
ms.assetid: d0c74d3a-4f2d-4fb0-b140-2d687db3d233
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _commit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일을 직접 디스크에 플러시합니다.  
  
## 구문  
  
```  
int _commit(   
   int fd   
);  
```  
  
#### 매개 변수  
 `fd`  
 열려 있는 파일을 나타내는 파일 기술자입니다.  
  
## 반환 값  
 만일 파일이 성공적으로 디스크에 플러시된 경우, `_commit` 은 0을 반환합니다.  반환값 \-1 은 오류를 나타냅니다.  
  
## 설명  
 `_commit` 함수는 디스크에 `fd` 와 연관된 파일을 쓰기위해 운영체제에 영향을 미칩니다.  이 호출은 운영체제의 재량이 아닌, 지정된 파일이 즉시 플러시되도록 합니다.  
  
 여기 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md) 에 설명된 대로 `fd` 이 잘못된 파일 기술자인 경우 잘못된 매개 변수 처리기가 호출됩니다.  만일 실행이 계속된다면, 이 함수는 \-1을 반환하고 `errno` 은 `EBADF`으로 설정됩니다.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_commit`|\<io.h\>|\<\<errno.h\>\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 참고 항목  
 [하위 수준 I\/O](../../c-runtime-library/low-level-i-o.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_read](../../c-runtime-library/reference/read.md)   
 [\_write](../../c-runtime-library/reference/write.md)