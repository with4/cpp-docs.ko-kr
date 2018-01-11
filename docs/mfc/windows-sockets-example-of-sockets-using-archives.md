---
title: "Windows 소켓: 아카이브를 사용 하는 소켓의 예 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- sockets [MFC], with archives
- examples [MFC], Windows Sockets
- Windows Sockets [MFC], with archives
ms.assetid: 2e3c9bb2-7e7b-4f28-8dc5-6cb7a484edac
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0e70e8ecc14496b03bc758d91f078a926f33532
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-example-of-sockets-using-archives"></a>Windows 소켓: 아카이브를 사용하는 소켓의 예
이 문서에서는 클래스를 사용 하는 예제를 제공 [CSocket](../mfc/reference/csocket-class.md)합니다. 이 예제에서는 사용 `CArchive` 소켓을 통해 데이터를 직렬화 하는 개체입니다. 파일 또는 문서 직렬화 아닌지 note 합니다.  
  
 다음 예제에서는 아카이브를 통해 데이터를 받거나 보내기 위해 사용 되는 방법을 보여주는 `CSocket` 개체입니다. 이 예제는 응용 프로그램 (동일한 컴퓨터에서 또는 네트워크에서 서로 다른 컴퓨터에서)의 두 인스턴스 데이터를 교환할 수 있도록 설계 되었습니다. 인스턴스 데이터를 다른 인스턴스의 받고 통보를 보냅니다. 응용 프로그램에서 교환을 시작할 수 있으며, 서버 또는 다른 응용 프로그램에 클라이언트로 작동할 수 중 하나입니다. 다음 함수는 응용 프로그램의 뷰 클래스에 정의 됩니다.  
  
 [!code-cpp[NVC_MFCSimpleSocket#1](../mfc/codesnippet/cpp/windows-sockets-example-of-sockets-using-archives_1.cpp)]  
  
 이 예제에 대 한 가장 중요 한 작업은 해당 구조는 MFC의 철자와 유사 `Serialize` 함수입니다. **PacketSerialize** 이루어져 있습니다 멤버 함수는 **경우** 문을 **다른** 절. 함수는 두 개의 받는다는 [CArchive](../mfc/reference/carchive-class.md) 매개 변수로 참조: `arData` 및 `arAck`합니다. 경우는 `arData` 보관 개체가 저장 (송신)에 대 한 설정의 **경우** 분기가 실행 됩니다; 그렇지 않은 경우, `arData` 설정 되어 함수 사용 (수신)를 로드 하기 위한는 **다른** 분기 합니다. MFC의 serialization에 대 한 자세한 내용은 참조 [Serialization](../mfc/how-to-make-a-type-safe-collection.md)합니다.  
  
> [!NOTE]
>  `arAck` 보관 개체의 반대 간주 `arData`합니다. 경우 `arData` , 전송을 위한 `arAck` 를 수신 하면 하며, 반대 적용 됩니다.  
  
 송신용, 예제 함수는 데모용으로 난수 데이터가 생성 될 때마다 횟수 지정 된 수에 대 한 루프입니다. 응용 프로그램은 파일 등의 일부 소스에서 실제 데이터를 가져옵니다. `arData` 보관 파일의 삽입 연산자 (**<<**) 스트림을 연속 된 3 개의 데이터 청크를 보내는 데 사용 됩니다.  
  
-   "헤더" 데이터의 특성을 지정 하는 (이 경우의 값은 `bValue` 변수와 복사본 수 전송 됩니다).  
  
     이 예제에서는 두 항목 모두 임의로 생성 됩니다.  
  
-   지정 된 데이터의 복사본 수입니다.  
  
     내부 **에 대 한** 보냅니다 루프 `bValue` 지정한 횟수 만큼 합니다.  
  
-   라는 문자열이 `strText` 수신기는 해당 사용자에 게 표시 하는 합니다.  
  
 수신에 함수가 작동 마찬가지로, 보관 파일의 추출 연산자를 사용 하 여 (**>>**) 보관 파일에서 데이터를 가져옵니다. 수신 응용 프로그램이 표시 하는 보내는 응용 프로그램에 대 한 데이터를 주고 받을 수, 최종 "Received" 메시지를 표시 한 다음 다시 보냈습니다."라는 메시지를 확인 합니다.  
  
 이 통신 모델에서 "Received" 라는 단어에서 메시지가 전송 된 `strText` , 변수가, 통신의 다른 쪽에 표시 하기 위해 특정 수의 데이터 패킷 수신한 받는 사용자를 지정 합니다. 수신기 "sent"를 표시 하기 위해 원래 보낸 사람의 화면에는 비슷한 문자열을 사용 하 여 회신 합니다. 두 문자열의 수신 통신이 성공이 발생 했음을 나타냅니다.  
  
> [!CAUTION]
>  설정된(MFC 이외) 서버와 통신하도록 MFC 클라이언트 프로그램을 작성하는 경우 아카이브를 통해 C++ 개체를 전송하지 마십시오. 서버가 전송 하려는 개체의 종류를 이해 하는 MFC 응용 프로그램, 있지 않으면을 받은 개체를 역직렬화 할 수 없습니다. 문서의 예제 [Windows 소켓: 바이트 순서 지정](../mfc/windows-sockets-byte-ordering.md) 이러한 종류의 통신을 보여 줍니다.  
  
 자세한 내용은 Windows Sockets 사양을 참조: **htonl**, **htons**, **ntohl**, **ntohs**합니다. 또한 자세한 내용은 다음을 참조 합니다.  
  
-   [Windows 소켓: 소켓 클래스에서 파생시키기](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows 소켓: 소켓과 아카이브를 함께 사용하는 방법](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows 소켓: 백그라운드](../mfc/windows-sockets-background.md)  
  
## <a name="see-also"></a>참고 항목  
 [MFC의 Windows 소켓](../mfc/windows-sockets-in-mfc.md)   
 [CArchive::IsStoring](../mfc/reference/carchive-class.md#isstoring)   
 [CArchive::operator <<](../mfc/reference/carchive-class.md#operator_lt_lt)   
 [CArchive::operator >>](../mfc/reference/carchive-class.md#operator_lt_lt)   
 [CArchive::Flush](../mfc/reference/carchive-class.md#flush)   
 [Cobject:: Serialize](../mfc/reference/cobject-class.md#serialize)

