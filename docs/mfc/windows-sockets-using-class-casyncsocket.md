---
title: 'Windows 소켓: Casyncsocket 클래스 사용 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CAsyncSocket
dev_langs:
- C++
helpviewer_keywords:
- CAsyncSocket class [MFC], programming model
- Windows Sockets [MFC], asynchronous
- sockets [MFC], converting between Unicode and MBCS strings
- SOCKET handle
- sockets [MFC], asynchronous operation
- Windows Sockets [MFC], converting Unicode and MBCS strings
ms.assetid: 825dae17-7c1b-4b86-8d6c-da7f1afb5d8d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a96ccdd4ce5c49f18c12aa85060954fc97a3408b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385183"
---
# <a name="windows-sockets-using-class-casyncsocket"></a>Windows 소켓: CAsyncSocket 클래스 사용
이 문서에서는 클래스를 사용 하는 방법을 설명 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)합니다. 이 클래스는 매우 낮은 수준에서 Windows 소켓 API를 캡슐화 알아야 합니다. `CAsyncSocket` 프로그래머에 게 네트워크 통신을 자세히 알고 있지만 네트워크 이벤트에 대 한 알림을 콜백에서 편리 하 게 사용 됩니다. 이러한 가정에 따라이 문서에서는 기본 지침만 제공 합니다. 사용 하 여 아마도 고려해 야 `CAsyncSocket` Windows 소켓 편의성 MFC 응용 프로그램에서 여러 네트워크 프로토콜을 처리 하지만 유연성을 무시 하지 않을 경우. 클래스의 보다 일반적인 대체 모델을 사용 하 수 보다 자신을 직접 프로그래밍 하는 통신 효율성 향상을 얻을 수 있다는 생각 수 `CSocket`합니다.  
  
 `CAsyncSocket` 에 설명 된 *MFC 참조*합니다. Visual c + +는 Windows SDK에 있는 Windows 소켓 사양을 제공 합니다. 세부 정보는 문서를 참조 합니다. Visual c + +에 대 한 샘플 응용 프로그램을 제공 하지 않는 `CAsyncSocket`합니다.  
  
 클래스를 사용 하 여 네트워크 통신에 대 한 지식이 없는 간단한 솔루션을 원하는 경우 [CSocket](../mfc/reference/csocket-class.md) 와 `CArchive` 개체입니다. 참조 [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../mfc/windows-sockets-using-sockets-with-archives.md) 자세한 정보에 대 한 합니다.  
  
 이 문에서는 다음과 같은 내용을 설명합니다.  
  
-   만들고 사용 하는 `CAsyncSocket` 개체입니다.  
  
