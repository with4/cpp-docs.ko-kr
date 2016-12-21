---
title: "CIPAddressCtrl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CIPAddressCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIPAddressCtrl class"
  - "공용 컨트롤, Internet Explorer 4.0"
  - "Internet address edit box"
  - "Internet Explorer 4.0 common controls"
  - "Internet protocol address box"
  - "IP address control"
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CIPAddressCtrl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

공용 IP 주소가 Windows 컨트롤의 기능을 제공합니다.  
  
## 구문  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CIPAddressCtrl::CIPAddressCtrl](../Topic/CIPAddressCtrl::CIPAddressCtrl.md)|`CIPAddressCtrl` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CIPAddressCtrl::ClearAddress](../Topic/CIPAddressCtrl::ClearAddress.md)|IP Address 컨트롤의 내용을 지웁니다.|  
|[CIPAddressCtrl::Create](../Topic/CIPAddressCtrl::Create.md)|IP 주소 컨트롤을 만들고 연결 하는 `CIPAddressCtrl` 개체입니다.|  
|[CIPAddressCtrl::CreateEx](../Topic/CIPAddressCtrl::CreateEx.md)|지정한 Windows 확장된 스타일에 IP 주소 컨트롤을 만들고 연결 하는 `CIPAddressCtrl` 개체입니다.|  
|[CIPAddressCtrl::GetAddress](../Topic/CIPAddressCtrl::GetAddress.md)|모든 네 개의 필드 컨트롤에 있는 IP 주소에 대 한 주소 값을 검색합니다.|  
|[CIPAddressCtrl::IsBlank](../Topic/CIPAddressCtrl::IsBlank.md)|IP 주소 컨트롤의 모든 필드가 비어 있는 경우를 결정 합니다.|  
|[CIPAddressCtrl::SetAddress](../Topic/CIPAddressCtrl::SetAddress.md)|IP Address 컨트롤에서 모든 네 개의 필드에 대 한 주소 값을 설정합니다.|  
|[CIPAddressCtrl::SetFieldFocus](../Topic/CIPAddressCtrl::SetFieldFocus.md)|IP Address 컨트롤에서 지정 된 필드에 키보드 포커스를 설정합니다.|  
|[CIPAddressCtrl::SetFieldRange](../Topic/CIPAddressCtrl::SetFieldRange.md)|IP Address 컨트롤에서 지정 된 필드에서 범위를 설정합니다.|  
  
## 설명  
 컨트롤 편집 컨트롤과 유사 제어는 IP 주소 입력 하 고 인터넷 프로토콜 \(IP\) 형식에서 숫자 주소를 조작할 수 있습니다.  
  
 이 컨트롤 \(즉의 `CIPAddressCtrl` 클래스\) Microsoft Internet Explorer 4.0 및 나중에 실행 하는 프로그램에만 사용할 수 있습니다.  Windows NT 및 Windows의 이후 버전에서 사용할 수 있는 수도 있습니다.  
  
 IP Address 컨트롤에 대 한 자세한 내용은  [IP 주소 컨트롤](http://msdn.microsoft.com/library/windows/desktop/bb761372) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CIPAddressCtrl`  
  
## 요구 사항  
 **헤더:**  afxcmn.h  
  
## 참고 항목  
 [CWnd 클래스](../../mfc/reference/cwnd-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)