---
title: "CSocketAddr Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSocketAddr"
  - "ATL.CSocketAddr"
  - "ATL::CSocketAddr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSocketAddr class"
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSocketAddr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스 형식은 IPv4 및 IPV6 모두를 지 원하는 호스트 주소를 호스트 이름 변환 메서드를 제공 합니다.  
  
## 구문  
  
```  
  
class CSocketAddr  
  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CSocketAddr::CSocketAddr](../Topic/CSocketAddr::CSocketAddr.md)|생성자입니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CSocketAddr::FindAddr](../Topic/CSocketAddr::FindAddr.md)|제공 된 호스트 이름 호스트 주소로 변환 하려면이 메서드를 호출 합니다.|  
|[CSocketAddr::FindINET4Addr](../Topic/CSocketAddr::FindINET4Addr.md)|호스트 주소를 IPv4 호스트 이름 변환 하려면이 메서드를 호출 합니다.|  
|[CSocketAddr::FindINET6Addr](../Topic/CSocketAddr::FindINET6Addr.md)|IPv6 호스트 이름과 호스트 주소를 변환 하려면이 메서드를 호출 합니다.|  
|[CSocketAddr::GetAddrInfo](../Topic/CSocketAddr::GetAddrInfo.md)|특정 요소에 포인터를 반환 하려면이 메서드를 호출 하 여  **addrinfo** 목록.|  
|[CSocketAddr::GetAddrInfoList](../Topic/CSocketAddr::GetAddrInfoList.md)|에 대 한 포인터를 반환 하려면이 메서드를 호출 하 여  **addrinfo** 목록.|  
  
## 설명  
 이 클래스 API 함수 및 소켓 래퍼 라이브러리에서 Windows 사용에 대 한 네트워크 주소를 조회 하는 중립적인 방식을 소켓은 IP 버전을 제공 합니다.  
  
 Win32 API 함수를 사용 하는 네트워크 주소를 찾는 데 사용 되는이 클래스의 멤버  [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520).  
  
 이 클래스는 IPv4 andIPv6 네트워크 주소가 모두 지원합니다.  
  
## 요구 사항  
 **헤더:** atlsocket.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)