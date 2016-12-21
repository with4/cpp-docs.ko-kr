---
title: "Windows 소켓: 차단 | Microsoft Docs"
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
  - "블로킹 모드 소켓"
  - "소켓[C++], 다른 Windows 플랫폼에서의 동작"
  - "소켓[C++], 블로킹 모드"
  - "Windows 소켓[C++], 블로킹 모드"
  - "Windows 소켓[C++], Windows 플랫폼"
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows 소켓: 차단
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서 및 두 개의 안내 문서는 Windows 소켓 프로그래밍의 몇 가지 문제를 설명합니다.  이 문서는 차단에 대해 설명합니다.  다른 문제는 문서 [Windows Sockets: Byte Ordering](../mfc/windows-sockets-byte-ordering.md) 및 [Windows Sockets: Converting Strings](../mfc/windows-sockets-converting-strings.md)에서 설명합니다.  
  
 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)를 사용하거나 이에서 파생되었다면, 사용자는 이 문제를 스스로 관리하는 것이 필요합니다.  [CSocket](../mfc/reference/csocket-class.md) 클래스를 사용하거나 이를 이용하여 파생시키면, MFC를 사용자를 위해 그들을 관리합니다.  
  
## 차단  
 소켓은 "차단 모드" 또는 "비차단 모드"가 될 수 있습니다. 차단\(또는 동기\) 모드에서 소켓 함수는 작업을 완료할 수 있을 때까지 반환되지 않습니다.  호출이 반환되기 전까지는 호출된 함수의 소켓이 아무 것도 할 수 없기 — 차단되기 — 때문에 이를 차단이라고 합니다.  **Receive** 멤버 함수의 호출은 예를 들어, 전송하는 응용 프로그램이 전송하기를 기다리며 \(이는 `CSocket`를 사용하거나 또는 `CAsyncSocket` 차단과 함께 사용한 경우입니다.\) 완성할 때까지 임의의 긴 시간이 걸릴 수 있습니다.  `CAsyncSocket` 개체가 차단 모드\(비동기식으로 작동하는\)이면, 호출은 즉시 반환되며, [GetLastError](../Topic/CAsyncSocket::GetLastError.md) 멤버 함수를 사용하여 검색 가능한 현재 오류 코드는 호출이 차단되었으며 모드로 인하여 즉시 반환되지 않았다는 것을 나타내는 **WSAEWOULDBLOCK**입니다. \(`CSocket`는 절대로 **WSAEWOULDBLOCK**을 반환하지 않습니다.  클래스는 사용자를 위한 차단을 관리합니다.  
  
 소켓의 동작은 32비트 및 64비트 운영 체제\(예를 들어 Windows 95 또는 Windows 98\)에서는 16비트 운영 체제\(예를 들어 Windows3.1\)와 다릅니다.  16비트 운영체제와 달리, 32비트 및 64비트 운영체제는 선점형 멀티태스킹을 사용하고 다중 스레딩을 제공합니다.  32비트 및 64비트 운영체제에서, 소켓을 별도의 작업자 스레드에 넣을 수 있습니다.  스레드의 소켓은 응용 프로그램에서 다른 작업을 방해하지 않고 차단할 수 있고 차단하는 데 계산 시간을 소비하지 않고 차단할 수 있습니다.  다중 스레드 프로그래밍에 대한 정보를 보려면 [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md)을 참조하십시오.  
  
> [!NOTE]
>  다중 스레드 응용 프로그램에서, 사용자 인터페이스의 응답성에 영향을 주지 않고 사용자 프로그램 디자인을 단순화하기 위해 `CSocket`의 차단 특성을 사용할 수 있습니다.  주 스레드에서 사용자 상호 작용을 처리하고 대체 스레드에서 `CSocket` 프로세싱을 처리하는 방법으로 이러한 논리 연산을 구분할 수 있습니다.  멀티 스레드가 아닌 응용 프로그램에서, 이러한 두 작업은 단일 스레드로써 결합되고 처리되어야 합니다. 이는 보통 `CAsyncSocket`를 사용하여 요구시 통신을 처리할 수 있다는 것을 의미하거나 긴 동기적 작업 도중 사용자 작업을 처리하기 위하여 `CSocket::OnMessagePending`를 오버라이딩한 것을 의미합니다.  
  
 이 설명의 나머지 부분은 16 비트 운영 체제를 대상으로 하는 프로그래머를 위한 것입니다.  
  
 일반적으로, `CAsyncSocket`를 사용하고 있다면, 차단 작업을 사용하는 것을 피해야 하고 대신에 비동기적으로 수행되어야 합니다.  비동기 작업에서, **Receive**를 호출한 이후 **WSAEWOULDBLOCK** 오류 코드를 수신하는 시점에서, 예를 들어, 다시 읽을 수 있다는 것을 사용자에게 통지하기 위해 `OnReceive` 멤버 함수가 호출될 때까지 기다릴 수 있습니다.  비동기 호출은 [OnReceive](../Topic/CAsyncSocket::OnReceive.md)와 같이 사용자 소켓의 적절한 콜백 통지 함수를 콜백함으로써 이루어집니다.  
  
 Windows에서, 차단 호출은 잘못된 작업으로 간주됩니다.  기본적으로 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)는 비동기 호출을 지원하며, 사용자는 콜백 알림을 사용하여 직접 차단을 관리해야 합니다.  반면에 클래스 [CSocket](../mfc/reference/csocket-class.md)는 동기화됩니다.  Windows 메시지를 띄우고 사용자를 위해 차단을 관리합니다.  
  
 차단에 대한 자세한 내용은 Windows 소켓 사양을 참조하십시오.  "On" 기능에 대한 자세한 내용은 [Windows Sockets: Socket Notifications](../mfc/windows-sockets-socket-notifications.md) 및 [Windows Sockets: Deriving from Socket Classes](../mfc/windows-sockets-deriving-from-socket-classes.md)을 참조하십시오.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows 소켓: 소켓과 아카이브 함께 사용](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows 소켓: 백그라운드](../mfc/windows-sockets-background.md)  
  
-   [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)  
  
## 참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)   
 [CAsyncSocket::OnSend](../Topic/CAsyncSocket::OnSend.md)