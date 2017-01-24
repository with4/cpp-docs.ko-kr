---
title: "_fsopen, _wfsopen | Microsoft Docs"
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
  - "_wfsopen"
  - "_fsopen"
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
  - "wfsopen"
  - "fsopen"
  - "tfsopen"
  - "_tfsopen"
  - "_wfsopen"
  - "_fsopen"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fsopen 함수"
  - "_tfsopen 함수"
  - "_wfsopen 함수"
  - "파일 공유[C++]"
  - "파일[C++], 열기"
  - "fsopen 함수"
  - "파일 열기, 스트림"
  - "tfsopen 함수"
  - "wfsopen 함수"
ms.assetid: 5e4502ab-48a9-4bee-a263-ebac8d638dec
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fsopen, _wfsopen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 공유를 사용한 스트림을 엽니다.  
  
## 구문  
  
```  
FILE *_fsopen(   
   const char *filename,  
   const char *mode,  
   int shflag   
);  
FILE *_wfsopen(   
   const wchar_t *filename,  
   const wchar_t *mode,  
   int shflag   
);  
```  
  
#### 매개 변수  
 `filename`  
 열 파일의 이름입니다.  
  
 `mode`  
 허용되는 액세스 형식입니다.  
  
 `shflag`  
 허용되는 공유 유형입니다.  
  
## 반환 값  
 각 함수는 스트림에 대한 포인터를 반환합니다.  null 포인터 값은 오류를 나타냅니다.  `filename` 또는 `mode`가 `NULL`이거나 빈 문자열인 경우 이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)의 설명대로 잘못된 매개 변수 처리기를 호출합니다.  계속해서 실행하도록 허용된 경우, 이러한 함수는 `NULL`를 반환하고 `errno`를 `EINVAL`로 설정합니다.  
  
 이 오류 및 다른 오류 코드에 대한 자세한 내용은 [\_doserrno, errno, \_sys\_errlist 및 \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)을 참조하세요.  
  
## 설명  
 `_fsopen` 함수는 `filename`에서 스트림으로 지정된 파일을 열고 모드 및 `shflag` 인수에 정의된 대로 후속 공유 읽기 또는 쓰기를 위해 파일을 준비합니다.  `_wfsopen`은 와이드 문자 버전의 `_fsopen`이며, `_wfsopen`에 대한 `filename` 및 `mode` 인수는 와이드 문자열입니다.  그렇지 않으면 `_wfsopen`과 `_fsopen`이 동일하게 작동합니다.  
  
 문자열 `mode`는 다음 표에 나온 것과 같이 파일에 대해 요청된 액세스 형식을 지정합니다.  
  
|용어|정의|  
|--------|--------|  
|`"r"`|읽기 위해 엽니다.  파일이 없거나 찾을 수 없는 경우 `_fsopen` 호출이 실패합니다.|  
|`"w"`|쓰기 위해 빈 파일을 엽니다.  지정한 파일이 있으면 이 파일의 내용은 삭제됩니다.|  
|`"a"`|파일 끝에 쓰기\(추가\) 위해 엽니다. 파일이 존재하지 않는 경우 먼저 파일을 만듭니다.|  
|`"r+"`|읽고 쓰기 위해 엽니다.  파일이 있어야 합니다.|  
|`"w+"`|읽고 쓰기 위해 빈 파일을 엽니다.  지정한 파일이 있으면 이 파일의 내용은 삭제됩니다.|  
|`"a+"`|읽기 및 추가를 위해 엽니다. 파일이 존재하지 않는 경우 먼저 파일을 만듭니다.|  
  
 `"w"` 및 `"w+"` 형식은 기존 파일을 삭제할 수 있으므로 이 형식을 사용할 때는 주의합니다.  
  
 파일이 `"a"` 또는 `"a+"` 액세스 형식으로 열려 있으면 모든 쓰기 작업이 파일 끝에서 발생합니다.  `fseek` 또는 `rewind`를 사용하여 파일 포인터의 위치를 변경할 수 있지만, 파일 포인터는 쓰기 작업을 수행하기 전에 항상 파일 끝으로 다시 이동합니다.  따라서 기존 데이터를 덮어쓸 수 없습니다.  `"r+"`, `"w+"` 또는 `"a+"` 액세스 형식을 지정한 경우 읽기와 쓰기가 모두 허용됩니다. 즉, 파일이 업데이트용으로 열립니다.  그러나 읽기와 쓰기를 전환할 때는 먼저 [fsetpos](../../c-runtime-library/reference/fsetpos.md), [fseek](../../c-runtime-library/reference/fseek-fseeki64.md) 또는 [rewind](../../c-runtime-library/reference/rewind.md) 작업이 있어야 합니다.  원하는 경우 `fsetpos` 또는 `fseek` 작업에 대한 현재 위치를 지정할 수 있습니다.  위의 값 외에도, 다음 문자 중 하나를 `mode`에 포함하여 새 줄 및 파일 관리에 대해 변환 모드를 지정할 수 있습니다.  
  