-   [CAsyncSocket와 사용자의 책임](#_core_your_responsibilities_with_casyncsocket)합니다.  
  
##  <a name="_core_creating_and_using_a_casyncsocket_object"></a> 만들기 및 CAsyncSocket 개체를 사용 합니다.  
  
#### <a name="to-use-casyncsocket"></a>CAsyncSocket를 사용 하려면  
  
1.  생성 한 [CAsyncSocket](../mfc/reference/casyncsocket-class.md) 개체 및 개체를 사용 하 여 기본 만들 **소켓** 처리 합니다.  
  
     소켓 만들기 2 단계 생성 MFC 패턴을 따릅니다.  
  
     예를 들어:  
  
     [!code-cpp[NVC_MFCSimpleSocket#3](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_1.cpp)]  
  
     -또는-  
  
     [!code-cpp[NVC_MFCSimpleSocket#4](../mfc/codesnippet/cpp/windows-sockets-using-class-casyncsocket_2.cpp)]  
  
     위의 첫 번째 생성자는 만듭니다는 `CAsyncSocket` 스택에 개체입니다. 두 번째 생성자는 만듭니다는 `CAsyncSocket` 힙에 합니다. 첫 번째 [만들기](../mfc/reference/casyncsocket-class.md#create) 호출 위의 기본 매개 변수를 사용 하 여 스트림 소켓을 만듭니다. 두 번째 **만들기** 호출이 지정 된 포트와 주소를 사용 하 여 데이터 그램 소켓을 만듭니다. (사용할 수 있습니다 **만들기** 버전 생성 방법입니다.)  
  
     매개 변수를 **만들기** 됩니다.  
  
    -   "Port": 정수 (short)입니다.  
  
         서버 소켓에 대 한 포트를 지정 합니다. 클라이언트 소켓의 경우 일반적으로이 매개 변수를 포트를 선택 하는 Windows 소켓에 대 한 기본값을 받아들입니다.  
  
    -   소켓 종류: **SOCK_STREAM** (기본값) 또는 **SOCK_DGRAM**합니다.  
  
    -   소켓 "address" "형식인" 또는 "128.56.22.8" 등입니다.  
  
         네트워크에서 사용자의 IP (인터넷 프로토콜) 주소입니다. 항상이 매개 변수에 대 한 기본값을 사용 합니다.  
  
     용어 "port" 및 "소켓 주소"에 설명 되어 [Windows 소켓: 포트 및 소켓 주소](../mfc/windows-sockets-ports-and-socket-addresses.md)합니다.  
  
2.  클라이언트가 소켓을 사용 하는 경우 소켓 개체는 서버에 연결 소켓을 사용 하 여 [CAsyncSocket::Connect](../mfc/reference/casyncsocket-class.md#connect)합니다.  
  
     -또는-  
  
     소켓 서버 이면 소켓 수신을 시작 하도록 설정 (으로 [CAsyncSocket::Listen](../mfc/reference/casyncsocket-class.md#listen)) 클라이언트에서 연결 시도를 합니다. 연결 요청을 받으면 사용할 수 있는 [CAsyncSocket::Accept](../mfc/reference/casyncsocket-class.md#accept)합니다.  
  
     연결을 허용한 후 암호 유효성 검사와 같은 작업을 수행할 수 있습니다.  
  
    > [!NOTE]
    >  **Accept** 멤버 함수는 비어 있는 새에 대 한 참조를 사용 `CSocket` 개체를 매개 변수로 합니다. 호출 하기 전에이 개체를 생성 해야 **Accept**합니다. 이 소켓 개체가 범위를 벗어나면 연결이 닫힙니다. 호출 하지 마십시오 **만들기** 이 새 소켓 개체에 대 한 합니다. 예를 들어 문서를 참조 하십시오. [Windows 소켓: 작업 순서](../mfc/windows-sockets-sequence-of-operations.md)합니다.  
  
3.  다른 소켓와의 통신을 호출 하 여 수행 된 `CAsyncSocket` Windows 소켓 API 함수를 캡슐화 하는 개체의 멤버 함수입니다.  
  
     Windows 소켓 사양 및 클래스 참조 [CAsyncSocket](../mfc/reference/casyncsocket-class.md) 에 *MFC 참조*합니다.  
  
4.  삭제 된 `CAsyncSocket` 개체입니다.  
  
     스택에 소켓 개체를 만든 경우 포함 하는 함수 범위를 벗어나면 해당 소멸자가 호출 됩니다. 힙의 소켓 개체를 만든 경우 사용 하 여는 **새** 연산자를 담당 하는 사용 하는 **삭제** 연산자 개체를 소멸 합니다.  
  
     소멸자가 호출 하는 개체의 [닫기](../mfc/reference/casyncsocket-class.md#close) 멤버 함수는 개체를 제거 하기 전에.  
  
 코드에서이 시퀀스의 예 (에 실제로 `CSocket` 개체)를 참조 [Windows 소켓: 작업 순서](../mfc/windows-sockets-sequence-of-operations.md)합니다.  
  
##  <a name="_core_your_responsibilities_with_casyncsocket"></a> CAsyncSocket와 사용자의 책임  
 클래스의 개체를 만들 때 [CAsyncSocket](../mfc/reference/casyncsocket-class.md), 개체 캡슐화 Windows **소켓** 처리 하 고 해당 핸들에 대 한 작업을 제공 합니다. 사용 하는 경우 `CAsyncSocket`, API를 직접 사용 하는 경우 직면할 수 있는 모든 문제를 처리 해야 합니다. 예를 들어:  
  
-   "차단" 시나리오  
  
-   바이트 순서 보내는 컴퓨터와 받는 컴퓨터 간의 차이입니다.  
  
-   유니코드 및 멀티 바이트 문자 사이 변환 집합 (MBCS) 문자열입니다.  
  
 이러한 용어와 추가 정보는 정의 참조 하십시오. [Windows 소켓: 차단](../mfc/windows-sockets-blocking.md), [Windows 소켓: 바이트 순서 지정](../mfc/windows-sockets-byte-ordering.md), [Windows 소켓: 문자열 변환](../mfc/windows-sockets-converting-strings.md) .  
  
 이러한 문제가 발생 하더라도 클래스 **CAsycnSocket** 경우 응용 프로그램에 필요한 모든 유연성 및 제어를 가져올 수 있습니다 있습니다에 대 한 올바른 선택 일 수 있습니다. 클래스를 사용 해야 하는 그렇지 않은 경우 `CSocket` 대신 합니다. `CSocket` 다양 한 사용자의 세부 숨깁니다: it에 대 한 액세스를 제공 하 고 Windows 블로킹 호출에 해당 하는 동안 메시지 펌프 `CArchive`, 바이트 순서 차이 및 문자열 변환에 대 한 관리 합니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [Windows 소켓: 백그라운드](../mfc/windows-sockets-background.md)  
  
-   [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)

