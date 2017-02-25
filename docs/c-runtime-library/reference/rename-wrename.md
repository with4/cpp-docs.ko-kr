---
title: "rename, _wrename | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "rename"
  - "_wrename"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wrename"
  - "_trename"
  - "Rename"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_trename 함수"
  - "_wrename 함수"
  - "디렉터리[C++], 이름 바꾸기"
  - "파일[C++], 이름 바꾸기"
  - "이름[C++], 디렉터리 변경"
  - "이름[C++], 파일 변경"
  - "rename 함수"
  - "디렉터리 이름 바꾸기"
  - "파일 이름 바꾸기"
  - "trename 함수"
  - "wrename 함수"
ms.assetid: 9f0a6103-26a2-4dda-b14b-79a48946266a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# rename, _wrename
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일 또는 디렉토리의 이름바꾸기.  
  
## 구문  
  
```  
  
      int rename(  
   const char *oldname,  
   const char *newname   
);  
int _wrename(  
   const wchar_t *oldname,  
   const wchar_t *newname   
);  
```  
  
#### 매개 변수  
 *기존 이름*  
 이전 이름에 대한 포인터입니다.  
  
 *새 이름*  
 새 이름에 대한 포인터입니다.  
  
## 반환 값  
 만일 이것이 성공한다면, 이들의 각 함수는 0을 반환합니다.  오류에서, 이 함수는 0 이외의 값을 반한하고 다음 값들 중 하나를 `errno` 로 설정합니다.  
  
 `EACCES`  
 *새 이름* 으로 지정된 파일이나 디렉터리는 이미 존재 하거나 만들 수 없습니다 \(잘못 된 경로\); *기존 이름* 는 디렉터리이고 *newname* 은 다른 경로를 지정 합니다.  
  
 `ENOENT`  
 *기존이름* 으로 지정 된 경로나 파일을 찾을 수 없습니다.  
  
 `EINVAL`  
 이름이 잘못된 문자를 포함하는 경우.  
  
 다른 가능한 반환값에 대해 [doserrno, \_errno, syserrlist, and \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 를 참조하세요.  
  
## 설명  
 **이름 바꾸기** 함수는 지정된 파일 또는 디렉토리의 *기존 이름* 을 주어진 *새 이름* 으로 바꿉니다.  오래된 이름은 기존 파일이나 디렉터리의 경로 이어야 합니다.  새 이름은 기존 파일 또는 디렉터리의 이름이면 안됩니다.  **이름 바꾸기** 를 사용하여 *새 이름* 인수에 다른 경로를 입력하여 다른 디렉터리 또는 장치로부터 다른곳으로 파일을 이동합니다.  그러나, **이름 바꾸기** 를 사용하여 디렉터리를 이동할 수 없습니다.  디렉터리 이름은 바꿀 수 있지만 이동될 수 않습니다.  
  
 `_wrename` 는 **\_rename** 의 와이드 문자 버전이며, `_wrename` 는 와이드 문자 문자열입니다.  그렇지 않으면 `_wrename` 과 **\_rename** 은 동일하게 작동합니다.  
  
### 제네릭 텍스트 라우팅 매핑  
  
|TCHAR.H 루틴|\_UNICODE &및 \_MBCS 정의되지 않음|\_MBCS 정의됨|\_UNICODE 정의됨|  
|----------------|---------------------------------|----------------|-------------------|  
|`_trename`|**이름 바꾸기**|**이름 바꾸기**|`_wrename`|  
  
## 요구 사항  
  
|루틴|필수 헤더|  
|--------|-----------|  
|**이름 바꾸기**|\<io.h\> 또는 \<stdio.h\>|  
|`_wrename`|\<stdio.h\> 또는 \<wchar.h\>|  
  
 호환성에 대한 자세한 내용은 소개 단원의 [호환성](../../c-runtime-library/compatibility.md) 부분을 참조하십시오.  
  
## 라이브러리  
 모든 버전의 [C 런타임 라이브러리](../../c-runtime-library/crt-library-features.md)입니다.  
  
## 예제  
  
```  
// crt_renamer.c  
/* This program attempts to rename a file named  
 * CRT_RENAMER.OBJ to CRT_RENAMER.JBO. For this operation  
 * to succeed, a file named CRT_RENAMER.OBJ must exist and  
 * a file named CRT_RENAMER.JBO must not exist.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   int  result;  
   char old[] = "CRT_RENAMER.OBJ", new[] = "CRT_RENAMER.JBO";  
  
   /* Attempt to rename file: */  
   result = rename( old, new );  
   if( result != 0 )  
      printf( "Could not rename '%s'\n", old );  
   else  
      printf( "File '%s' renamed to '%s'\n", old, new );  
}  
```  
  
## Output  
  
```  
File 'CRT_RENAMER.OBJ' renamed to 'CRT_RENAMER.JBO'  
```  
  
## 해당 .NET Framework 항목  
 [System::IO::File::Move](https://msdn.microsoft.com/en-us/library/system.io.file.move.aspx)  
  
## 참고 항목  
 [파일 처리](../../c-runtime-library/file-handling.md)