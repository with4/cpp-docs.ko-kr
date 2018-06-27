---
title: 'Windows 소켓: 바이트 순서 지정 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- byte order issues in sockets programming
- sockets [MFC], byte order issues
- Windows Sockets [MFC], byte order issues
ms.assetid: 8a787a65-f9f4-4002-a02f-ac25a5dace5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3a95725565dee2b25fd7f2e39927fde88c9cddff
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36956004"
---
# <a name="windows-sockets-byte-ordering"></a>Windows 소켓: 바이트 순서 지정
이 문서 및 두 개의 참조 문서에서는 Windows 소켓 프로그래밍의 몇 가지 문제를 설명합니다. 이 문서에서는 바이트 순서 지정에 대해 설명 합니다. 다른 문제는 문서에서 다루지: [Windows 소켓: 차단](../mfc/windows-sockets-blocking.md) 및 [Windows 소켓: 문자열 변환](../mfc/windows-sockets-converting-strings.md)합니다.  
  
 사용 하거나 클래스에서 파생 되는 경우 [CAsyncSocket](../mfc/reference/casyncsocket-class.md), 이러한 문제를 직접 관리 해야 합니다. 사용 하거나 클래스에서 파생 되는 경우 [CSocket](../mfc/reference/csocket-class.md), MFC에서를 관리 합니다.  
  
## <a name="byte-ordering"></a>바이트 순서 지정  
 다양 한 컴퓨터 아키텍처는 경우에 따라 서로 다른 바이트 순서를 사용 하 여 데이터를 저장 합니다. 예를 들어 Intel 기반 컴퓨터는 Macintosh (Motorola) 컴퓨터의 반대 순서로 데이터를 저장 합니다. "Little Endian,"를 호출 하는 Intel 바이트 순서 네트워크 표준 "Big-endian" 순서의 반대로 이기도 합니다. 다음 표에서 이러한 항에 설명 합니다.  
  
### <a name="big--and-little-endian-byte-ordering"></a>큰-및 Little Endian 바이트 순서 지정  
  
|바이트 순서 지정|의미|  
|-------------------|-------------|  
|Big Endian|가장 중요 한 바이트 워드의 왼쪽된 끝 켜져 있습니다.|  
|Little-endian|가장 중요 한 바이트가 단어의 오른쪽 끝입니다.|  
  
 일반적으로 네트워크를 통해 송수신 하는 데이터에 대 한 바이트 순서 변환에 걱정할 필요는 없지만 바이트 순서를 변환 해야 하는 경우가 있습니다.  
  
## <a name="when-you-must-convert-byte-orders"></a>바이트 순서를 변환 해야 하는 경우  
 다음과 같은 상황에서 바이트 순서를 변환 해야 합니다.  
  
-   다른 컴퓨터에 보내는 데이터와는 달리 네트워크에 의해 해석 되어야 하는 정보를 전달 합니다. 예를 들어 전달 하면 포트와 주소는 네트워크 이해 해야 합니다.  
  
-   서버 응용 프로그램이 통신 하는 MFC 응용 프로그램 (아니며에 대 한 소스 코드가 없는). 이 위치는 두 컴퓨터는 동일한 바이트 순서 지정을 공유 하지 않는 경우 바이트 순서 변환에 대 한 호출 합니다.  
  
## <a name="when-you-do-not-have-to-convert-byte-orders"></a>바이트 순서를 변환할 필요가 없습니다 경우  
 다음과 같은 경우에는 바이트 순서를 변환할을 방지할 수 있습니다.  
  
-   양쪽 끝에 컴퓨터 수에 동의 하지 않고 바이트를 교환 하 고 두 컴퓨터 모두 동일한 바이트 순서를 사용 합니다.  
  
-   서버와 통신 하는 MFC 응용 프로그램입니다.  
  
-   말할 수 있도록 명시적으로 또는 not 바이트 순서를 변환 해야 하는지 여부를 통신 하는 서버에 대 한 소스 코드를 있는 합니다.  
  
-   MFC에 서버를 이식할 수 있습니다. 상당히 쉽게 며이 결과 일반적으로 더 작은, 더 빠른 코드입니다.  
  
 작업할 [CAsyncSocket](../mfc/reference/casyncsocket-class.md), 모든 필요한 바이트 순서 변환을 직접 관리 해야 합니다. Windows 소켓은 "Big-endian" 바이트 순서 모델을 표준화 하 고이 순서와 다른 사용자 간에 변환할 기능을 제공 합니다. [CArchive](../mfc/reference/carchive-class.md)그러나 함께 사용 하면 [CSocket](../mfc/reference/csocket-class.md), 순서를 바꿔서 ("Little-endian")를 사용 하 여 하지만 `CArchive` 바이트 순서 변환의 세부 사항을 처리 합니다. 이 응용 프로그램에서 표준 순서를 지정 하거나 Windows 소켓 바이트 순서 변환 함수를 사용 하 여를 사용 하 여 더욱 이식 가능한 코드를 만들 수 있습니다.  
  
 MFC 소켓을 사용 하기 위한 이상적인 사례는 통신의 양쪽 끝을 작성 하는 경우: 양쪽 끝에서 MFC를 사용 합니다. Windows 소켓 변환 루틴 를사용하여통신하는FTP서버와같은비MFC응용프로그램바이트스왑직접보관개체에데이터를전달하기전에관리하고시켜야합니다응용프로그램을작성하는경우**ntohs**, **ntohl**, **htons**, 및 **htonl**합니다. 비 MFC 응용 프로그램과 통신에 사용 되는 이러한 함수의 예는이 문서의 뒷부분에 나타납니다.  
  
