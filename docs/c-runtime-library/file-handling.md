---
title: "파일 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.files"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "파일[C++], 처리"
  - "파일[C++], 조작"
  - "파일[C++], 열기"
ms.assetid: 48119e2e-e94f-4602-b08b-b72440f731d8
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# 파일 처리
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이러한 루틴을 사용하여 파일을 만들고 삭제하고 조작하며 파일 액세스 권한을 설정하고 확인합니다.  
  
 C 런타임 라이브러리에서는 한 번에 열 수 있는 파일의 수가 512개로 제한됩니다. 최대 파일 수보다 많이 열려고 하면 설명자 또는 파일 스트림에서 프로그램 오류가 발생합니다.[\_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md)를 사용하여 이 숫자를 변경합니다.  
  
 다음 루틴은 파일 설명자에 지정된 파일에서 작동합니다.  
  
### 파일 처리 루틴\(파일 설명자\)  
  
|루틴|기능|.NET Framework의 해당 값|  
|--------|--------|--------------------------|  
|[\_chsize](../c-runtime-library/reference/chsize.md),[\_chsize\_s](../c-runtime-library/reference/chsize-s.md)|파일 크기 변경|[System::IO::Stream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.stream.setlength.aspx), [System::IO::FileStream::SetLength](https://msdn.microsoft.com/en-us/library/system.io.filestream.setlength.aspx)|  
|[\_filelength, \_filelengthi64](../c-runtime-library/reference/filelength-filelengthi64.md)|파일 길이 가져오기|[System::IO::Stream::Length](https://msdn.microsoft.com/en-us/library/system.io.stream.length.aspx), [System::IO::FileStream::Length](https://msdn.microsoft.com/en-us/library/system.io.filestream.length.aspx)|  
|[\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)|설명자에서 파일 상태 정보 가져오기|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.|  
|[\_get\_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|기존 C 런타임 파일 설명자와 연결된 운영 체제 파일 핸들 반환|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.|  
|[\_isatty](../c-runtime-library/reference/isatty.md)|문자 입출력 장치 확인|[System::IO::Stream::CanWrite](https://msdn.microsoft.com/en-us/library/system.io.filestream.canwrite.aspx), [System::IO::FileStream::CanWrite](https://msdn.microsoft.com/en-us/library/system.io.stream.canwrite.aspx)|  
|[\_locking](../c-runtime-library/reference/locking.md)|파일의 잠금 영역|[System::IO::FileStream::Lock](https://msdn.microsoft.com/en-us/library/system.io.filestream.lock.aspx)|  
|[\_open\_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|기존 운영 체제 파일 핸들에 C 런타임 파일 설명자 연결|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
|[\_setmode](../c-runtime-library/reference/setmode.md)|파일 변환 모드 설정|[System::IO::BinaryReader 클래스](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.aspx), [System::IO::TextReader 클래스](https://msdn.microsoft.com/en-us/library/system.io.textreader.aspx)|  
  
 다음 루틴은 경로 또는 파일 이름으로 지정된 파일에서 작동합니다.  
  
### 파일 처리 루틴\(경로 또는 파일 이름\)  
  
|루틴|기능|.NET Framework의 해당 값|  
|--------|--------|--------------------------|  
|[\_access, \_waccess](../c-runtime-library/reference/access-waccess.md), [\_access\_s, \_waccess\_s](../c-runtime-library/reference/access-s-waccess-s.md)|파일 권한 설정 확인|[System::IO::FileAccess 열거형](https://msdn.microsoft.com/en-us/library/4z36sx0f.aspx)|  
|[\_chmod, \_wchmod](../c-runtime-library/reference/chmod-wchmod.md)|파일 사용 권한 설정 변경|[System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx), [System::Security::Permissions::FileIOPermission](https://msdn.microsoft.com/en-us/library/system.security.permissions.fileiopermission.aspx)|  
|[\_fullpath, \_wfullpath](../c-runtime-library/reference/fullpath-wfullpath.md)|상대 경로를 절대 경로 이름으로 확장|[System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[\_makepath, \_wmakepath](../c-runtime-library/reference/makepath-wmakepath.md), [\_makepath\_s, \_wmakepath\_s](../c-runtime-library/reference/makepath-s-wmakepath-s.md)|경로 구성 요소를 단일 전체 경로에 병합|[System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)|  
|[\_mktemp, \_wmktemp](../c-runtime-library/reference/mktemp-wmktemp.md), [\_mktemp\_s, \_wmktemp\_s](../c-runtime-library/reference/mktemp-s-wmktemp-s.md)|고유한 파일 이름 만들기|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.|  
|[remove, \_wremove](../c-runtime-library/reference/remove-wremove.md)|파일 삭제|[System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)|  
|[rename, \_wrename](../c-runtime-library/reference/rename-wrename.md)|파일 이름 바꾸기|[System::IO::File::Move](https://msdn.microsoft.com/en-us/library/system.io.file.move.aspx)|  
|[\_splitpath, \_wsplitpath](../c-runtime-library/reference/splitpath-wsplitpath.md), [\_splitpath\_s, \_wsplitpath\_s](../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)|구성 요소로 경로 구문 분석|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.|  
|[\_stat, \_stat64, \_stati64, \_wstat, \_wstat64, \_wstati64](../c-runtime-library/reference/stat-functions.md)|명명된 파일에서 파일 상태 정보 가져오기|[System::IO::File::GetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.getattributes.aspx), [System::IO::File::GetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.getcreationtime.aspx), [System::IO::File::GetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastaccesstime.aspx), [System::IO::File::GetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastwritetime.aspx)|  
|[\_umask](../c-runtime-library/reference/umask.md), [\_umask\_s](../c-runtime-library/reference/umask-s.md)|프로그램에서 만든 새 파일에 대해 기본 사용 권한 마스크 설정|[System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)|  
|[\_unlink, \_wunlink](../c-runtime-library/reference/unlink-wunlink.md)|파일 삭제|[System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)|  
  
 다음 루틴은 파일을 엽니다.  
  
### 파일 처리 루틴\(파일 열기\)  
  
|루틴|기능|.NET Framework의 해당 값|  
|--------|--------|--------------------------|  
|[fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen\_s, \_wfopen\_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|파일을 열고 열린 파일에 대한 포인터를 반환합니다.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.%23ctor%2A>|  
|[\_fsopen, \_wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)|파일 공유로 스트림을 열고 열린 파일에 대한 포인터를 반환합니다.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.%23ctor%2A>|  
|[\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)|파일을 열고 열린 파일에 대한 파일 설명자를 반환합니다.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.%23ctor%2A>|  
|[\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md), [\_sopen\_s, \_wsopen\_s](../c-runtime-library/reference/sopen-s-wsopen-s.md)|파일 공유로 파일을 열고 열린 파일에 대한 파일 설명자를 반환합니다.||  
|[\_pipe](../c-runtime-library/reference/pipe.md)|읽기 및 쓰기용 파이프를 만듭니다.|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.|  
|[freopen, \_wfreopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen\_s, \_wfreopen\_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|파일 포인터를 다시 할당합니다.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx), <xref:System.IO.FileStream.%23ctor%2A>|  
  
 다음 함수는 `FILE` 구조체, 파일 설명자 및 Win32 파일 핸들 사이에서 파일의 표현을 변경하는 방법을 제공합니다.  
  
||||  
|-|-|-|  
|[\_fdopen, \_wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)|하위 수준 I\/O를 위해 이전에 연 파일에 스트림을 연결하고 열린 스트림에 대한 포인터를 반환합니다.|[System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.filestream.aspx)|  
|[\_fileno](../c-runtime-library/reference/fileno.md)|스트림에 연결된 파일 설명자를 가져옵니다.|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
|[\_get\_osfhandle](../c-runtime-library/reference/get-osfhandle.md)|기존 C 런타임 파일 설명자와 연결된 운영 체제 파일 핸들 반환|해당 사항 없음. 표준 C 함수를 호출하려면 `PInvoke`를 사용합니다. 자세한 내용은 [플랫폼 호출 예제](../Topic/Platform%20Invoke%20Examples.md)를 참조하세요.|  
|[\_open\_osfhandle](../c-runtime-library/reference/open-osfhandle.md)|C 런타임 파일 설명자를 기존 운영 체제 파일 핸들에 연결합니다.|[System::IO::FileStream::Handle](https://msdn.microsoft.com/en-us/library/system.io.filestream.handle.aspx)|  
  
 다음 Win32 함수도 파일 및 파이프를 엽니다.  
  
-   [CreateFile](http://msdn.microsoft.com/library/windows/desktop/aa363858.aspx)  
  
-   [CreatePipe](http://msdn.microsoft.com/library/windows/desktop/aa365152.aspx)  
  
-   [CreateNamedPipe](http://msdn.microsoft.com/library/windows/desktop/aa365150.aspx)  
  
## 참고 항목  
 [범주별 런타임 루틴](../c-runtime-library/run-time-routines-by-category.md)   
 [디렉터리 제어](../c-runtime-library/directory-control.md)   
 [시스템 호출](../c-runtime-library/system-calls.md)