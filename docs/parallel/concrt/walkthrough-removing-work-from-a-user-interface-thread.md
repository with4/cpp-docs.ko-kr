---
title: "연습: 사용자 인터페이스 스레드에서 작업 제거 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "사용자 인터페이스 스레드에서 작업 제거[동시성 런타임]"
  - "사용자 인터페이스 스레드, 작업 제거[동시성 런타임]"
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# 연습: 사용자 인터페이스 스레드에서 작업 제거
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 문서는 MFC\(Microsoft Foundation Classes\) 응용 프로그램의 UI\(사용자 인터페이스\) 스레드에서 수행되는 작업을 동시성 런타임을 사용하여 작업자 스레드로 이동하는 방법을 보여 줍니다.  또한 시간이 오래 걸리는 그리기 작업의 성능을 향상시키는 방법도 보여 줍니다.  
  
 그리기 등의 차단 작업을 작업자 스레드로 오프로드하여 UI 스레드에서 작업을 제거하면 응용 프로그램의 응답성이 향상될 수 있습니다.  이 연습에서는 Mandelbrot 프랙탈을 생성하는 그리기 루틴을 사용하여 시간이 오래 걸리는 차단 작업을 보여 줍니다.  각 픽셀의 계산이 다른 모든 계산과 독립적이라는 점에서 Mandelbrot 프랙탈의 생성은 병렬화에 적합한 대상이기도 합니다.  
  
## 사전 요구 사항  
 이 연습을 시작하기 전에 다음 항목의 내용을 읽어 보십시오.  
  
-   [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
-   [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)  
  
-   [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)  
  
-   [취소](../../parallel/concrt/cancellation-in-the-ppl.md)  
  
 또한 이 연습을 시작하기 전에 MFC 응용 프로그램 개발 및 [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)]의 기본 사항을 이해하는 것이 좋습니다.  CMMI에 대한 자세한 내용은 [MFC 데스크톱 응용 프로그램](../../mfc/mfc-desktop-applications.md)를 참조하십시오.  [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)]에 대한 자세한 내용은 [GDI\+](_gdiplus_GDI_start_cpp)를 참조하십시오.  
  
##  <a name="top"></a> 단원  
 이 연습에는 다음 단원이 포함되어 있습니다.  
  
