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
ms.openlocfilehash: dadc502900285d879f2fd77af69b1fcf08a4ba1e
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880933"
---
# <a name="wsadata-structure"></a>WSADATA 구조체
합니다 `WSADATA` 구조에 대 한 호출에서 반환 하는 Windows 소켓 초기화 정보를 저장 하는를 사용 하는 `AfxSocketInit` 전역 함수입니다.  
  
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
 Windows 소켓 DLL 사용 하 여 호출자가 필요로 하는 Windows 소켓 사양 버전입니다.  
  
 *wHighVersion*  
 (위와 같이 인코딩된 또한) Windows 소켓 사양이 DLL을 지원할 수 있는 가장 높은 버전입니다. 일반적으로이 동일 *wVersion*합니다.  
  
 *szDescription*  
 Null로 끝나는 ASCII 문자열로 Windows 소켓 DLL 공급 업체 식별을 포함 하 여 Windows 소켓 구현에 대 한 설명의 복사 하는 합니다. 텍스트 (최대 256 자)에 모든 문자를 포함할 수 있지만 컨트롤 등 문자 서식 지정에 대 한 공급 업체는 주의가 요구: 상태 메시지의 응용 프로그램은이를 배치 하는 가장 많이 사용 (잘릴 수 있습니다) 표시 하는 것입니다.  
  
 *szSystemStatus*  
 null로 끝나는 ASCII 문자열 Windows 소켓 DLL 복사 상태 또는 구성에 대 한 관련 정보입니다. Windows 소켓 DLL 정보를 사용자에 게 유용할 수도 직원이 지 원하는 경우에이 필드를 사용 해야 확장으로 고려 되어야 합니다는 *szDescription* 필드입니다.  
  
 *iMaxSockets*  
 단일 프로세스를 노출 시킬 수 있는 소켓의 최대 수입니다. Windows 소켓 구현이 모든 프로세스에 대 한 할당에 대 한 소켓의 전역 풀을 제공할 수 있습니다. 또는 소켓에 대 한 프로세스 당 리소스에 할당할 수 있습니다. 수에는 Windows 소켓 DLL 또는 네트워킹 소프트웨어를 구성 하는 방법은 반영할 잘 수 있습니다. 응용 프로그램 작성자는 Windows 소켓 구현이 응용 프로그램에서 사용할 수 있는지 여부를 조잡 한 확인이 숫자를 사용할 수 있습니다. 예를 들어 X Windows 서버를 확인할 수 있습니다 *iMaxSockets* 처음 시작할 때: 8 보다 작은 경우 응용 프로그램 네트워킹 소프트웨어를 다시 구성 사용자 지정 오류 메시지를 표시 합니다. (이는 상황을 *szSystemStatus* 텍스트를 사용할 수 있습니다.) 물론 보장이 없습니다 특정 응용 프로그램을 실제로 할당할 수 있는 *iMaxSockets* 소켓을 사용 하 여 다른 Windows 소켓 응용 프로그램 수 있기 때문입니다.  
  
 *iMaxUdpDg*  
 전송 되거나 응용 프로그램을 Windows 소켓에서 수신 될 수 있는 최대 사용자 데이터 그램 프로토콜 (UDP) 데이터 그램의 바이트 크기입니다. 구현에서는 제한 하지 않습니다 하는 경우 *iMaxUdpDg* 은 0입니다. Berkeley 소켓의 여러 구현에서 8192 바이트 (필요한 경우 조각화)는 UDP 데이터 그램에 암묵적인 제한이 있습니다. Windows 소켓 구현 예를 들어 조각 리어셈블리 버퍼 할당에 따라 제한이 발생할 수 있습니다. 최소값 *iMaxUdpDg* 를 준수 하는 Windows 소켓에 대 한 구현은 512입니다. 값에 관계 없이 유의 *iMaxUdpDg*, 네트워크에 대 한 최대 전송 단위 (MTU) 보다 큰 브로드캐스트 데이터 그램을 보내려면 하려고 바람직하지 않습니다. (Windows 소켓 API는 MTU를 검색 하는 메커니즘을 제공 하지 않지만 512 바이트 이상 이어야 합니다.)  
  
 *lpVendorInfo*  
 공급 업체별 데이터 구조에 먼 포인터입니다. (제공) 하는 경우이 구조의 정의 Windows Sockets 사양의 범위를 벗어납니다.  
  
> [!NOTE]
>  MFC에서 합니다 `WSADATA` 구조에서 반환 되는 `AfxSocketInit` 함수에서 호출 하는 프로그램 `InitInstance` 함수입니다. 구조를 검색 하 고 나중에 정보를 사용 해야 하는 경우 프로그램에서 저장할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** winsock2.h  
  
## <a name="see-also"></a>참고 항목  
 [구조체, 스타일, 콜백 및 메시지 맵](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxSocketInit](../../mfc/reference/application-information-and-management.md#afxsocketinit)

