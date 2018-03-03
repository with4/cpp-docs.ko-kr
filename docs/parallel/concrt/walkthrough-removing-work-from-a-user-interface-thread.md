---
title: "연습: 사용자 인터페이스 스레드에서 작업 제거 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- user-interface threads, removing work from [Concurrency Runtime]
- removing work from user-interface threads [Concurrency Runtime]
ms.assetid: a4a65cc2-b3bc-4216-8fa8-90529491de02
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7c32613aa6938b873a820fbb491fa2c507605a6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-removing-work-from-a-user-interface-thread"></a>연습: 사용자 인터페이스 스레드에서 작업 제거
이 문서에는 작업자 스레드를 Microsoft Foundation 클래스 (MFC) 응용 프로그램의 사용자 인터페이스 (UI) 스레드에서 수행 하는 작업을 이동 하려면 동시성 런타임을 사용 하는 방법을 보여 줍니다. 이 문서에는 긴 그리기 작업의 성능을 개선 하는 방법을 보여 줍니다.  
  
 차단 작업 오프 로드 하 여 UI 스레드에서 작업을 제거, 예를 들어 그리기 작업자 스레드 수를 향상 시킬 수 응용 프로그램의 응답성. 이 연습에서는 긴 차단 작업을 보여 주기 위해 Mandelbrot 프랙탈을 생성 하는 그리기 루틴을 사용 합니다. Mandelbrot 프랙탈 생성 각 픽셀의 계산이 다른 모든 계산 독립적 이므로 병렬화에 대 한 적합 이기도 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 시작 하기 전에 다음 항목을 읽어보세요.  
  
-   [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)  
  
-   [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)  
  
-   [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)  
  
-   [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)  
  
