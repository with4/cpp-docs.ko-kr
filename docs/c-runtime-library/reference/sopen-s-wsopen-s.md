---
title: "_sopen_s, _wsopen_s | Microsoft Docs"
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
  - "_sopen_s"
  - "_wsopen_s"
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
  - "_sopen_s"
  - "wsopen_s"
  - "_wsopen_s"
  - "sopen_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_sopen_s 함수"
  - "_wsopen_s 함수"
  - "파일[C++], 열기"
  - "파일[C++], 공유"
  - "파일 열기, 공유용"
  - "sopen_s 함수"
  - "wsopen_s 함수"
ms.assetid: 059a0084-d08c-4973-9174-55e391b72aa2
caps.latest.revision: 29
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _sopen_s, _wsopen_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

공유할 파일을 엽니다.  다음 [\_sopen and \_wsopen](../../c-runtime-library/reference/sopen-wsopen.md) 버전에는 [CRT의 보안 기능](../../c-runtime-library/security-features-in-the-crt.md)에서 설명하는 향상된 보안 기능이 있습니다.  
  
## 구문  
  
```  
errno_t _sopen_s(    int* pfh,    const char *filename,    int oflag,    int shflag,    int pmode ); errno_t _wsopen_s(    int* pfh,    const wchar_t *filename,    int oflag,    int shflag,    int pmode, );  
```  
  
#### 매개 변수  
 \[out\] `pfh`  
 파일 핸들 또는 오류 발생 시 \-1  
  
 \[in\] `filename`  
 파일 이름.  
  
 \[in\] `oflag`  
 허용되는 연산의 종류  
  
 \[in\] `shflag`  
 허용되는 공유의 종류  
  
 \[in\] `pmode`  
 권한 설정  
  