-   [MFC 응용 프로그램 만들기](#application)  
  
-   [Mandelbrot 응용 프로그램의 직렬 버전 구현](#serial)  
  
-   [사용자 인터페이스 스레드에서 작업 제거](#removing-work)  
  
-   [그리기 성능 향상](#performance)  
  
-   [취소 지원 추가](#cancellation)  
  
##  <a name="application"></a> MFC 응용 프로그램 만들기  
 이 단원에서는 기본적인 MFC 응용 프로그램을 만드는 방법에 대해 설명합니다.  
  
### Visual C\+\+ MFC 응용 프로그램을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  
  
2.  **새 프로젝트** 대화 상자의 **설치된 템플릿** 창에서 **Visual C\+\+**를 선택하고 **템플릿** 창에서 **MFC 응용 프로그램**을 클릭합니다.  프로젝트 이름\(예: `Mandelbrot`\)을 입력하고 **확인**을 클릭하여 **MFC 응용 프로그램 마법사**를 표시합니다.  
  
3.  **응용 프로그램 종류** 창에서 **단일 문서**를 선택합니다.  **문서\/뷰 아키텍처 지원** 확인란의 선택이 취소되어 있는지 확인합니다.  
  
4.  **마침**을 클릭하여 프로젝트를 만들고 **MFC 응용 프로그램 마법사**를 닫습니다.  
  
     응용 프로그램을 빌드하고 실행하여 제대로 만들어졌는지 확인합니다.  응용 프로그램을 빌드하려면 **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  응용 프로그램이 제대로 빌드되면 **디버그** 메뉴에서 **디버깅 시작**을 클릭하여 응용 프로그램을 실행합니다.  
  
##  <a name="serial"></a> Mandelbrot 응용 프로그램의 직렬 버전 구현  
 이 단원에서는 Mandelbrot 프랙탈을 그리는 방법에 대해 설명합니다.  이 버전은 Mandelbrot 프랙탈을 [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] [Bitmap](https://msdn.microsoft.com/en-us/library/ms534420.aspx) 개체에 그린 다음 해당 비트맵의 내용을 클라이언트 창에 복사합니다.  
  
#### Mandelbrot 응용 프로그램의 직렬 버전을 구현하려면  
  
1.  stdafx.h에서 다음 `#include` 지시문을 추가합니다.  
  
     [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_1.h)]  
  
2.  ChildView.h에서 `pragma` 지시문 뒤에 `BitmapPtr` 형식을 정의합니다.  `BitmapPtr` 형식은 `Bitmap` 개체 포인터가 여러 구성 요소에서 공유되도록 합니다.  `Bitmap` 개체가 구성 요소에서 더 이상 참조되지 않으면 해당 개체가 삭제됩니다.  
  
     [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_2.h)]  
  
3.  ChildView.h에서 다음 코드를 `CChildView` 클래스의 `protected` 섹션에 추가합니다.  
  
     [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_3.h)]  
  
4.  ChildView.cpp에서 다음 줄을 주석으로 처리하거나 제거합니다.  
  
     [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]  
  
     디버그 빌드에서 이 단계는 [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)]와 호환되지 않는 `DEBUG_NEW` 할당자를 응용 프로그램이 사용하지 못하도록 합니다.  
  
5.  ChildView.cpp에서 `Gdiplus` 네임스페이스에 `using` 지시문을 추가합니다.  
  
     [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]  
  
6.  [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)]를 초기화하고 종료하기 위해 다음 코드를 `CChildView` 클래스의 생성자 및 소멸자에 추가합니다.  
  
     [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]  
  
7.  `CChildView::DrawMandelbrot` 메서드를 구현합니다.  이 메서드는 Mandelbrot 프랙탈을 지정된 `Bitmap` 개체에 그립니다.  
  
     [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]  
  
8.  `CChildView::OnPaint` 메서드를 구현합니다.  이 메서드는 `CChildView::DrawMandelbrot`을 호출한 다음 `Bitmap` 개체의 내용을 창에 복사합니다.  
  
     [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]  
  
9. 응용 프로그램을 빌드하고 실행하여 제대로 업데이트되었는지 확인합니다.  
  
 다음 그림에서는 Mandelbrot 응용 프로그램의 결과를 보여 줍니다.  
  
 ![Mandelbrot 응용 프로그램](../../parallel/concrt/media/mandelbrot.png "Mandelbrot")  
  
 각 픽셀의 연산에는 많은 계산 과정이 필요하기 때문에 UI 스레드는 전체 연산이 끝날 때까지 다른 메시지를 추가로 처리할 수 없습니다.  이로 인해 응용 프로그램의 응답성이 저하될 수 있습니다.  그러나 UI 스레드에서 작업을 제거하면 응답성의 저하 정도를 완화할 수 있습니다.  
  
 \[[맨 위](#top)\]  
  
##  <a name="removing-work"></a> UI 스레드에서 작업 제거  
 이 단원은 Mandelbrot 응용 프로그램의 스레드에서 그리기 작업을 제거하는 방법을 보여 줍니다.  그리기 작업을 UI 스레드에서 작업자 스레드로 이동하면 UI 스레드는 작업자 스레드에 의해 백그라운드로 이미지가 생성될 때 메시지를 처리할 수 있습니다.  
  
 동시성 런타임에서는 작업을 실행할 수 있는 세 가지 방법, 즉 [작업 그룹](../../parallel/concrt/task-parallelism-concurrency-runtime.md), [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md) 및 [간단한 작업](../../parallel/concrt/task-scheduler-concurrency-runtime.md)을 제공합니다.  이러한 메커니즘 중 하나를 임의로 사용하여 UI 스레드에서 작업을 제거할 수 있지만 작업 그룹이 취소를 지원하기 때문에 이 예제에서는 [concurrency::task\_group](../Topic/task_group%20Class.md) 개체를 사용합니다.  이 연습의 뒷부분에서는 취소를 사용하여 클라이언트 창의 크기가 조정될 때 수행되는 작업량을 줄이고 창이 소멸될 때 정리 작업을 수행합니다.  
  
 또한 이 예제에서는 [concurrency::unbounded\_buffer](../Topic/unbounded_buffer%20Class.md) 개체를 사용하여 UI 스레드와 작업자 스레드가 서로 통신할 수 있게 합니다.  작업자 스레드는 이미지를 만든 후 `Bitmap` 개체 포인터를 `unbounded_buffer` 개체로 보내고 paint 메시지를 UI 스레드로 전달합니다.  그러면 UI 스레드는 `unbounded_buffer` 개체 및 `Bitmap` 개체로부터 그릴 내용을 받아 클라이언트 창에 그립니다.  
  
#### UI 스레드에서 그리기 작업을 제거하려면  
  
1.  stdafx.h에서 다음 `#include` 지시문을 추가합니다.  
  
     [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_9.h)]  
  
2.  ChildView.h에서 `task_group` 및 `unbounded_buffer` 멤버 변수를 `CChildView` 클래스의 `protected` 섹션에 추가합니다.  `task_group` 개체는 그리기를 수행하는 작업을 저장하고, `unbounded_buffer` 개체는 완성된 Mandelbrot 이미지를 저장합니다.  
  
     [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_10.h)]  
  
3.  ChildView.cpp에서 `concurrency` 네임스페이스에 `using` 지시문을 추가합니다.  
  
     [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]  
  
4.  `CChildView::DrawMandelbrot` 메서드에서 `Bitmap::UnlockBits` 호출 뒤에 [concurrency::send](../Topic/send%20Function.md) 함수를 호출하여 `Bitmap` 개체를 UI 스레드에 전달합니다.  그런 다음 paint 메시지를 UI 스레드로 보내고 클라이언트 영역을 무효화합니다.  
  
     [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]  
  
5.  업데이트된 `Bitmap` 개체를 받고 이미지를 클라이언트 창에 그리도록 `CChildView::OnPaint` 메서드를 업데이트합니다.  
  
     [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]  
  
     `CChildView::OnPaint` 메서드는 메시지 버퍼에 Mandelbrot 이미지가 없으면 이 이미지를 생성하기 위해 작업을 만듭니다.  최초의 paint 메시지를 받거나 다른 창이 클라이언트 창 앞으로 이동하는 경우 등에는 메시지 버퍼에 `Bitmap` 개체가 포함되지 않습니다.  
  
6.  응용 프로그램을 빌드하고 실행하여 제대로 업데이트되었는지 확인합니다.  
  
 그리기 작업이 백그라운드로 수행되기 때문에 이제 UI의 응답성이 향상됩니다.  
  
 \[[맨 위](#top)\]  
  
##  <a name="performance"></a> 그리기 성능 향상  
 각 픽셀의 계산이 다른 모든 계산과 독립적이라는 점에서 Mandelbrot 프랙탈의 생성은 병렬화에 적합한 대상입니다.  그리기 프로시저를 병렬화하려면 `CChildView::DrawMandelbrot` 메서드에 있는 외부 `for` 루프를 다음과 같이 [concurrency::parallel\_for](../Topic/parallel_for%20Function.md) 알고리즘에 대한 호출로 변환합니다.  
  
 [!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]  
  
 각 비트맵 요소에 대한 계산은 서로 독립적이므로 비트맵 메모리에 액세스하는 그리기 작업을 동기화할 필요는 없습니다.  따라서 사용 가능한 프로세서 수가 증가할수록 성능은 향상될 수 있습니다.  
  
 \[[맨 위](#top)\]  
  
##  <a name="cancellation"></a> 취소 지원 추가  
 이 단원에서는 창 크기 조정을 처리하는 방법 및 창이 소멸될 때 활성 그리기 작업을 취소하는 방법에 대해 설명합니다.  
  
 [취소](../../parallel/concrt/cancellation-in-the-ppl.md) 문서에서는 런타임에서 취소가 작동하는 방식에 대해 설명합니다.  취소는 협조를 통해 이루어지므로 취소가 즉시 발생하지는 않습니다.  취소된 작업을 중지하기 위해 런타임에서는 이후에 작업에서 런타임으로 호출하는 도중 내부 예외를 throw합니다.  이전 단원에서는 `parallel_for` 알고리즘을 사용하여 그리기 작업의 성능을 향상시키는 방법을 보여 줍니다.  `parallel_for`를 호출하면 런타임에서 작업을 중지하므로 취소가 작동하게 됩니다.  
  
### 활성 작업 취소  
 Mandelbrot 응용 프로그램에서는 크기가 클라이언트 창의 크기와 일치하는 `Bitmap` 개체를 만듭니다.  클라이언트 창의 크기가 조정될 때마다 이 응용 프로그램은 백그라운드 작업을 추가로 만들어 새 창 크기에 맞게 이미지를 생성합니다.  이 응용 프로그램에는 이러한 중간 이미지가 필요하지 않고 최종 창 크기에 맞는 이미지만 필요합니다.  응용 프로그램이 이 추가 작업을 수행하지 못하도록 하려면 `WM_SIZE` 및 `WM_SIZING` 메시지의 메시지 처리기에서 모든 활성 그리기 작업을 취소한 다음 창 크기가 조정된 이후에 그리기 작업을 다시 예약하면 됩니다.  
  
 창 크기가 조정될 때 활성 그리기 작업을 취소하기 위해 응용 프로그램에서는 `WM_SIZING` 및 `WM_SIZE` 메시지의 처리기에 있는 [concurrency::task\_group::cancel](../Topic/task_group::cancel%20Method.md) 메서드를 호출합니다.  또한 `WM_SIZE` 메시지 처리기에서는 모든 활성 작업이 완료될 때까지 기다린 다음 업데이트된 창 크기에 따라 그리기 작업을 다시 예약하기 위해 [concurrency::task\_group::wait](../Topic/task_group::wait%20Method.md) 메서드를 호출합니다.  
  
 클라이언트 창이 소멸될 때 모든 활성 그리기 작업을 취소하는 것이 좋습니다.  모든 활성 그리기 작업을 취소하면 클라이언트 창이 소멸된 이후에 작업자 스레드가 메시지를 UI 스레드로 보내지 않습니다.  응용 프로그램은 `WM_DESTROY` 메시지 처리기에서 모든 활성 그리기 작업을 취소합니다.  
  
### 취소에 응답  
 그리기 작업을 수행하는 `CChildView::DrawMandelbrot` 메서드는 취소에 응답해야 합니다.  런타임에서는 예외 처리를 사용하여 작업을 취소하기 때문에 `CChildView::DrawMandelbrot` 메서드는 예외로부터 안전한 메커니즘을 사용하여 모든 리소스가 올바로 정리되도록 해야 합니다.  이 예제에서는 작업이 취소될 때 비트맵 비트의 잠금이 해제되도록 하기 위해 *RAII\(Resource Acquisition Is Initialization\)* 패턴을 사용합니다.  
  
##### Mandelbrot 응용 프로그램에서 취소에 대한 지원을 추가하려면  
  
1.  ChildView.h에서 `CChildView` 클래스의 `protected` 섹션에 `OnSize`, `OnSizing` 및 `OnDestroy` 메시지 맵 함수의 선언을 추가합니다.  
  
     [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_15.h)]  
  
2.  ChildView.cpp에서 `WM_SIZE`, `WM_SIZING` 및 `WM_DESTROY` 메시지 처리기를 포함하도록 메시지 맵을 수정합니다.  
  
     [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]  
  
3.  `CChildView::OnSizing` 메서드를 구현합니다.  이 메서드는 기존의 모든 그리기 작업을 취소합니다.  
  
     [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]  
  
4.  `CChildView::OnSize` 메서드를 구현합니다.  이 메서드는 기존의 모든 그리기 작업을 취소하고 업데이트된 클라이언트 창 크기에 맞게 새 그리기 작업을 만듭니다.  
  
     [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]  
  
5.  `CChildView::OnDestroy` 메서드를 구현합니다.  이 메서드는 기존의 모든 그리기 작업을 취소합니다.  
  
     [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]  
  
6.  ChildView.cpp에서 RAII 패턴을 구현하는 `scope_guard` 클래스를 정의합니다.  
  
     [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]  
  
7.  다음 코드를 `Bitmap::LockBits`에 대한 호출 뒤의 `CChildView::DrawMandelbrot` 메서드에 추가합니다.  
  
     [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]  
  
     이 코드는 `scope_guard` 개체를 만들어 취소를 처리합니다.  개체가 범위를 벗어나면 해당 개체에서 비트맵 비트의 잠금을 해제합니다.  
  
8.  비트맵 비트의 잠금이 해제된 후 메시지가 UI 스레드로 보내지기 전에 `scope_guard` 개체를 폐기하도록 `CChildView::DrawMandelbrot` 메서드의 끝 부분을 수정합니다.  이렇게 하면 비트맵 비트의 잠금이 해제되기 전에 UI 스레드가 업데이트되지 않습니다.  
  
     [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/CPP/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]  
  
9. 응용 프로그램을 빌드하고 실행하여 제대로 업데이트되었는지 확인합니다.  
  
 창 크기를 조정하면 최종 창 크기에 대해서만 그리기 작업이 수행됩니다.  창이 소멸되는 경우 모든 활성 그리기 작업 역시 취소됩니다.  
  
 \[[맨 위](#top)\]  
  
## 참고 항목  
 [동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)   
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [취소](../../parallel/concrt/cancellation-in-the-ppl.md)   
 [MFC 데스크톱 응용 프로그램](../../mfc/mfc-desktop-applications.md)