|용어|정의|  
|--------|--------|  
|`t`|파일을 텍스트\(변환됨\) 모드에서 엽니다.  이 모드에서는 CR\-LF\(캐리지 리턴 줄 바꿈\) 조합은 입력 시 단일 LF\(줄 바꿈\)로 변환되고, LF 문자는 출력 시 CR\-LF 조합으로 변환됩니다.  또한 CTRL\+Z는 입력 시 파일 끝 문자로 변환됩니다.  읽기용으로나 읽기\/쓰기용으로 열려 있는 파일에서 `_fsopen`는 파일 끝에 CTRL\+Z가 있는지 확인하고 가능한 경우 이를 제거합니다.  이렇게 처리되는 이유는 `fseek` 및 `ftell`을 사용하여 CTRL\+Z로 끝나는 파일 내에서 이동하면 `fseek`가 파일 끝 부분에서 제대로 동작하지 않을 수 있기 때문입니다.|  
|`b`|이진\(변환되지 않은\) 모드에서 파일을 엽니다. 위에서 설명한 변환은 표시되지 않습니다.|  
|`S`|캐싱이 디스크에서 순차적 액세스를 위해 최적화되며 이에 제한되지 않습니다.|  
|`R`|캐싱이 디스크에서 임의 액세스를 위해 최적화되며 이에 제한되지 않습니다.|  
|`T`|파일을 임시 파일로 지정합니다.  가능하면 디스크에 플러시되지 않습니다.|  
|`D`|파일을 임시 파일로 지정합니다.  마지막 파일 포인터를 닫을 때 삭제됩니다.|  
  
 `mode`에 `t` 또는 `b`가 지정되지 않은 경우, 변환 모드는 기본 모드 변수 `_fmode`로 정의됩니다.  `t` 또는 `b`가 인수에 접두어로 추가되면 이 함수는 실행되지 못하고 `NULL`을 반환합니다.  텍스트 모드와 이진 모드에 대한 자세한 내용은 [텍스트 및 이진 모드 파일 I\/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)를 참조하세요.  
  
 인수 `shflag`는 Share.h에 정의된 다음 매니페스트 상수 중 하나로 구성된 상수 식입니다.  
  
|용어|정의|  
|--------|--------|  
|`_SH_COMPAT`|16비트 응용 프로그램에 대한 호환성 모드를 설정합니다.|  
|`_SH_DENYNO`|읽기 및 쓰기 권한을 허용합니다.|  
|`_SH_DENYRD`|파일에 대한 읽기 권한을 거부합니다.|  
|`_SH_DENYRW`|파일에 대한 읽기 및 쓰기 권한을 거부합니다.|  
|`_SH_DENYWR`|파일에 대한 쓰기 권한을 거부합니다.|  
  
### 제네릭 텍스트 라우팅 매핑  
  
|Tchar.h 루틴|\_UNICODE 및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|--------------------------------|----------------|-------------------|  
|`_tfsopen`|`_fsopen`|`_fsopen`|`_wfsopen`|  
  
## 요구 사항  
  
|함수|필수 헤더|선택적 헤더|  
|--------|-----------|------------|  
|`_fsopen`|\<stdio.h\>|\<share.h\><br /><br /> `shflag` 매개 변수에 대한 매니페스트 상수입니다.|  
|`_wfsopen`|\<stdio.h\> 또는 \<wchar.h\>|\<share.h\><br /><br /> `shflag` 매개 변수에 대한 매니페스트 상수입니다.|  
  
## 예제  
  
```  
// crt_fsopen.c  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <share.h>  
  
int main( void )  
{  
   FILE *stream;  
  
   // Open output file for writing. Using _fsopen allows us to  
   // ensure that no one else writes to the file while we are  
   // writing to it.  
    //  
   if( (stream = _fsopen( "outfile", "wt", _SH_DENYWR )) != NULL )  
   {  
      fprintf( stream, "No one else in the network can write "  
                       "to this file until we are done.\n" );  
      fclose( stream );  
   }  
   // Now others can write to the file while we read it.  
   system( "type outfile" );  
}  
```  
  
  **완료될 때까지 네트워크의 다른 사람이 이 파일에 쓸 수 없습니다.**   
## 해당 .NET Framework 항목  
  
-   [System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx)  
  
-   <xref:System.IO.FileStream.%23ctor%2A>  
  
## 참고 항목  
 [스트림 I\/O](../../c-runtime-library/stream-i-o.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_fdopen, \_wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [\_fileno](../../c-runtime-library/reference/fileno.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_setmode](../../c-runtime-library/reference/setmode.md)   
 [\_sopen, \_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)