> [!NOTE]
>  통신의 다른 끝에서 MFC 응용 프로그램 없는 경우 또한 피해 야 할 c + + 개체에서 파생 된 스트리밍 `CObject` 보관 저장소로 받는 사람이 처리할 수 없기 때문에 있습니다. 에 나와 있는 참고를 참조 하십시오. [Windows 소켓: 아카이브 함께 사용 하 여 소켓](../mfc/windows-sockets-using-sockets-with-archives.md)합니다.  
  
 바이트 순서에 대 한 자세한 내용은 Windows SDK에서 사용할 수 있는 Windows 소켓 사양을 참조 하십시오.  
  
## <a name="a-byte-order-conversion-example"></a>바이트 순서 변환 예제  
 다음 예제에 대 한 serialization 함수는 `CSocket` 아카이브를 사용 하는 개체입니다. Windows 소켓 API에서 바이트 순서 변환 함수를 사용 하 여 보여 줍니다.  
  
 이 예제를 작성 하는 소스 코드에 액세스할 수 없습니다 권한이 없는 비 MFC 서버 응용 프로그램과 통신 하는 클라이언트 하는 시나리오를 제공 합니다. 이 시나리오에서는 비 MFC 서버 표준 네트워크 바이트 순서를 사용 하는지 생각해 야 합니다. MFC 클라이언트 응용 프로그램이 사용 하는 반면, 한 `CArchive` 개체는 `CSocket` 개체 및 `CArchive` 표준 네트워크의 반대, "little Endian" 바이트 순서를 사용 합니다.  
  
 통신 하려는 비 MFC 서버에 다음과 같은 메시지 패킷에 대 한 프로토콜을 설정된 하는 있다고 가정 합니다.  
  
 [!code-cpp[NVC_MFCSimpleSocket#5](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_1.cpp)]  
  
 MFC 측면에서이 다음과 같이 표현 됩니다.  
  
 [!code-cpp[NVC_MFCSimpleSocket#6](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_2.cpp)]  
  
 C + +에서는 **구조체** 는 기본적으로 클래스와 같은 것입니다. `Message` 구조는 같은 멤버 함수를 가질 수 있습니다는 `Serialize` 위에서 멤버 함수를 선언 합니다. `Serialize` 멤버 함수는 다음과 비슷합니다.  
  
 [!code-cpp[NVC_MFCSimpleSocket#7](../mfc/codesnippet/cpp/windows-sockets-byte-ordering_3.cpp)]  
  
 한쪽 끝에서 비 MFC 서버 응용 프로그램의 경우 바이트 순서 사이의 분명 한 불일치가 있기 때문에이 예제에서는 데이터의 바이트 순서 변환에 대 한 호출 및 `CArchive` 반대쪽 끝에서 MFC 응용 프로그램에 사용 합니다. 이 예제에서는 Windows 소켓을 제공 하는 바이트 순서 변환 함수 중 몇 가지 보여 줍니다. 다음 표에서 이러한 함수를 설명합니다.  
  
### <a name="windows-sockets-byte-order-conversion-functions"></a>Windows 소켓 Byte-order 변환 함수  
  
|기능|용도|  
|--------------|-------------|  
|**ntohs**|네트워크 바이트 순서에서 16 비트 수량 호스트 바이트 순서 (big Endian에 little Endian)으로 변환 합니다.|  
|**ntohl**|네트워크 바이트 순서에서 32 비트 수량 호스트 바이트 순서 (big Endian에 little Endian)으로 변환 합니다.|  
|**Htons**|네트워크 바이트 순서 (little Endian big Endian을)를 호스트 바이트 순서에서 16 비트 값을 변환 합니다.|  
|**Htonl**|호스트 바이트 순서에서 네트워크 바이트 순서 (little Endian을 big Endian)는 32 비트 수량을 변환 합니다.|  
  
 이 예의 다른 지점은 소켓의 응용 프로그램 통신의 다른 쪽 end에는 비 MFC 응용 프로그램 이면 해야 하지 않는 다음과 같은 작업을 수행할입니다.  
  
 `ar << pMsg;`  
  
 여기서 `pMsg` 클래스에서 파생 된 c + + 개체에 대 한 포인터 `CObject`합니다. MFC 응용 프로그램은 마치와 마찬가지로이 개체와 서버와 관련 된 추가 MFC 정보를 인식 하지 못합니다 보내집니다.  
  
 자세한 내용은 다음을 참조하세요.  
  
-   [Windows 소켓: CAsyncSocket 클래스 사용](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows 소켓: 백그라운드](../mfc/windows-sockets-background.md)  
  
-   [Windows 소켓: 스트림 소켓](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows 소켓: 데이터그램 소켓](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)

