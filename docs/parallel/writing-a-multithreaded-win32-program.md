---
title: 다중 스레드 Win32 프로그램 작성 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- thread stacks [C++]
- resources [C++], multithreading
- stacks [C++]
- shared resources [C++]
- threading [C++], sharing common resources
- multithreading [C++], thread stacks
- multithreading [C++], sharing common resources
- mutual exclusion [C++]
- communications [C++], between threads
- mutex [C++]
- threading [C++], thread stacks
ms.assetid: 1415f47d-417f-4f42-949b-946fb28aab0e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d88add7830316ae192a728f9c9ff10320657eaf
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="writing-a-multithreaded-win32-program"></a>다중 스레드 Win32 프로그램 작성
여러 스레드를 사용 하 여 프로그램을 작성 하는 경우의 동작을 조정 해야 하 고 [프로그램의 리소스 사용](#_core_sharing_common_resources_between_threads)합니다. 각 스레드에 있는지 확인 해야 [스레드 스택](#_core_thread_stacks)합니다.  
  
##  <a name="_core_sharing_common_resources_between_threads"></a> 스레드 간 공용 리소스 공유  
  
> [!NOTE]
>  MFC의 관점에서 비슷한 논의 알려면 [다중 스레딩: 프로그래밍 팁](../parallel/multithreading-programming-tips.md) 및 [다중 스레딩: 동기화 클래스를 사용 하는 경우](../parallel/multithreading-when-to-use-the-synchronization-classes.md)합니다.  
  
 각 스레드는 스레드 스택 및 CPU의 자체 복사본을 등록 합니다. 힙 메모리, 파일 및 정적 데이터 등의 다른 리소스는 프로세스의 모든 스레드에서 공유 됩니다. 공용 리소스를 사용 하 여 스레드를 동기화 되어야 합니다. Win32는 세마포, 임계 영역, 이벤트 및 뮤텍스를 포함 하 여 리소스를 동기화 하는 여러 방법을 제공 합니다.  
  
 다중 스레드 정적 데이터에 액세스 하는, 프로그램 리소스 충돌에 제공 해야 합니다. 한 스레드가 포함 하는 정적 데이터 구조를 업데이트 하는 프로그램을 사용해 보십시오 *x*,*y* 좌표 항목에 대 한 다른 스레드에 의해 표시 됩니다. 업데이트 스레드를 변경 하는 경우는 *x* 조정 하 고 변경 하기 전에 비워진는 *y* 좌표, 표시 스레드가 예약 될 수 있습니다 하기 전에 *y* 좌표는 업데이트. 항목이 잘못 된 위치에 표시 됩니다. 세마포를 사용 하 여 구조에 대 한 액세스를 제어 하 여이 문제를 방지할 수 있습니다.  
  
 뮤텍스 (짧은 *mut*ual *ex*clusion)는 서로 비동기적으로 실행 하는 프로세스 또는 스레드 간에 통신 하는 방법이 있습니다. 이 통신은 잠금 및 잠금 리소스를 해제 하 여 공유 리소스에 대 한 액세스를 제어 하 여 일반적으로 여러 개의 스레드 또는 프로세스의 동작을 조정 하려면 일반적으로 사용 됩니다. 이 문제를 해결 하려면 *x*,*y* 좌표 업데이트 문제를 업데이트 스레드 데이터 구조는 업데이트를 실행 하기 전에 사용 중임을 나타내는 뮤텍스를 설정 합니다. 두 좌표가 모두 처리 된 후 뮤텍스를 지웁니다. 디스플레이 업데이트 하기 전에 명확 하 게 뮤텍스에 대 한 표시 스레드가 기다려야 합니다. 이 프로세스는 뮤텍스를 기다리는 프로세스가 차단 되 고 뮤텍스를 지울 때까지 계속할 수 없습니다 때문에 뮤텍스를 차단 이라고 합니다.  
  
 에 표시 된 Bounce.c 프로그램 [샘플 다중 스레드 C 프로그램](../parallel/sample-multithread-c-program.md) 명명 된 뮤텍스를 사용 하 여 `ScreenMutex` 화면 업데이트를 조정 합니다. 호출 될 때마다 디스플레이 스레드 중 하나는 화면에 쓸 준비가 **WaitForSingleObject** 핸들을 사용 하 여 `ScreenMutex` 상수 및 **무한** 임을 나타내는  **WaitForSingleObject** 호출의 뮤텍스에 제한 시간이 초과 되지 차단 해야 합니다. 경우 `ScreenMutex` 명확 대기 함수는 다른 스레드에서 디스플레이 방해할 수 없도록 뮤텍스를 설정 하 고는 스레드를 계속 실행 합니다. 그렇지 않으면 스레드가 뮤텍스를 지울 때까지 차단 합니다. 호출 하 여 뮤텍스가 해제 스레드 표시 업데이트 완료 되 면 **ReleaseMutex**합니다.  
  
 화면 표시와 정적 데이터는 신중 하 게 관리를 요구 하는 리소스 중 두 개만 있습니다. 예를 들어 프로그램 동일한 파일에 액세스 하는 여러 스레드를 가질 수 있습니다. 다른 스레드가 파일 포인터를 이동 했을 수 있으므로 각 스레드는 읽기 또는 쓰기 전에 파일 포인터를 다시 설정 해야 합니다. 또한 각 스레드는 포인터를 배치 하는 시간 및 파일에 액세스 하는 시간 사이의 하지 선점 될 확인 해야 합니다. 이러한 스레드 세마포를 대괄호와 각 파일 액세스 하 여 파일에 대 한 액세스를 조정 하는 데 사용 해야 **WaitForSingleObject** 및 **ReleaseMutex** 호출 합니다. 다음 코드 예제에서는이 기술을 보여 줍니다.  
  
```  
HANDLE    hIOMutex= CreateMutex (NULL, FALSE, NULL);  
  
WaitForSingleObject( hIOMutex, INFINITE );  
fseek( fp, desired_position, 0L );  
fwrite( data, sizeof( data ), 1, fp );  
ReleaseMutex( hIOMutex);  
```  
  
##  <a name="_core_thread_stacks"></a> 스레드 스택  
 응용 프로그램의 기본 스택 공간은 모두 스레드 1 이라고 하는 실행의 첫 번째 스레드가 할당 됩니다. 결과적으로, 프로그램 추가 각 스레드에 대 한 별도 스택에 할당할 메모리 양이 필요한 지정 해야 합니다. 필요한 경우 운영 체제는 스레드에 대 한 추가 스택 공간을 할당 하지만 기본값을 지정 해야 합니다.  
  
 첫 번째 인수는 `_beginthread` 호출에 대 한 포인터는는 **BounceProc** 스레드를 실행 하는 함수입니다. 두 번째 인수는 스레드에 대 한 기본 스택 크기를 지정합니다. 마지막 인수에 전달 되는 ID 번호는 **BounceProc**합니다. **BounceProc** ID 번호를 사용 하 여 난수 생성기 초기값으로 사용할 스레드의 color 특성을 선택 하 고 문자 표시를 합니다.  
  
 C 런타임 라이브러리에 또는 Win32 API를 호출 하는 스레드 라이브러리 및 API 함수 호출에 대 한 충분 한 스택 공간을 허용 해야 합니다. C `printf` 함수 500 바이트 보다 큰 스택 공간이 필요 하 고 Win32 API 루틴을 호출할 때 2k 스택 공간이 있어야 합니다.  
  
 각 스레드가 스레드 스택을 사용 하므로 데이터 항목에 대해 거의 정적 데이터를 최대한으로 사용 하 여 충돌 가능성을 방지할 수 있습니다. 스레드에 private 일 수 있는 모든 데이터에 대 한 스택 자동 변수를 사용 하 여 프로그램을 디자인 합니다. Bounce.c 프로그램에는 유일한 전역 변수는 뮤텍스 이거나 초기화 이후 변경 되지 않는 변수입니다.  
  
 또한 Win32 스레드 로컬 저장소 (TLS) 스레드별 데이터를 저장할를 제공 합니다. 자세한 내용은 참조 [로컬 저장소 (TLS 스레드)](../parallel/thread-local-storage-tls.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C 및 Win32를 사용한 다중 스레딩](../parallel/multithreading-with-c-and-win32.md)