-   [PPL에서의 취소](cancellation-in-the-ppl.md)  
  
 MFC 응용 프로그램 개발의 기본 사항을 이해 하는 것이 좋습니다 및 [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] 이 연습을 시작 하기 전에. MFC에 대 한 자세한 내용은 참조 [MFC 데스크톱 응용 프로그램](../../mfc/mfc-desktop-applications.md)합니다. 에 대 한 자세한 내용은 [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)], 참조 [GDI +](https://msdn.microsoft.com/en-us/library/windows/desktop/ms533798)합니다.  
  
##  <a name="top"></a> 섹션  
 이 연습에는 다음과 같은 섹션이 있습니다.  
  
-   [MFC 응용 프로그램 만들기](#application)  
  
-   [직렬 버전 Mandelbrot 응용 프로그램의 구현](#serial)  
  
-   [사용자 인터페이스 스레드에서 작업 제거](#removing-work)  
  
-   [그리기 성능 향상](#performance)  
  
-   [취소에 대 한 지원 추가](#cancellation)  
  
##  <a name="application"></a>MFC 응용 프로그램 만들기  
 이 섹션에서는 기본 MFC 응용 프로그램을 만드는 방법을 설명 합니다.  
  
### <a name="to-create-a-visual-c-mfc-application"></a>Visual c + + MFC 응용 프로그램을 만들려면  
  
1.  **파일** 메뉴에서 **새로 만들기**를 클릭한 다음 **프로젝트**를 클릭합니다.  
  
2.  에 **새 프로젝트** 대화 상자는 **설치 된 템플릿** 창 선택 **Visual c + +**를 선택한 후는 **템플릿** 창 선택 **MFC 응용 프로그램**합니다. 예를 들어 프로젝트에 대 한 이름을 입력 `Mandelbrot`, 클릭 하 고 **확인** 표시 하는 **MFC 응용 프로그램 마법사**합니다.  
  
3.  에 **응용 프로그램 종류** 창 선택 **단일 문서**합니다. 확인 된 **문서/뷰 아키텍처 지원** 확인란의 선택을 취소 합니다.  
  
4.  클릭 **마침** 를 프로젝트를 만들고 닫습니다는 **MFC 응용 프로그램 마법사**합니다.  
  
     응용 프로그램 빌드 및 실행 하 여 만들어졌는지 확인 합니다. 에 응용 프로그램을 작성 하는 **빌드** 메뉴를 클릭 하 여 **솔루션 빌드**합니다. 응용 프로그램이 성공적으로 빌드되면를 클릭 하 여 응용 프로그램을 실행 **디버깅 시작** 에 **디버그** 메뉴.  
  
##  <a name="serial"></a>직렬 버전 Mandelbrot 응용 프로그램의 구현  
 이 섹션에서는 Mandelbrot 프랙탈을 그리는 방법을 설명 합니다. 이 버전 Mandelbrot 프랙탈을 그립니다는 [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)] [비트맵](https://msdn.microsoft.com/library/ms534420.aspx) 개체를 다음 해당 비트맵의 내용을 클라이언트 창에 복사 합니다.  
  
#### <a name="to-implement-the-serial-version-of-the-mandelbrot-application"></a>Mandelbrot 응용 프로그램의 직렬 버전을 구현 하려면  
  
1.  Stdafx.h에 다음 추가 `#include` 지시문:  
  
     [!code-cpp[concrt-mandelbrot#1](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_1.h)]  
  
2.  ChildView.h에서 후는 `pragma` 지시문 정의 `BitmapPtr` 유형입니다. `BitmapPtr` 종류에 대 한 포인터를 사용 하는 `Bitmap` 여러 구성 요소에서 공유 하는 개체입니다. `Bitmap` 모든 구성 요소에서 더 이상 참조 개체가 삭제 됩니다.  
  
     [!code-cpp[concrt-mandelbrot#2](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_2.h)]  
  
3.  ChildView.h, 다음 코드를 추가 `protected` 의 섹션은 `CChildView` 클래스:  
  
     [!code-cpp[concrt-mandelbrot#3](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_3.h)]  
  
4.  ChildView.cpp에 주석으로 처리 하거나 다음 줄을 제거 합니다.  
  
     [!code-cpp[concrt-mandelbrot#4](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_4.cpp)]  
  
     디버그 빌드에이 단계에서 사용 하 여 응용 프로그램을 차단 합니다.는 `DEBUG_NEW` 할당자와 호환 되지 않는 [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)]합니다.  
  
5.  ChildView.cpp에 추가 `using` 지시문을 `Gdiplus` 네임 스페이스입니다.  
  
     [!code-cpp[concrt-mandelbrot#5](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_5.cpp)]  
  
6.  다음 코드를 생성자와 소멸자의 추가 `CChildView` 클래스를 초기화 및 종료 [!INCLUDE[ndptecgdiplus](../../parallel/concrt/includes/ndptecgdiplus_md.md)]합니다.  
  
     [!code-cpp[concrt-mandelbrot#6](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_6.cpp)]  
  
7.  `CChildView::DrawMandelbrot` 메서드를 구현합니다. 이 메서드를 지정 된 Mandelbrot 프랙탈 그립니다 `Bitmap` 개체입니다.  
  
     [!code-cpp[concrt-mandelbrot#7](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_7.cpp)]  
  
8.  `CChildView::OnPaint` 메서드를 구현합니다. 이 메서드를 호출 `CChildView::DrawMandelbrot` 다음의 내용을 복사 하 고는 `Bitmap` 창에는 개체입니다.  
  
     [!code-cpp[concrt-mandelbrot#8](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_8.cpp)]  
  
9. 응용 프로그램 빌드 및 실행 하 여 성공적으로 업데이트 되었는지 확인 합니다.  
  
 다음 그림에서는 Mandelbrot 응용 프로그램의 결과 보여 줍니다.  
  
 ![Mandelbrot 응용 프로그램](../../parallel/concrt/media/mandelbrot.png "mandelbrot")  
  
 각 픽셀에 대 한 계산 과정이 이기 때문에 UI 스레드 전체 계산 완료 될 때까지 추가 메시지를 처리할 수 없습니다. 이 응용 프로그램의 응답성을 저하 될 수 있습니다. 그러나 UI 스레드에서 작업 제거 하 여이 문제를 덜 수 있습니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="removing-work"></a>UI 스레드에서 작업 제거  
 이 섹션에는 Mandelbrot 응용 프로그램의 UI 스레드에서 그리기 작업을 제거 하는 방법을 보여 줍니다. 그리기 작업을 UI 스레드와에서 작업자 스레드를 이동 하 여 UI 스레드 백그라운드에서 이미지를 생성 하는 작업자 스레드가 메시지를 처리할 수 있습니다.  
  
 동시성 런타임 작업을 실행 하려면 세 가지 방법을 제공: [작업 그룹](../../parallel/concrt/task-parallelism-concurrency-runtime.md), [비동기 에이전트](../../parallel/concrt/asynchronous-agents.md), 및 [간단한 작업](../../parallel/concrt/task-scheduler-concurrency-runtime.md)합니다. 이 예에서는 이러한 메커니즘 중 하나를 사용 하 여 UI 스레드에서 작업을 제거할 수 있지만 한 [concurrency:: task_group](reference/task-group-class.md) 작업 그룹이 취소를 지원 하기 때문에 개체입니다. 이 연습에서는 클라이언트 창의 크기를 조정할 때 수행 되는 작업의 양을 줄이기 위해 및 창이 소멸 될 때 정리 작업을 나중에 취소를 사용 합니다.  
  
 또한이 예제에서는 한 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) UI 스레드와 작업자 스레드가 서로 통신할 수 있도록 하는 개체입니다. 에 대 한 포인터 이미지 생성 하는 작업자 스레드 후 보냅니다는 `Bitmap` 개체는 `unbounded_buffer` 개체 하 고 다음을 UI 스레드에 그리기 메시지를 게시 합니다. UI 스레드에서 받습니다는 `unbounded_buffer` 개체는 `Bitmap` 개체 및 클라이언트 창에 그립니다.  
  
#### <a name="to-remove-the-drawing-work-from-the-ui-thread"></a>UI 스레드에서 그리기 작업을 제거 하려면  
  
1.  Stdafx.h에 다음 추가 `#include` 지시문:  
  
     [!code-cpp[concrt-mandelbrot#101](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_9.h)]  
  
2.  ChildView.h, 추가 `task_group` 및 `unbounded_buffer` 멤버 변수를는 `protected` 의 섹션은 `CChildView` 클래스입니다. `task_group` ; 그리기를 수행 하는 작업을 보유 하는 개체는 `unbounded_buffer` 개체 완료 Mandelbrot 이미지를 보유 합니다.  
  
     [!code-cpp[concrt-mandelbrot#102](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_10.h)]  
  
3.  ChildView.cpp에 추가 `using` 지시문을 `concurrency` 네임 스페이스입니다.  
  
     [!code-cpp[concrt-mandelbrot#103](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_11.cpp)]  
  

4.  에 `CChildView::DrawMandelbrot` 메서드를 호출한 후 `Bitmap::UnlockBits`, 호출의 [concurrency:: send](reference/concurrency-namespace-functions.md#send) 전달 하는 함수는 `Bitmap` 을 UI 스레드에 개체입니다. 그런 다음 UI 스레드로 그리기 메시지를 게시 하 고 클라이언트 영역을 무효화 합니다.  

  
     [!code-cpp[concrt-mandelbrot#104](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_12.cpp)]  
  
5.  업데이트는 `CChildView::OnPaint` 받을 업데이트 된 메서드를 `Bitmap` 개체 및 클라이언트 창에 이미지를 그립니다.  
  
     [!code-cpp[concrt-mandelbrot#105](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_13.cpp)]  
  
     `CChildView::OnPaint` 메서드 하나는 메시지 버퍼에 존재 하지 않는 경우 Mandelbrot 이미지를 생성 하는 작업을 만듭니다. 메시지 버퍼에 포함 되지 것입니다는 `Bitmap` 초기 그리기 메시지와 같은 클라이언트 창 앞 다른 창으로 이동 하는 경우에는 개체입니다.  
  
6.  응용 프로그램 빌드 및 실행 하 여 성공적으로 업데이트 되었는지 확인 합니다.  
  
 그리기 작업은 백그라운드에서 수행 되기 때문에 UI 응답성이 향상 되었습니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="performance"></a>그리기 성능 향상  

 Mandelbrot 프랙탈의 생성은 각 픽셀의 수치는 다른 모든 계산의 독립적 병렬화에 대 한 적합 합니다. 그리기 프로시저를 병렬화 하는 외부 변환 `for` 루프는 `CChildView::DrawMandelbrot` 메서드를 호출 하 여 [concurrency:: parallel_for](reference/concurrency-namespace-functions.md#parallel_for) 알고리즘을 다음과 같이 합니다.  

  
 [!code-cpp[concrt-mandelbrot#301](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_14.cpp)]  
  
 각 비트맵 요소의 계산은 서로 독립적 이기 때문에 비트맵 메모리에 액세스 하는 그리기 작업을 동기화 할 필요가 없습니다. 이렇게 하면 성능은 수가 사용 가능한 프로세서 증가 합니다.  
  
 [[맨 위로 이동](#top)]  
  
##  <a name="cancellation"></a>취소에 대 한 지원 추가  
 이 섹션에는 창 크기 조정을 처리 하는 방법 및 창이 소멸 될 때 모든 활성 그리기 작업을 취소 하는 방법을 설명 합니다.  
  
 문서 [PPL에서의 취소](cancellation-in-the-ppl.md) 런타임에에서 취소가 작동 하는 방법에 대해 설명 합니다. 취소는 협조적입니다. 따라서 즉시 실행 되지 않습니다. 취소 된 작업을 중지 하려면 런타임에서 런타임에 태스크에서 후속 호출 하는 동안 내부 예외가 throw 됩니다. 이전 섹션에서는 사용 하는 `parallel_for` 그리기 작업의 성능을 향상 시키기 위해 알고리즘입니다. 에 대 한 호출 `parallel_for` 하면 런타임에서 해당 작업을 중지 하 고 작동 하도록 하므로 취소가 있습니다.  
  
### <a name="cancelling-active-tasks"></a>활성 작업 취소  
 Mandelbrot 응용 프로그램을 만듭니다 `Bitmap` 클라이언트 창의 크기와 일치 하는 개체입니다. 클라이언트 창 크기를 조정할 때마다 응용 프로그램이 새 창 크기에 대 한 이미지를 생성 하는 추가 배경 작업을 만듭니다. 응용 프로그램이 이러한 중간 이미지; 필요 하지 않습니다. 마지막 창 크기에 대 한 이미지에만 필요합니다. 응용 프로그램에서이 추가 작업을 수행 하지 않으려면에 대 한 메시지 처리기에서 모든 활성 그리기 작업을 취소할 수 있습니다는 `WM_SIZE` 및 `WM_SIZING` 창의 크기를 조정한 후 메시지와 다음 일정을 재조정 그리기 작동 합니다.  
  
 응용 프로그램 파일을 창의 크기를 조정할 때 활성 그리기 작업을 취소 하려면 호출는 [concurrency::task_group::cancel](reference/task-group-class.md#cancel) 에 대 한 처리기에서 메서드는 `WM_SIZING` 및 `WM_SIZE` 메시지입니다. 에 대 한 처리기는 `WM_SIZE` 호출 또한 메시지는 [concurrency::task_group::wait](reference/task-group-class.md#wait) 메서드 모든 활성 작업이 완료 한 다음 업데이트 된 창 크기에 따라 그리기 작업을 다시 예약에 대해 기다려야 합니다.  
  
 클라이언트 창이 소멸 될 때 것이 좋습니다 활성 모든 그리기 작업을 취소 합니다. 모든 활성 그리기 작업을 취소 하면 작업자 스레드 클라이언트 창이 소멸 된 후 메시지 UI 스레드를 게시 하지 마십시오. 응용 프로그램에 대 한 처리기에서 그리기 모든 활성 작업 취소는 `WM_DESTROY` 메시지입니다.  
  
### <a name="responding-to-cancellation"></a>취소에 응답  
 `CChildView::DrawMandelbrot` 그리기 작업을 수행 하는 메서드는 취소에 응답 해야 합니다. 런타임에서 예외 처리 작업을 취소를 사용 하기 때문에 `CChildView::DrawMandelbrot` 메서드는 모든 리소스가 올바르게 정리 되도록 예외 로부터 안전한 메커니즘을 사용 해야 합니다. 사용 하 여이 예제는 *Resource Acquisition Is Initialization* (RAII) 패턴을 보장 작업이 취소 되는 경우 비트맵 비트 잠금 해제 됩니다.  
  
##### <a name="to-add-support-for-cancellation-in-the-mandelbrot-application"></a>Mandelbrot 응용 프로그램에서 취소에 대 한 지원을 추가 하려면  
  
1.  ChildView.h에서는 `protected` 의 섹션은 `CChildView` 클래스에 대 한 선언을 추가 `OnSize`, `OnSizing`, 및 `OnDestroy` 메시지 맵 함수.  
  
     [!code-cpp[concrt-mandelbrot#201](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_15.h)]  
  
2.  ChildView.cpp, 수정에 대 한 처리기를 포함 하도록 메시지 맵에 `WM_SIZE`, `WM_SIZING`, 및 `WM_DESTROY` 메시지입니다.  
  
     [!code-cpp[concrt-mandelbrot#202](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_16.cpp)]  
  
3.  `CChildView::OnSizing` 메서드를 구현합니다. 이 메서드는 기존의 모든 그리기 작업을 취소합니다.  
  
     [!code-cpp[concrt-mandelbrot#203](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_17.cpp)]  
  
4.  `CChildView::OnSize` 메서드를 구현합니다. 이 메서드는 기존의 모든 그리기 작업을 취소 하 고 업데이트 된 클라이언트 창 크기에 대 한 새 그리기 작업을 만듭니다.  
  
     [!code-cpp[concrt-mandelbrot#204](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_18.cpp)]  
  
5.  `CChildView::OnDestroy` 메서드를 구현합니다. 이 메서드는 기존의 모든 그리기 작업을 취소합니다.  
  
     [!code-cpp[concrt-mandelbrot#205](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_19.cpp)]  
  
6.  ChildView.cpp에서 정의 된 `scope_guard` RAII 패턴을 구현 하는 클래스입니다.  
  
     [!code-cpp[concrt-mandelbrot#206](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_20.cpp)]  
  
7.  다음 코드를 추가 하는 `CChildView::DrawMandelbrot` 메서드를 호출한 후 `Bitmap::LockBits`:  
  
     [!code-cpp[concrt-mandelbrot#207](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_21.cpp)]  
  
     이 코드를 만들어서 취소를 처리 한 `scope_guard` 개체입니다. 개체가 범위를 벗어나면 비트맵 비트 잠금을 해제 합니다.  
  
8.  끝 수정 하는 `CChildView::DrawMandelbrot` 메서드를 닫습니다는 `scope_guard` 비트맵 비트 잠겨 있지 않은지, 되었으나 UI 스레드에 모든 메시지를 보내는 개체입니다. 이렇게 하면 UI 스레드 비트맵 비트 잠기지 않습니다. 되기 전에 업데이트 되지 않습니다.  
  
     [!code-cpp[concrt-mandelbrot#208](../../parallel/concrt/codesnippet/cpp/walkthrough-removing-work-from-a-user-interface-thread_22.cpp)]  
  
9. 응용 프로그램 빌드 및 실행 하 여 성공적으로 업데이트 되었는지 확인 합니다.  
  
 창의 크기를 조정할 드로잉 작업 최종 창 크기에 대해서만 수행 됩니다. 창이 소멸 될 때에 현재 그리기 작업이 모두 취소 됩니다.  
  
 [[맨 위로 이동](#top)]  
  
## <a name="see-also"></a>참고 항목  
 [동시성 런타임 연습](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [작업 병렬 처리](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [비동기 메시지 블록](../../parallel/concrt/asynchronous-message-blocks.md)   
 [메시지 전달 함수](../../parallel/concrt/message-passing-functions.md)   
 [병렬 알고리즘](../../parallel/concrt/parallel-algorithms.md)   
 [PPL에서의 취소](cancellation-in-the-ppl.md)   
 [MFC 데스크톱 응용 프로그램](../../mfc/mfc-desktop-applications.md)
