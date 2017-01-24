---
title: "다중 스레드 Win32 프로그램 작성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "통신[C++], 스레드 간"
  - "다중 스레딩[C++], 공용 리소스 공유"
  - "다중 스레딩[C++], 스레드 스택"
  - "뮤텍스[C++]"
  - "상호 제외[C++]"
  - "리소스[C++], 다중 스레딩"
  - "공유 리소스[C++]"
  - "스택[C++]"
  - "스레드 스택[C++]"
  - "스레딩[C++], 공용 리소스 공유"
  - "스레딩[C++], 스레드 스택"
ms.assetid: 1415f47d-417f-4f42-949b-946fb28aab0e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 다중 스레드 Win32 프로그램 작성
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

스레드가 여러 개 있는 프로그램을 작성하는 경우 스레드의 동작과 [프로그램 리소스 사용](#_core_sharing_common_resources_between_threads)을 조정해야 합니다.  또한 각 스레드에 [스레드 스택](#_core_thread_stacks)을 제공해야 합니다.  
  
##  <a name="_core_sharing_common_resources_between_threads"></a> 스레드 간 공용 리소스 공유  
  
> [!NOTE]
>  MFC 관점에서 이와 유사한 논의를 보려면 [다중 스레딩: 프로그래밍 팁](../parallel/multithreading-programming-tips.md) 및 [다중 스레딩: 동기화 클래스 사용 시기](../parallel/multithreading-when-to-use-the-synchronization-classes.md)를 참조하십시오.  
  
 각 스레드는 고유한 스택 및 CPU 레지스터 복사본을 가집니다.  프로세스의 모든 스레드는 파일, 정적 데이터 및 힙 메모리와 같은 다른 리소스를 공유합니다.  공용 리소스를 사용하는 스레드는 동기화되어야 합니다.  Win32는 세마포, 임계 섹션, 이벤트, 뮤텍스 등 리소스를 동기화하는 여러 가지 방법을 제공합니다.  
  
 여러 스레드가 정적 데이터에 액세스하는 경우 프로그램은 리소스 충돌에 대비해야 합니다.  한 스레드가 다른 스레드에서 표시할 항목의 x,y 좌표를 포함하는 정적 데이터 구조를 업데이트하는 프로그램을 고려해 보십시오.  업데이트 스레드가 x 좌표를 변경한 다음 y 좌표를 변경하기 전에 선점되면 y 좌표가 업데이트되기 전에 표시 스레드가 예약될 수 있습니다.  이렇게 되면 항목은 잘못된 위치에 표시됩니다.  구조에 대한 액세스를 제어하는 세마포를 사용하면 이 문제를 방지할 수 있습니다.  
  
 뮤텍스\(mutex: mutual exclusion의 약어\)는 서로 비동기적으로 실행되는 스레드 또는 프로세스 사이의 통신 수단입니다.  이 통신은 일반적으로 리소스를 잠금 및 잠금 해제하여 공유 리소스에 대한 액세스를 제어함으로써 여러 스레드 또는 프로세스의 동작을 조정하는 데 사용됩니다.  x,y 좌표 업데이트 문제를 해결하기 위해 업데이트 스레드는 업데이트를 실행하기 전에 데이터 구조가 사용 중임을 나타내는 뮤텍스를 설정합니다.  그리고 두 좌표가 모두 처리되면 뮤텍스를 지웁니다.  표시 스레드는 표시를 업데이트하기 전에 뮤텍스가 지워질 때까지 기다려야 합니다.  프로세스가 차단되어 뮤텍스가 지워질 때까지 작업을 계속할 수 없기 때문에 뮤텍스를 기다리는 이러한 과정을 뮤텍스에 대한 차단이라고 합니다.  
  
 [샘플 다중 스레드 C 프로그램](../parallel/sample-multithread-c-program.md)에서 소개한 Bounce.c 프로그램은 `ScreenMutex` 뮤텍스를 사용하여 화면 업데이트를 조정합니다.  표시 스레드가 화면에 표시할 준비가 될 때마다 `ScreenMutex`에 대한 핸들과 **INFINITE** 상수를 매개 변수로 **WaitForSingleObject**를 호출하여 **WaitForSingleObject** 호출이 해당 뮤텍스에 대해 차단되도록 하고 시간 제한 간격은 경과되지 않았음을 나타냅니다.  `ScreenMutex`가 지워지면 이 대기 함수는 다른 스레드가 표시를 방해할 수 없도록 뮤텍스를 설정하고 스레드를 계속 실행합니다.  그렇지 않은 경우 스레드는 뮤텍스가 지워질 때까지 차단됩니다.  표시 업데이트를 완료하면 스레드는 **ReleaseMutex**를 호출하여 뮤텍스를 해제합니다.  
  
 화면 표시와 정적 데이터는 주의해서 관리해야 하는 리소스입니다.  예를 들어, 프로그램의 여러 스레드가 동일한 파일에 액세스할 수 있습니다.  다른 스레드가 파일 포인터를 이동했을 수 있으므로 각 스레드는 읽기 또는 쓰기 작업을 수행하기 전에 파일 포인터를 다시 설정해야 합니다.  또한 각 스레드는 포인터를 배치하는 시간과 파일에 액세스하는 시간 사이에 비선점 방식으로 실행되어야 합니다.  이러한 스레드는 세마포를 사용하여 파일에 대한 액세스를 조정해야 하며, 이렇게 하기 위해서는 **WaitForSingleObject** 및 **ReleaseMutex**를 호출하여 각 파일 액세스를 제한합니다.  다음 코드 예제에서는 이 기법을 설명합니다.  
  
```  
HANDLE    hIOMutex= CreateMutex (NULL, FALSE, NULL);  
  
WaitForSingleObject( hIOMutex, INFINITE );  
fseek( fp, desired_position, 0L );  
fwrite( data, sizeof( data ), 1, fp );  
ReleaseMutex( hIOMutex);  
```  
  
##  <a name="_core_thread_stacks"></a> 스레드 스택  
 응용 프로그램의 기본 스택 공간은 모두 첫째 실행 스레드에 할당되며 이것을 스레드 1이라고 합니다.  따라서 사용자는 프로그램에 필요한 각 추가 스레드에 대한 별도의 스택에 할당할 메모리 공간을 지정해야 합니다.  필요한 경우 운영 체제에서 스레드에 대한 추가 스택 공간을 할당하지만 사용자가 기본값을 지정해야 합니다.  
  
 `_beginthread` 호출의 첫째 인수는 **BounceProc** 함수에 대한 포인터이며 스레드를 실행합니다.  둘째 인수는 스레드의 기본 스택 크기를 지정합니다.  마지막 인수는 **BounceProc**에 전달되는 ID 번호입니다.  **BounceProc**는 ID 번호를 사용하여 난수 생성기를 시드하고 스레드의 색 특성 및 표시 문자를 선택합니다.  
  
 C 런타임 라이브러리 또는Win32 API를 호출하는 스레드는 호출되는 라이브러리와 API 함수에 대해 충분한 스택 공간을 허용해야 합니다.  C `printf` 함수를 사용하려면 500바이트가 넘는 스택 공간이 있어야 하고 Win32 API 루틴을 호출하려면 2K의 스택 공간이 있어야 합니다.  
  
 각 스레드는 자신의 고유 스택을 갖기 때문에 가능한 한 정적 데이터를 적게 사용하여 데이터 항목에 대한 충돌 가능성을 방지할 수 있습니다.  각 스레드에 한정되는 모든 데이터에 대한 자동 스택 변수를 사용하도록 프로그램을 디자인하십시오.  Bounce.c 프로그램에서 전역 변수는 뮤텍스 또는 초기화 이후 변경되지 않는 변수 뿐입니다.  
  
 또한 Win32는 TLS\(스레드 로컬 저장소\)를 제공하여 스레드별 데이터를 저장합니다.  자세한 내용은 [TLS](../parallel/thread-local-storage-tls.md)을 참조하십시오.  
  
## 참고 항목  
 [C 및 Wind32를 사용한 다중 스레딩](../parallel/multithreading-with-c-and-win32.md)