## 반환 값  
 0이 아닌 반환 값은 오류를 나타냅니다. 이 경우 `errno`는 다음 값 중 하나로 설정되어 있습니다.  
  
 `EACCES`  
 지정된 경로가 디렉터리거나 파일이 읽기 전용인데 쓰기 위한 열기 작업을 시도했습니다.  
  
 `EEXIST`  
 `_O_CREAT` 및 `_O_EXCL` 플래그를 지정했으나 `filename`이 이미 있습니다.  
  
 `EINVAL`  
 `oflag`, `shflag` 또는 `pmode` 인수가 잘못되었거나 `pfh` 또는 `filename`이 null 포인터입니다.  
  
 `EMFILE`  
 사용 가능한 추가 파일 설명자가 없습니다.  
  
 `ENOENT`  
 파일 또는 경로를 찾을 수 없습니다.  
  
 함수에 잘못된 인수가 전달되면 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명된 대로 잘못된 매개 변수 처리기가 호출됩니다.  계속해서 실행하도록 허용한 경우 `errno`는 `EINVAL`로 설정되고 `EINVAL`이 반환됩니다.  
  
 이러한 반환 코드 및 기타 반환 코드에 대한 자세한 내용은 [errno, \_doserrno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하십시오.  
  
 오류 발생 시 `pfh`를 통해 \-1이 반환됩니다\(`pfh`가 null 포인터가 아닌 경우\).  
  
## 설명  
 `_sopen_s` 함수는 `filename`에서 지정한 파일을 열고 `oflag` 및 `shflag`에서 정의한 대로 공유 읽기 또는 쓰기를 위해 해당 파일을 준비합니다.  `_wsopen_s`는 `_sopen_s`의 와이드 문자 버전이며, `_wsopen_s`에 대한 `filename` 인수는 와이드 문자열입니다.  그렇지 않으면 `_wsopen_s`과 `_sopen_s`이 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tsopen_s`|`_sopen_s`|`_sopen_s`|`_wsopen_s`|  
  
 정수 식 `oflag`는 \<fcntl.h\>에 정의된 매니페스트 상수 한 개 이상을 결합하여 구성됩니다.  상수 두 개 이상이 인수 `oflag`를 구성할 때 이러한 상수는 비트 OR 연산자로 결합됩니다\(  `|` \).  
  
 `_O_APPEND`  
 모든 쓰기 작업 전에 파일 끝으로 파일 포인터의 위치를 변경합니다.  
  
 `_O_BINARY`  
 파일을 이진\(변환되지 않음\) 모드에서 엽니다.  이진 모드에 대한 설명은 [fopen](../../c-runtime-library/reference/fopen-wfopen.md)을 참조하세요.  
  
 `_O_CREAT`  
 파일을 만든 다음 쓰기 위해 엽니다.  `filename`에서 지정한 파일이 있으면 의미가 없습니다.  
  
 `_O_CREAT | _O_SHORT_LIVED`  
 파일을 임시로 만든 다음 가능한 경우 디스크로 플러시하지 않습니다.  
  
 `_O_CREAT | _O_TEMPORARY`  
 파일을 임시로 만듭니다. 마지막 파일 설명자가 닫히면 파일이 삭제됩니다.  
  
 `_O_CREAT | _O_EXCL`  
 `filename`에서 지정한 파일이 있으면 오류 값을 반환합니다.  `_O_CREAT`와 함께 사용하는 경우에만 적용됩니다.  
  
 `_O_NOINHERIT`  
 공유 파일 설명자의 생성을 방지합니다.  
  
 `_O_RANDOM`  
 디스크에서의 임의 액세스를 주로 지정합니다.  
  
 `_O_RDONLY`  
 읽으려는 경우에만 파일을 엽니다.  `_O_RDWR` 또는 `_O_WRONLY`와 함께 지정할 수 없습니다.  
  
 `_O_RDWR`  
 읽고 쓰기 위해 파일을 엽니다.  `_O_RDONLY` 또는 `_O_WRONLY`와 함께 지정할 수 없습니다.  
  
 `_O_SEQUENTIAL`  
 디스크에서의 순차적 액세스를 주로 지정합니다.  
  
 `_O_TEXT`  
 파일을 텍스트\(변환됨\) 모드에서 엽니다.  자세한 내용은 [텍스트 및 이진 모드 파일 I\/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) 및 [fopen](../../c-runtime-library/reference/fopen-wfopen.md)을 참조하세요.  
  
 `_O_TRUNC`  
 파일을 열고 길이가 0이 되도록 자릅니다. 이 파일에는 쓰기 권한이 있어야 합니다.  `_O_RDONLY`와 함께 지정할 수 없습니다.  `_O_CREAT`와 함께 `_O_TRUNC`를 사용하면 기존 파일을 열거나 파일을 만듭니다.  
  
> [!NOTE]
>  `_O_TRUNC` 플래그는 지정된 파일의 내용을 제거합니다.  
  
 `_O_WRONLY`  
 쓰려는 경우에만 파일을 엽니다.  `_O_RDONLY` 또는 `_O_RDWR`와 함께 지정할 수 없습니다.  
  
 `_O_U16TEXT`  
 유니코드 UTF\-16 모드에서 파일을 엽니다.  
  
 `_O_U8TEXT`  
 유니코드 UTF\-8 모드에서 파일을 엽니다.  
  
 `_O_WTEXT`  
 유니코드 모드에서 파일을 엽니다.  
  
 파일 액세스 모드를 지정하려면 `_O_RDONLY`, `_O_RDWR` 또는 `_O_WRONLY`를 지정해야 합니다.  액세스 모드의 기본값은 없습니다.  
  
 `_O_WTEXT`, `_O_U8TEXT` 또는 `_O_U16TEXT`를 사용하여 파일을 유니코드 모드에서 열면 입력 함수는 해당 파일에서 읽은 데이터를 UTF\-16 데이터로 변환하고 `wchar_t` 형식으로 저장합니다.  유니코드 모드에서 연 파일에 쓰는 함수는 UTF\-16 데이터가 포함된 버퍼가 `wchar_t` 형식으로 저장되는 것으로 예상합니다.  이 파일이 UTF\-8로 인코딩되면 UTF\-16 데이터는 쓸 때 UTF\-8로 변환되고 이 파일의 UTF\-8로 인코딩된 내용은 읽을 때 UTF\-16으로 변환됩니다.  유니코드 모드에서 홀수 바이트를 읽거나 쓰려고 하면 매개 변수 유효성 검사 오류가 발생합니다.  프로그램에 UTF\-8로 저장된 데이터를 읽거나 쓰려는 경우 유니코드 모드 대신 텍스트 또는 이진 파일 모드를 사용합니다.  필수 인코딩은 사용자가 변환해야 합니다.  
  
 `_sopen_s`를 `_O_WRONLY | _O_APPEND`\(추가 모드\) 및 `_O_WTEXT`, `_O_U16TEXT` 또는 `_O_U8TEXT`로 호출하면 먼저 읽고 쓰기 위해 파일을 열고 BOM을 읽은 다음 쓰기를 위해서만 파일을 다시 엽니다.  읽고 쓰기 위해 파일을 여는데 실패하면 쓰기 위해서만 파일을 열고 유니코드 모드 설정에 기본값을 사용합니다.  
  
 `shflag` 인수는 \<share.h\>에 정의된 다음 매니페스트 상수 중 하나로 구성된 상수 식입니다.  
  
 `_SH_DENYRW`  
 파일에 대한 읽기 및 쓰기 액세스를 거부합니다.  
  
 `_SH_DENYWR`  
 파일에 대한 쓰기 액세스를 거부합니다.  
  
 `_SH_DENYRD`  
 파일에 대한 읽기 액세스를 거부합니다.  
  
 `_SH_DENYNO`  
 읽기 및 쓰기 액세스 권한을 허용합니다.  
  
 `pmode` 인수는 `_sopen`과 달리 항상 필요합니다.  `_O_CREAT`를 지정했는데 해당 파일이 없으면 `pmode`는 새 파일이 처음 닫힐 때 설정되는 파일의 권한 설정을 지정합니다.  그렇지 않으면 `pmode`가 무시됩니다.  `pmode`는 \<sys\\stat.h\>에 정의된 매니페스트 상수 `_S_IWRITE` 및 `_S_IREAD` 둘 다 또는 둘 중 하나가 포함된 정수 식입니다.  두 상수가 지정된 경우 비트 OR 연산자를 사용하여 결합합니다.  `pmode`의 의미는 다음과 같습니다.  
  
 `_S_IWRITE`  
 쓰기를 허용합니다.  
  
 `_S_IREAD`  
 읽기를 허용합니다.  
  
 `_S_IREAD | _S_IWRITE`  
 읽기 및 쓰기를 허용합니다.  
  
 쓰기 권한이 부여되지 않은 경우 파일은 읽기 전용입니다.  Windows 운영 체제에서 모든 파일을 읽을 수 있지만 쓰기 전용 권한을 부여할 수는 없습니다.  따라서 `_S_IWRITE` 및 `_S_IREAD | _S_IWRITE` 모드는 동일합니다.  
  
 권한을 설정하기 전에 `_sopen_s`는 현재 파일 권한 마스크를 `pmode`에 적용합니다.  [\_umask](../../c-runtime-library/reference/umask.md)를 참조하세요.  
  
## 요구 사항  
  
|루틴|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_sopen_s`|\<io.h\>|\<fcntl.h\>, \<sys\\types.h\>, \<sys\\stat.h\>, \<share.h\>|  
|`_wsopen_s`|\<io.h\> 또는 \<wchar.h\>|\<fcntl.h\>, \<sys\/types.h\>, \<sys\/stat.h\>, \<share.h\>|  
  
 `_sopen_s` 및 `_wsopen_s`는 Microsoft 확장입니다.  호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하십시오.  
  
## 예제  
 [\_locking](../../c-runtime-library/reference/locking.md)에 대한 예를 참조하세요.  
  
## 참고 항목  
 [하위 수준 I\/O](../../c-runtime-library/low-level-i-o.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_fsopen, \_wfsopen](../../c-runtime-library/reference/fsopen-wfsopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)