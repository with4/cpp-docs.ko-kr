---
title: "errno 상수 | Microsoft Docs"
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
  - "ENOEXEC"
  - "ENOMEM"
  - "E2BIG"
  - "STRUNCATE"
  - "ENOENT"
  - "EMFILE"
  - "EBADF"
  - "EDEADLOCK"
  - "EXDEV"
  - "EILSEQ"
  - "EINVAL"
  - "EDOM"
  - "EACCES"
  - "ERANGE"
  - "ENOSPC"
  - "EAGAIN"
  - "EEXIST"
  - "ECHILD"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "E2BIG 상수"
  - "EACCES 상수"
  - "EAGAIN 상수"
  - "EBADF 상수"
  - "ECHILD 상수"
  - "EDEADLOCK 상수"
  - "EDOM 상수"
  - "EEXIST 상수"
  - "EILSEQ 상수"
  - "EINVAL 상수"
  - "EMFILE 상수"
  - "ENOENT 상수"
  - "ENOEXEC 상수"
  - "ENOMEM 상수"
  - "ENOSPC 상수"
  - "ERANGE 상수"
  - "errno 상수"
  - "EXDEV 상수"
  - "STRUNCATE 상수"
ms.assetid: 47089258-d5a5-4cd8-b193-223894dea0cf
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# errno 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## 구문  
  
```  
  
#include <errno.h>  
```  
  
## 설명  
 **errno**값은 다양한 오류 조건의 이벤트에서 [errno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)에 지정된 상수입니다.  
  
 ERRNO.H는 **errno** 값의 정의를 포함합니다.  그러나 ERRNO.H에 주어진 모든 정의가 32비트 Windows 운영 체제에서 사용되는 것은 아닙니다.  ERRNO.H 안의 값 일부는 UNIX 계열 운영 체제와의 호환성을 유지하기 위해 존재합니다.  
  
 32비트 Windows 운영 체제에서 **errno** 값은 XENIX 시스템 내 **errno** 값의 부분집합입니다.  따라서, 해당 **errno** 값은 Windows 운영 체제로부터의 시스템 호출에 의해 반환되는 실제 오류 코드와 반드시 동일할 필요가 없습니다.  실제 운영 체제의 오류 코드에 액세스하려면, 이 값을 포함하고 있는 [\_doserrno](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 변수를 사용하십시오.  
  
 다음 **errno** 값을 사용할 수 있습니다.  
  
 **ECHILD**  
 생성된 프로세스가 없습니다.  
  
 **EAGAIN**  
 더 이상 프로세스가 없습니다.  더 이상 프로세스 슬롯이 없거나 충분한 메모리가 없거나, 최대 중첩 수준에 도달했기 때문에 새 프로세스를 만들려는 시도가 실패하였습니다.  
  
 **E2BIG**  
 인수 목록이 너무 깁니다.  
  
 **EACCES**  
 사용 권한이 거부되었습니다.  파일의 권한 설정이 지정된 액세스를 허용하지 않습니다.  이 오류는 파일의 속성과 호환되지 않는 방법을 통해서 파일\(또는 일부 경우 디렉터리\)에 대한 액세스 시도가 일어났다는 것을 의미합니다.  
  
 예를 들어, 열려 있지 않은 파일로부터 읽거나, 읽기 전용 파일을 쓰기 위해서 열거나, 파일 대신 디렉터리를 열려는 시도가 있는 경우 오류가 발생할 수 있습니다.  MS\-DOS 운영 체제 버전 3.0 및 그 이후 버전에서,  **EACCES**는 잠금 또는 공유 위반을 나타낼 수도 있습니다.  
  
 파일 또는 디렉터리 이름 바꾸기 또는 기존 디렉터리를 제거하는 시도에서 오류가 발생할 수도 있습니다.  
  
 **EBADF**  
 잘못된 파일 번호입니다.  가능한 원인은 두 가지입니다. 1\) 지정한 파일 기술자가 잘못된 값이거나 파일의 열기를 참조하지 않습니다. 2\) 읽기 전용으로 열린 파일 또는 장치에 쓰려는 시도가 발생한 경우  
  
 **EDEADLOCK**  
 리소스 교착 상태가 발생합니다.  수학 함수에 대한 인수는 함수의 도메인에 포함되지 않습니다.  
  
 **EDOM**  
 수학 인수입니다.  
  
 **EEXIST**  
 파일이 존재합니다.  이미 존재하는 파일을 만드려는 시도가 일어났습니다.  예를 들어, **\_O\_CREAT** 및 **\_O\_EXCL** 플래그가 **\_open** 호출에서 지정됩니다. 하지만 명명된 된 파일이 이미 있습니다.  
  
 **EILSEQ**  
 잘못된 바이트의 시퀀스\(예를 들어, MBCS 문자열\)입니다.  
  
 **EINVAL**  
 잘못된 인수입니다.  함수의 인수 중 하나에 잘못된 값이 지정되었습니다.  예를 들어, 파일 포인터의 위치를 지정할 때 \(**fseek**의 호출에 의해\) 주어진 값이 파일의 시작보다 앞인 경우입니다.  
  
 **EMFILE**  
 너무 많은 파일을 엽니다.  더 이상의 사용 가능한 파일 기술자가 없으므로, 더 이상 파일을 열 수 없습니다.  
  
 **ENOENT**  
 그러한 파일 또는 디렉터리가 없습니다.  지정된 파일 또는 디렉터리가 존재하지 않거나 찾을 수 없습니다.  지정한 파일이 존재하지 않거나 경로가 존재하는 디렉터리를 지정하지 않을 때마다 이 메시지가 나타날 수 있습니다.  
  
 **ENOEXEC**  
 Exec 형식 오류입니다.  실행 파일이 아니거나 잘못된 형식의 실행 파일을 실행하려는 시도가 있었습니다.  
  
 **ENOMEM**  
 코어가 부족합니다.  시도된 연산자를 위한 메모리가 부족합니다.  예를 들어, 자식 프로세스를 실행하기에 메모리가 부족하거나 **\_getcwd**의 할당 요청 호출이 만족되지 않은 경우 이 메시지가 나타날 수 있습니다.  
  
 **ENOSPC**  
 장치에 남은 공간이 없습니다.  장치에 더 이상 쓸 공간이 없습니다. \(예를 들어, 디스크가 꽉 찬 경우\)  
  
 **ERANGE**  
 결과가 너무 큽니다.  수학 함수의 인수가 너무 커서 결과의 일부 또는 전체가 손실되었습니다.  이 오류는 인수가 예상보다 클 때 다른 함수에서도 발생할 수 있습니다\(예를 들어, **\_getcwd**의 *buffer* 인수가 예상보다 길 경우\).  
  
 **EXDEV**  
 장치 간 연결입니다.  파일을 다른 장치로 이동하려는 시도가 있었습니다\(**rename** 함수를 이용해서\).  
  
 **STRUNCATE**  
 문자열 복사 또는 연결에 의해 절단된 문자열이 생성되었습니다.  [\_TRUNCATE](../c-runtime-library/truncate.md)를 참조하십시오.  
  
 다음 값은 Posix 호환을 위해 지원됩니다.  이들은 비 Posix 시스템에서 필요한 값입니다.  
  
