---
title: WSADATA 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- WSADATA
dev_langs:
- C++
helpviewer_keywords:
- WSADATA structure [MFC]
ms.assetid: 80cc60e5-f9ae-4290-8ed5-07003136627d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93c98f792e1d72d3e6d4a8e15b8347c653b32f46
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380086"
---
# <a name="wsadata-structure"></a>WSADATA 구조체
`WSADATA` 구조는에 대 한 호출에서 반환 된 Windows 소켓 초기화 정보를 저장 하는 데 사용 되는 `AfxSocketInit` 전역 함수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct WSAData {  
    WORD wVersion;  
    WORD wHighVersion;  
    char szDescription[WSADESCRIPTION_LEN+1];  
    char szSystemStatus[WSASYSSTATUS_LEN+1];  
    unsigned short iMaxSockets;  
    unsigned short iMaxUdpDg;  
    char FAR* lpVendorInfo;  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 *wVersion*  
 Windows 소켓 DLL 호출자가 사용할 수 필요로 하는 Windows 소켓 사양의 버전입니다.  
  
 *wHighVersion*  
 (또한로 인코딩된 위의 설명 참조)이이 DLL을 지원할 수 있는 Windows 소켓 사양의 가장 높은 버전입니다. 보통은이 동일 **wVersion**합니다.  
  
 *szDescription*  
 Null로 끝나는 ASCII 문자열 식별 공급 업체를 비롯 한 Windows 소켓 구현에 대 한 설명을 Windows 소켓 DLL을 복사 하 합니다. 텍스트 (최대 256 자)는 모든 문자를 포함할 수 있지만 컨트롤을 포함 하 고 서식 문자에 대해 공급 업체는 주의가 요구: 상태 메시지에 응용 프로그램은이를 보관 하는 가장 가능성이 높은 사용 (잘릴 수)에 표시 하는 것입니다.  
  
 *szSystemStatus*  
 null로 끝나는 ASCII 문자열 Windows 소켓 DLL 복사 상태 또는 구성에 대 한 관련 정보입니다. Windows 소켓 DLL 정보 지원 담당자; 또는 사용자에 게 유용할 수 있습니다 하는 경우에이 필드를 사용 해야 확장으로 간주 되지 해야는 **szDescription** 필드입니다.  
  
 *iMaxSockets*  
 단일 프로세스 노출 시킬 수는 소켓의 최대 수입니다. Windows 소켓 구현이; 모든 프로세스에 할당 소켓의 전역 풀을 제공할 수 있습니다. 또는 각 프로세스 리소스 소켓에 할당할 수 있습니다. 수는 Windows 소켓 DLL 또는 네트워킹 소프트웨어 구성 된 방식으로 반영도 될 수 있습니다. Windows 소켓 구현이 응용 프로그램에서 사용할 수 있는지 여부의 조잡 표시로 응용 프로그램 작성자가이 숫자를 사용할 수 있습니다. 예를 들어 X Windows 서버 직접 확인할 수 있습니다 **iMaxSockets** 처음 시작 될 때: 8 보다 작은 경우 응용 프로그램이 네트워킹 소프트웨어를 다시 구성 사용자 지정 오류 메시지를 표시 합니다. (이 있는 상황에서 **szSystemStatus** 텍스트를 사용할 수 있습니다.) 물론 보장이 없습니다 특정 응용 프로그램을 실제로 할당할 수 있는 **iMaxSockets** 소켓, 다른 Windows 소켓 응용 프로그램 사용에서 될 수 있으므로 합니다.  
  
 *iMaxUdpDg*  
 Windows 소켓 응용 프로그램에서 수신 하거나 전송 수 있는 최대 데이터 그램 프로토콜 UDP (User) 데이터 그램의 바이트 크기입니다. 구현에서는 제한 하지 않습니다 경우 **iMaxUdpDg** 은 0입니다. Berkeley 소켓의 여러 구현에서 8, 192 바이트 (필요한 경우 조각난)는 UDP 데이터 그램에 암묵적인 제한이 있습니다. Windows 소켓 구현 예를 들어 조각 리어셈블리 버퍼의 할당에 기반 제한을 적용 수 있습니다. 최소 값 **iMaxUdpDg** 규격 Windows 소켓 구현은 512입니다. 값에 관계 없이 유의 **iMaxUdpDg**, 네트워크에 대 한 최대 전송 단위 (MTU) 보다 큰 브로드캐스트 데이터 그램을 보내려고 시도 바람직하지 않습니다. (Windows 소켓 API는 MTU을 검색 하는 메커니즘을 제공 하지 않지만 512 바이트 이상 이어야 합니다.)  
  
 *lpVendorInfo*  
 공급 업체 관련 데이터 구조에 대 한 far 포인터입니다. (제공 경우)이 구조의 정의 Windows 소켓 사양의 범위를 벗어납니다.  
  
> [!NOTE]
>  Mfc에서 `WSADATA` 구조에서 반환 되는 `AfxSocketInit` 함수에서 호출 하는 프로그램 `InitInstance` 함수입니다. 구조를 검색 하 고 나중에 정보를 사용 해야 하는 경우 프로그램에 저장할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winsock2.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)

