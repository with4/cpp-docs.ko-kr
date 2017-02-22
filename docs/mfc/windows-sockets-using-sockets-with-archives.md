---
title: "Windows 소켓: 소켓과 아카이브 함께 사용 | Microsoft Docs"
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
  - "보관[C++], 및 Windows 소켓"
  - "CSocket 클래스, 프로그래밍 모델"
  - "소켓[C++], 보관"
  - "Windows 소켓[C++], 보관"
ms.assetid: 17e71a99-a09e-4e1a-9fda-13d62805c824
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Windows 소켓: 소켓과 아카이브 함께 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서에서 [CSocket 프로그래밍 모델](#_core_the_csocket_programming_model)을 설명합니다.  클래스 [CSocket](../mfc/reference/csocket-class.md) 는 클래스 [CAsyncSocket](../mfc/reference/casyncsocket-class.md) 보다 높은 수준의 추상화에서 소켓지원을 제공합니다.  `CSocket` 은 [CArchive](../mfc/reference/carchive-class.md) 개체를 통해 소켓 개체로부터 데이터를 전달하기 위해 MFC serialization 프로토콜의 버전을 사용합니다.  `CSocket` 는 차단을 제공하고\(Windows 메시지의 백그라운드 처리를 관리하는 동안\) `CArchive` 에대한 액세스를 제공하는데, 이것은 행 API 또는 클래스 `CAsyncSocket` 들 중 하나를 사용하여야하는 통신의 여러 측면을 관리합니다.  
  
> [!TIP]
>  `CAsyncSocket` 의 보다 편리한 버전으로써 이 자신으로 `CSocket` 클래스를 사용할 수 있지만, 가장 간단한 프로그래밍 모델은 `CSocket` 와 `CArchive` 개체를 함께 사용합니다.  
  
 보관 작업들에서 소켓들을 어떻게 구현하는지에 관한 자세한 내용은, [Windows 소켓: 소켓과 아카이브를 함께 사용하는 방법](../mfc/windows-sockets-how-sockets-with-archives-work.md)을 참고하세요.  예제 코드는, [Windows 소켓: 작업 순서](../mfc/windows-sockets-sequence-of-operations.md) 와 [Windows 소켓: 아카이브를 사용하는 소켓의 예](../mfc/windows-sockets-example-of-sockets-using-archives.md)를 참고하세요.  소켓 클래스로부터 직접 클래스를 파생하여 얻을 수 있는 일부 기능에 관한 정보는, [Windows 소켓: 소켓 클래스에서 파생시키기](../mfc/windows-sockets-deriving-from-socket-classes.md) 를 참고하세요.  
  
> [!NOTE]
>  만일 설정된 \(비 MFC\) 서버들과 통신하는 MFC 클라이언트 프로그램을 작성하는 경우, 보관을 통해 C\+\+ 개체들을 보내지 마세요.  서버가 보내길 원하는 개체의 종류를 이해하는 MFC 응용프로그램이 아니라면, 이것은 받을 수 없고 개체는 역직렬화됩니다.  비 MFC 응용 프로그램과 통신의 주제에서 관련된 자료는, [Windows 소켓: 바이트 순서 지정](../mfc/windows-sockets-byte-ordering.md) 문서를 참고하세요.  
  
##  <a name="_core_the_csocket_programming_model"></a> CSocket 프로그래밍 모델  
 `CSocket` 개체를 사용하여 생성과 여러 MFC 클래스 개체들의 연결을 호출합니다.  일반 프로시저 아래에서, 각 실행은 서버 소켓과 클라이언트 두곳에서 처리되고 각 소켓 형식을 다른 작업들을 필요로 합니다.  
  
> [!TIP]
>  런타임에서, 서버 응용 프로그램이 일반적으로 먼저 준비되고, 클라이언트 응용프로그램이 연결을 찾을 때 "listening"상태가 됩니다.  만일 클라이언트가 연결을 시도할 때 서버가 준비되지 않았을 경우, 일반적으로 후에 다시 연결을 시도하도록 하는 응용프로그램이 요구됩니다.  
  
#### 서버 소켓과 클라이언트 소켓 사이에 통신을 설정하려면  
  
1.  [CSocket](../mfc/reference/csocket-class.md) 개체를 생성합니다.  
  
2.  내부 **SOCKET** 핸들을 생성하기 위한 개체를 사용합니다.  
  
     `CSocket` 클라이언트 개체에 대하여, 데이터그램 소켓을 필요로 하지 않는다면, 일반적으로 [Create](../Topic/CAsyncSocket::Create.md) 를 위한 기본 매개변수를 사용해야합니다.  `CSocket` 서버 개체에 대해, **Create** 호출에서 포트를 지정해야 합니다.  
  
    > [!NOTE]
    >  `CArchive` 는 데이터그램 소켓을 사용하는 경우 작동하지 않습니다.  만일 데이터그램 소켓에 대해 `CSocket` 을 사용하려는 경우, `CAsyncSocket` 을 이용해서 이 클래스를 사용해야하며, 이 경우 보관되지 않습니다.  데이터그램을 신뢰할 수 없기 때문에 \(전달이 보장되지 않고 순서가 바뀌거나 반복될 수 있습니다.\), 이것은 보관을 통해 직렬화와 호환되지 않습니다.  안정적이고 순서대로 완료하기 위해 직렬화 연산을 예상합니다.  만일 `CSocket` 을 데이터그램을 통해 `CArchive` 개체와 함께 사용하려고 하는 경우, MFC 어셜션 오류가 발생합니다.  
  
3.  만일 소켓이 클라이언트라면, 서버 소켓으로 소켓 개체를 연결하기 위해 [CAsyncSocket::Connect](../Topic/CAsyncSocket::Connect.md) 를 호출합니다.  
  
     또는  
  
     만일 소켓이 서버인 경우, 클라이언트로부터 연결 시도를 listening을 시작하기위해 [CAsyncSocket::Listen](../Topic/CAsyncSocket::Listen.md) 을 호출합니다.  연결 요청을 받으면, [CAsyncSocket::Accept](../Topic/CAsyncSocket::Accept.md) 을 호출함으로써 이것을 수락합니다.  
  
    > [!NOTE]
    >  **Accept** 멤버함수는 새로, 이것의 매개변수로써 빈 `CSocket` 개체로 참조를 받습니다.  **Accept** 를 호출 하기 전에 이 개체를 생성해야합니다.  만일 이 소켓 개체가 범위를 벗어날 경우, 연결이 닫힙니다.  이 새 소켓 개체에 대해 **Create** 를 호출하세요.  
  
4.  이것과 함께 `CSocket` 개체를 연관시켜, [CSocketFile](../mfc/reference/csocketfile-class.md) 개체를 만듭니다.  
  
5.  로드\(수신\) 또는 저장\(송신\) 데이터 중 하나에 대해 [CArchive](../mfc/reference/carchive-class.md) 개체를 만듭니다.  보관은 `CSocketFile` 개체와 연결됩니다.  
  
     데이터그램 소켓들과 함께 `CArchive` 이 사용할 수 없음을 유의하세요.  
  
6.  클라이언트와 서버 소켓사이에 데이터를 전달하기 위해 `CArchive` 개체를 사용합니다.  
  
     주어진 `CArchive` 개체는 오직 한 방향에서만 데이터를 옮기는 것에 주의하세요: 로드 \(수신\) 또는 저장 \(송신\) 중 하나.  어떤 경우에는, 2 `CArchive` 개체들을 사용합니다: 하나는 데이터를 보내고, 다른 하나는 정보를 받기 위해.  
  
     연결되고 보관이 설정된 이후 암호 검사와 같은 작업을 수행할 수 있습니다.  
  
7.  보관, 소켓 파일과 소켓 개체를 파괴합니다.  
  
    > [!NOTE]
    >  클래스 `CArchive` 는 특히 클래스 `CSocket` 를 사용하는 경우 `IsBufferEmpty` 함수를 제공합니다.  만일 버퍼가 여러 데이터 메시지를 포함하는 경우, 예를 들어, 모든 읽기와 버퍼가 비워질때까지 반복이 필요합니다.  그렇지 않으면, 데이터가 수신되고 다음 알림이 무기한으로 지연될 수 있습니다.  모든 데이터를 받았는지 확인하기 위해 `IsBufferEmpty` 를 사용합니다.  
  
 [Windows 소켓: 작업 순서](../mfc/windows-sockets-sequence-of-operations.md) 문서는 예제코드의 이 프로세스의 양면을 모두 보여줍니다.  
  
 자세한 내용은 다음을 참조하십시오.  
  
-   [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)  
  
## 참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)   
 [CSocket::Create](../Topic/CSocket::Create.md)