```  
#define E2BIG [argument list too long]  
#define EACCES [permission denied]  
#define EADDRINUSE [address in use]  
#define EADDRNOTAVAIL [address not available]  
#define EAFNOSUPPORT [address family not supported]  
#define EAGAIN [resource unavailable try again]  
#define EALREADY [connection already in progress]  
#define EBADF [bad file descriptor]  
#define EBADMSG [bad message]  
#define EBUSY [device or resource busy]  
#define ECANCELED [operation canceled]  
#define ECHILD [no child process]  
#define ECONNABORTED [connection aborted]  
#define ECONNREFUSED [connection refused]  
#define ECONNRESET [connection reset]  
#define EDEADLK [resource deadlock would occur]  
#define EDESTADDRREQ [destination address required]  
#define EDOM [argument out of domain]  
#define EEXIST [file exists]  
#define EFAULT [bad address]  
#define EFBIG [file too large]  
#define EHOSTUNREACH [host unreachable]  
#define EIDRM [identifier removed]  
#define EILSEQ [illegal byte sequence]  
#define EINPROGRESS [operation in progress]  
#define EINTR [interrupted]  
#define EINVAL [invalid argument]  
#define EIO [io error]  
#define EISCONN [already connected]  
#define EISDIR [is a directory]  
#define ELOOP [too many synbolic link levels]  
#define EMFILE [too many files open]  
#define EMLINK [too many links]  
#define EMSGSIZE [message size]  
#define ENAMETOOLONG [filename too long]  
#define ENETDOWN [network down]  
#define ENETRESET [network reset]  
#define ENETUNREACH [network unreachable]  
#define ENFILE [too many files open in system]  
#define ENOBUFS [no buffer space]  
#define ENODATA [no message available]  
#define ENODEV [no such device]  
#define ENOENT [no such file or directory]  
#define ENOEXEC [executable format error]  
#define ENOLCK [no lock available]  
#define ENOLINK [no link]  
#define ENOMEM [not enough memory]  
#define ENOMSG [no message]  
#define ENOPROTOOPT [no protocol option]  
#define ENOSPC [no space on device]  
#define ENOSR [no stream resources]  
#define ENOSTR [not a stream]  
#define ENOSYS [function not supported]  
#define ENOTCONN [not connected]  
#define ENOTDIR [not a directory]  
#define ENOTEMPTY [directory not empty]  
#define ENOTRECOVERABLE [state not recoverable]  
#define ENOTSOCK [not a socket]  
#define ENOTSUP [not supported]  
#define ENOTTY [inappropriate io control operation]  
#define ENXIO [no such device or address]  
#define EOPNOTSUPP [operation not supported]  
#define EOTHER [other]  
#define EOVERFLOW [value too large]  
#define EOWNERDEAD [owner dead]  
#define EPERM [operation not permitted]  
#define EPIPE [broken pipe]  
#define EPROTO [protocol error]  
#define EPROTONOSUPPORT [protocol not supported]  
#define EPROTOTYPE [wrong protocol type]  
#define ERANGE [result out of range]  
#define EROFS [read only file system]  
#define ESPIPE [invalid seek]  
#define ESRCH [no such process]  
#define ETIME [stream timeout]  
#define ETIMEDOUT [timed out]  
#define ETXTBSY [text file busy]  
#define EWOULDBLOCK [operation would block]  
#define EXDEV [cross device link]  
```  
  
## 참고 항목  
 [전역 상수](../c-runtime-library/global-constants.md)